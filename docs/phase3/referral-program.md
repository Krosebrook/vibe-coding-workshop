# Referral Program

> How alumni can refer friends and colleagues to the Vibe Coding Workshop — and how we track and reward it.

---

## Overview

Alumni referrals are the most powerful acquisition channel for a workshop like this. When someone has genuinely shipped 4 apps in one day, they tell people about it. The referral program formalizes that behavior with incentives and makes it easy for alumni to share.

**Goal:** 30% of new registrations come from alumni referrals by the end of Phase 3.

---

## How It Works (Participant-Facing)

### For the Referring Alumni

1. **Get your referral link** from the participant portal (`/dashboard/referrals`)
   - Format: `vibecodingworkshop.com/r/[username]`
   - Example: `vibecodingworkshop.com/r/marcusb`

2. **Share it** — in messages, social posts, email, anywhere

3. **Earn a reward** when someone registers using your link and attends:
   - Cash reward: $25 Venmo/PayPal (default)
   - Workshop credit: $40 toward a future workshop (higher value option)
   - Merch option: Workshop swag pack (if/when merch exists)

4. **Track your referrals** — the portal shows who signed up via your link and when they complete

### For the Referred Person

- They get a **10% discount** automatically applied at checkout when clicking a referral link
- No promo code needed — it's embedded in the URL
- The discount is real and visible in the Stripe Checkout

---

## Mechanics

### Referral Link Structure

```
Base URL: https://vibecodingworkshop.com
Referral path: /r/[ref_code]
Redirect: → /register?ref=[ref_code]
```

The `/r/[ref_code]` path is a lightweight redirect (handled by Next.js or Vercel config) that:
1. Sets a `ref` cookie (30-day expiry)
2. Redirects to the registration page

The `ref` cookie is read during Stripe Checkout to attribute the registration.

### Attribution

```
1. Visitor clicks referral link
2. Cookie set: ref=[ref_code], expires in 30 days
3. Visitor browses, leaves, comes back (cookie persists)
4. Visitor registers and pays
5. Webhook reads ref cookie from session metadata
6. Referral record created in Supabase
7. Alumni notified by email: "Someone you referred just registered!"
```

---

## Data Model

### ReferralCode

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "ReferralCode",
  "description": "A unique referral code belonging to an alumni participant",
  "type": "object",
  "required": ["id", "userId", "code", "createdAt"],
  "properties": {
    "id": { "type": "string" },
    "userId": { "type": "string", "description": "References profiles.id" },
    "code": { "type": "string", "description": "Unique short code, e.g., 'marcusb'" },
    "isActive": { "type": "boolean", "default": true },
    "createdAt": { "type": "string", "format": "date-time" }
  }
}
```

### ReferralEvent

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "ReferralEvent",
  "description": "A completed referral — someone registered using a referral link",
  "type": "object",
  "required": ["id", "referralCodeId", "referredEmail", "status", "createdAt"],
  "properties": {
    "id": { "type": "string" },
    "referralCodeId": { "type": "string", "description": "References referral_codes.id" },
    "referredEmail": { "type": "string", "format": "email" },
    "registrationId": { "type": "string", "description": "References workshop_registrations.id" },
    "status": {
      "type": "string",
      "enum": ["registered", "attended", "rewarded", "cancelled"],
      "description": "registered: paid; attended: showed up; rewarded: alumni paid out"
    },
    "rewardType": {
      "type": "string",
      "enum": ["cash", "credit", "merch", "none"]
    },
    "rewardAmount": { "type": "number" },
    "rewardPaidAt": { "type": "string", "format": "date-time" },
    "createdAt": { "type": "string", "format": "date-time" }
  }
}
```

---

## Reward Payout Process

Rewards are paid after the referred person **attends** (not just registers) to prevent gaming:

1. Referred person registers → status: `registered`
2. Referred person attends the workshop (checked in on the day) → status: `attended`
3. Instructor reviews referral queue in admin portal weekly
4. Payout sent via Venmo/PayPal → status: `rewarded`
5. Alumni notified by email: "Your $25 referral reward is on its way!"

**Timeline:** Rewards are paid within 7 days of the attended workshop.

---

## Referral Dashboard (Portal Feature)

In the participant portal (`/dashboard/referrals`):

| Element | Description |
|---------|-------------|
| Your referral link | Copyable link and a QR code |
| Share buttons | Twitter/X, LinkedIn, copy-to-clipboard |
| Stats | Clicks / Registrations / Attended / Rewarded |
| Referral history | List of each referral with status and reward |
| Payout preference | Choose: cash (default), credit, merch |

---

## Launch Sequence

### Step 1: Email alumni after the first cohort completes

**Subject:** Want to bring a friend? You'll both get something.

```
Hi [Name],

You shipped 4 apps last week. That's not something most people do.

If you know someone who should do what you did — a friend, a teammate, 
a founder — send them your personal referral link:

[referral link]

They get 10% off. You get $25 when they show up.

No expiry. No catch.

Kyle
```

### Step 2: Feature the referral program in the portal

- Prominent card on the dashboard: "Refer a friend → earn $25"
- Reminder in the post-workshop follow-up email sequence (1 month after)

### Step 3: Social proof prompt

After 10 successful referrals: publish a "referred by the community" section on the marketing site (see [Project Showcase Gallery](./project-showcase-gallery.md)).

---

## Rules & Abuse Prevention

- One referral code per participant
- Self-referrals are blocked (can't use your own code)
- Referral must result in attendance (not just registration) before reward
- Corporate referrals use a separate affiliate program (see [affiliate-partnership-program.md](./affiliate-partnership-program.md))
- If a registration is refunded, the referral is voided
- Codes can be deactivated by admin if misuse is detected

---

## Goals & Metrics

| Metric | Phase 3 Target |
|--------|---------------|
| % of alumni with active referral codes | > 80% |
| % of alumni who share their link at least once | > 40% |
| Referral conversion rate (click → registration) | > 5% |
| % of new registrations from referrals | > 30% |
| Average time from workshop → first referral share | < 7 days |

---

*Owner: Kyle Rosebrook · Part of [Phase 3 documentation](./README.md)*
