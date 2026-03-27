# Affiliate & Partnership Program

> How to build and manage a network of partners who promote the Vibe Coding Workshop — and earn a commission for each enrollment they drive.

---

## Overview

The affiliate program extends reach beyond alumni referrals. Where the referral program is peer-to-peer ("tell your friend"), the affiliate program is partner-to-audience — newsletters, communities, creators, and companies that can promote the workshop to their audiences in exchange for a revenue share.

**Goal:** 3–5 active affiliate partners driving 20% of registrations by end of Phase 3.

---

## Program Types

### Type 1 — Content Affiliate
A newsletter writer, blogger, or creator who mentions the workshop to their audience.

- **Commission:** 15% of each registration they drive
- **Payment:** Monthly via PayPal/Venmo after a 30-day hold
- **Tracking:** Unique affiliate link + UTM parameters
- **Requirements:** Authentic audience interest in tech, building, or career change

### Type 2 — Community Partner
A community (Discord, Slack, Meetup, Reddit, etc.) that promotes the workshop to its members.

- **Commission:** 15% of registrations + option for a free seat to give away
- **Co-benefit:** We promote their community to workshop participants
- **Requirements:** Community with 500+ active members, aligned audience

### Type 3 — Corporate Referral Partner
A consultant, coach, or service provider who refers companies to the corporate training program.

- **Commission:** 10% of the corporate engagement fee (paid once, on completion)
- **Requirements:** Pre-approved list; must qualify the referral before making the intro
- **Process:** Referral must be registered in the system before the intro

### Type 4 — Institution Partner
A bootcamp, community college, library, or nonprofit that integrates the workshop into their programming.

- **Revenue share:** 20% discount on bulk seats + co-branded delivery
- **Requirements:** Minimum 8-seat commitment per cohort
- **Benefits:** Co-branded certificate, joint marketing

---

## Application Process

1. **Apply** via a simple form (email or Typeform):
   - Name / Organization
   - Audience size and description
   - Why this is a fit for your audience
   - Preferred partnership type

2. **Review** by Kyle (within 5 business days):
   - Is the audience aligned?
   - Is the promoter authentic and credible?
   - No conflicts with other partners or brand values?

3. **Approve and onboard:**
   - Send affiliate agreement (simple 1-page doc)
   - Create affiliate link in tracking system
   - Provide promotional assets (copy, images, discount codes)
   - Add to monthly affiliate newsletter

4. **Launch** — partner shares the workshop with their audience

---

## Affiliate Tracking

### Tooling (Phase 3 v1)

Use **Rewardful** (affiliate software that integrates with Stripe) or build lightweight custom tracking:

| Tool | Integration | Cost |
|------|-------------|------|
| Rewardful | Stripe native, easy setup | ~$49/mo |
| PartnerStack | More features, enterprise-grade | $500+/mo |
| Custom (Supabase + redirect) | Full control, no recurring cost | Dev time |

**Phase 3 v1 recommendation:** Rewardful for lowest friction. Migrate to custom if it becomes limiting.

### Link Structure

```
Affiliate link: https://vibecodingworkshop.com/?via=[affiliate_code]
Example: https://vibecodingworkshop.com/?via=techwithtimmy
```

The `via` parameter is read by Rewardful or custom middleware and attributed to the affiliate's account.

---

## Affiliate Dashboard

Each affiliate gets access to a lightweight dashboard (Rewardful provides this) showing:

- Total clicks on their link
- Total registrations attributed
- Total commission earned
- Pending payout vs. paid out
- Promotional assets and link

---

## Commission Data Model

### AffiliatePartner

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "AffiliatePartner",
  "description": "An approved affiliate or partner",
  "type": "object",
  "required": ["id", "name", "email", "type", "code", "commissionRate", "status"],
  "properties": {
    "id": { "type": "string" },
    "name": { "type": "string" },
    "email": { "type": "string", "format": "email" },
    "type": {
      "type": "string",
      "enum": ["content", "community", "corporate-referral", "institution"]
    },
    "code": { "type": "string", "description": "Unique tracking code, e.g., 'techwithtimmy'" },
    "commissionRate": {
      "type": "number",
      "minimum": 0,
      "maximum": 1,
      "description": "Decimal commission rate, e.g., 0.15 for 15%"
    },
    "status": {
      "type": "string",
      "enum": ["pending", "active", "paused", "terminated"]
    },
    "payoutMethod": {
      "type": "string",
      "enum": ["paypal", "venmo", "bank-transfer", "credit"]
    },
    "createdAt": { "type": "string", "format": "date-time" }
  }
}
```

---

## Promotional Assets

Provide affiliates with a standard kit:

### Copy Snippets

**Short (social / DM):**
> "If you've ever wanted to build an app but don't know where to start — [link]. I know the instructor. It's the real deal."

**Medium (newsletter):**
> "[Workshop Name] is a one-day workshop where non-technical people build and deploy 4 real apps using AI tools. No prior coding required. If your audience has founders, designers, or career-changers who've been curious about building — this is worth sharing. [Referral link]"

**Long (blog post / review):**
Provide a draft 300-word post that affiliates can adapt. Focus on the transformation (I went from zero to 4 live apps) rather than features.

### Images

- Workshop logo (dark + light versions)
- "4 apps in 1 day" stat graphic
- Before/after: "What you come in knowing vs. what you leave with"
- Instructor headshot with permission

---

## Partner Benefits Summary

| Benefit | Content Affiliate | Community Partner | Corporate Referral | Institution |
|---------|------------------|-------------------|-------------------|-------------|
| Commission | 15% | 15% | 10% of fee | 20% discount |
| Free seat giveaway | ❌ | 1 per cohort | ❌ | 1 per cohort |
| Co-marketing | ❌ | ✅ | ❌ | ✅ |
| Branded certificate | ❌ | ❌ | ❌ | ✅ |
| Affiliate dashboard | ✅ | ✅ | ✅ | ✅ |

---

## Partner Communication Cadence

| Cadence | Content |
|---------|---------|
| Onboarding | Welcome email, assets, tracking link, affiliate agreement |
| Monthly | Newsletter: upcoming cohorts, new assets, top performer shoutout |
| Per cohort launch | "New cohort open — here's your promo link" email |
| Quarterly | Review call (optional, for top partners) |
| Annually | Program terms review, commission adjustment |

---

## Brand Safety Guidelines

All affiliates agree to:

- Not make income claims ("you'll make $X after this workshop")
- Not misrepresent the workshop format, price, or outcomes
- Not run paid ads using the workshop name without approval
- Clearly disclose the affiliate relationship per FTC guidelines
- Not promote to audiences that don't fit the target profile

Violations can result in immediate termination and commission forfeiture.

---

## Phase 3 Launch Targets

| Metric | Target |
|--------|--------|
| Active affiliates at Phase 3 launch | 3–5 |
| Registrations from affiliate traffic | 20% of total |
| Average commission per affiliate (monthly) | $100–$500 |
| First affiliate-driven cohort | Fall 2026 |

---

*Owner: Kyle Rosebrook · Part of [Phase 3 documentation](./README.md)*
