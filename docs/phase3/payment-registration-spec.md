# Payment & Registration Spec

> How to handle payment processing and workshop registration for Phase 3 — from "I'm interested" to "confirmed and paid."

---

## Overview

Phase 3 requires a real payment and registration system. The current waitlist (email link) works at small scale but doesn't handle:
- Multiple workshop formats at different price points
- Early-bird discounts and promo codes
- Confirmation and receipt emails
- Refund and cancellation workflow
- Reporting on revenue and registrations

This spec covers the tooling, data model, workflows, and implementation plan for Phase 3 registration.

---

## Registration Formats

| Format | Price Point | Registration Type |
|--------|-------------|-------------------|
| In-Person Cohort | $297–$397 | Individual, limited seats |
| Virtual Cohort | $197–$247 | Individual, limited seats |
| Multi-Day Intensive | $497–$597 | Individual, limited seats |
| Corporate Team (Tier 1) | $2,500–$4,000 | Invoice / SOW |
| Corporate Team (Tier 2) | $5,000–$8,000 | Invoice / SOW |
| Self-Paced Course | $97–$197 | Instant access, no seat limit |

Corporate clients use a separate invoice process (not this registration form). This spec covers individual registration only.

---

## Tooling Recommendation

### Option A — Stripe + Custom Form (Recommended for v1)

| Component | Tool |
|-----------|------|
| Payment processing | Stripe Checkout |
| Registration form | Typeform or Tally (embeds on site) |
| Confirmation emails | Resend |
| Receipts | Stripe (automatic) |
| Reporting | Stripe Dashboard |
| Customer records | Supabase (synced via webhook) |

**Why:** Stripe Checkout handles PCI compliance, mobile UX, and international cards. Resend handles transactional email. Both have great docs and are used in the workshop curriculum — using them in production is consistent with teaching.

### Option B — Lemon Squeezy (Simpler)

All-in-one: payment, license keys, email, and refunds. Less customization but faster to launch.

**Why consider:** No webhook setup, no separate email tool. Single dashboard.

### Option C — Eventbrite (Avoid for Phase 3)

- Higher fees (6%+)
- No customization
- Drives people off your site

---

## Registration Flow

```
1. Visitor clicks "Register" or "Join Waitlist" on marketing site
2. Redirected to registration form (Typeform/Tally embed or /register page)
3. Form collects:
   - Name
   - Email
   - Workshop format selection
   - Background (dropdown — same options as WaitlistEntry schema)
   - App idea (optional, one sentence)
   - Promo code (optional)
4. On submit: redirect to Stripe Checkout
5. Stripe Checkout:
   - Participant enters payment details
   - Stripe handles 3DS / fraud checks
6. On payment success:
   - Stripe webhook fires → Supabase record created
   - Resend confirmation email sent
   - Participant added to cohort roster
   - Portal invite email sent (if portal is live)
7. On payment failure:
   - Stripe shows error
   - No record created
   - Participant can retry
```

---

## Stripe Configuration

### Products and Prices

Create in Stripe Dashboard:

```
Product: In-Person Workshop — Summer 2026
  Price: $297.00 USD (one-time)
  Price ID: price_inperson_summer2026

Product: Virtual Workshop — Fall 2026
  Price: $197.00 USD (one-time)
  Price ID: price_virtual_fall2026

Product: Multi-Day Intensive — Fall 2026
  Price: $497.00 USD (one-time)
  Price ID: price_intensive_fall2026

Product: Self-Paced Course
  Price: $97.00 USD (one-time)
  Price ID: price_selfpaced_v1
```

### Promo Codes

| Code | Discount | Expiry | Purpose |
|------|----------|--------|---------|
| `EARLYBIRD` | 20% off | 48 hrs after cohort opens | Early bird window |
| `ALUMNI10` | 10% off | Permanent | Alumni referral |
| `REFER-[username]` | $25 off | Per referral | Referral program |
| `SCHOLARSHIP` | 100% off | Per request | Scholarship access |

Create in Stripe → Promotions. Reference in the registration form as an optional field.

---

## Webhook Handler

A serverless function (Vercel Edge Function or Netlify Function) handles Stripe webhooks:

### Events to Handle

```
checkout.session.completed → Create WorkshopRegistration record in Supabase
payment_intent.payment_failed → Log to error table, send support email
charge.refunded → Update registration status to 'refunded', send confirmation
```

### WorkshopRegistration Schema

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "WorkshopRegistration",
  "description": "A completed workshop registration (post-payment)",
  "type": "object",
  "required": ["id", "email", "name", "cohortId", "format", "amountPaid", "registeredAt"],
  "properties": {
    "id": { "type": "string", "description": "UUID v4" },
    "stripeSessionId": { "type": "string" },
    "stripeCustomerId": { "type": "string" },
    "email": { "type": "string", "format": "email" },
    "name": { "type": "string" },
    "cohortId": { "type": "string", "description": "e.g., 'fall-2026-virtual-01'" },
    "format": {
      "type": "string",
      "enum": ["in-person", "virtual", "intensive", "self-paced", "corporate"]
    },
    "amountPaid": { "type": "number", "description": "Amount in USD" },
    "promoCodeUsed": { "type": "string" },
    "status": {
      "type": "string",
      "enum": ["confirmed", "refunded", "cancelled", "transferred"],
      "default": "confirmed"
    },
    "registeredAt": { "type": "string", "format": "date-time" },
    "background": {
      "type": "string",
      "enum": ["designer", "marketer", "founder", "student", "career-change", "curious", "other"]
    },
    "appIdea": { "type": "string" },
    "portalAccessGranted": { "type": "boolean", "default": false }
  }
}
```

---

## Confirmation Email Templates

### Template 1: Registration Confirmed (Resend)

**Subject:** You're in — [Workshop Name] on [Date] 🚀

```
Hi [Name],

You're registered for the Vibe Coding Workshop on [Date].

Here's what's next:

1. You'll get a "Get Ready" email 2 weeks before the workshop.
2. In the meantime, don't do any pre-studying — seriously.
3. Just think about one thing you'd want to build.

Your details:
- Workshop: [Format] — [Date]
- Location/Link: [Venue address or Zoom link sent 48 hrs before]
- Paid: $[Amount] · Receipt attached

Questions? hello@vibecodingworkshop.com

See you there.
Kyle
```

### Template 2: Self-Paced Course Access

**Subject:** Your Vibe Coding course is ready

```
Hi [Name],

Your self-paced course access is ready.

Go here to get started: [Portal URL or Gumroad download link]

When you're done with all 4 projects, drop your live URLs in the #project-submissions channel in our Discord: [Discord link]

Questions? hello@vibecodingworkshop.com

Kyle
```

---

## Refund Policy

- **Full refund:** Requested more than 14 days before the workshop date
- **50% refund:** Requested 7–14 days before
- **No refund:** Less than 7 days before; credit toward a future cohort offered instead
- **Self-paced course:** No refunds after accessing course materials (first lesson)
- **Exceptions:** All edge cases handled case-by-case by Kyle

Process refunds manually via Stripe Dashboard. Update registration status in Supabase. Send confirmation email via Resend.

---

## Capacity Management

### Seat Limits

In-person: 30 seats (Phase 3 capacity increase)  
Virtual: 30 seats  
Multi-Day Intensive: 20 seats  
Self-Paced Course: Unlimited  

When a cohort is sold out:
1. Stripe product price sets to $0 (or deactivate the link)
2. Update marketing site to "Sold Out — Join Waitlist for Next Cohort"
3. Collect waitlist via existing email link (Phase 1 item)
4. Run PB02 — Waitlist to Registered Playbook for the next cohort

---

## Implementation Phases

### Phase 3-A (Launch): Stripe + Typeform
- [ ] Create Stripe products and prices for all formats
- [ ] Create Typeform registration forms for each format
- [ ] Set up Resend account and email templates
- [ ] Build Stripe webhook handler (Vercel Function)
- [ ] Connect webhook to Supabase (creates WorkshopRegistration record)
- [ ] Test end-to-end with a $1 test purchase
- [ ] Update index.html register buttons to point to Typeform forms

### Phase 3-B (Optimize): Integrated Registration
- [ ] Build custom /register page (Next.js) in participant portal
- [ ] Embed Stripe Checkout in the flow
- [ ] Add promo code field with live discount preview
- [ ] Add capacity indicator ("3 seats left")
- [ ] Send portal invite email after successful registration (if portal is live)

---

*Owner: Kyle Rosebrook · Part of [Phase 3 documentation](./README.md)*
