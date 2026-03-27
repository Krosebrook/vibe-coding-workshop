# Data Schemas

> Data structures and contracts used by the Vibe Coding Workshop — for workshop projects and operational data.

---

## Workshop Project Schemas

### Project 01 — Personal Landing Page

**No persistent data.** Static HTML/CSS only.

---

### Project 02 — Mood Tracker

#### MoodEntry

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "MoodEntry",
  "description": "A single mood log entry",
  "type": "object",
  "required": ["id", "mood", "timestamp"],
  "properties": {
    "id": {
      "type": "string",
      "description": "Unique identifier (UUID v4)",
      "example": "a1b2c3d4-e5f6-7890-abcd-ef1234567890"
    },
    "mood": {
      "type": "integer",
      "minimum": 1,
      "maximum": 5,
      "description": "Mood score: 1 (very sad) to 5 (very happy)"
    },
    "note": {
      "type": "string",
      "maxLength": 280,
      "description": "Optional text note"
    },
    "timestamp": {
      "type": "string",
      "format": "date-time",
      "description": "ISO 8601 datetime of entry"
    },
    "tags": {
      "type": "array",
      "items": { "type": "string" },
      "description": "Optional tags (e.g., ['work', 'exercise'])"
    }
  }
}
```

**Example:**
```json
{
  "id": "a1b2c3d4-e5f6-7890-abcd-ef1234567890",
  "mood": 4,
  "note": "Good day, got a lot done",
  "timestamp": "2026-06-15T09:30:00Z",
  "tags": ["work", "productive"]
}
```

---

### Project 03 — Recipe Finder

#### RecipeSearch (API Request)

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "RecipeSearch",
  "description": "Parameters for a recipe search query",
  "type": "object",
  "required": ["query"],
  "properties": {
    "query": {
      "type": "string",
      "minLength": 2,
      "description": "Ingredient or dish name to search for"
    },
    "cuisine": {
      "type": "string",
      "description": "Cuisine type filter (e.g., 'italian', 'mexican')"
    },
    "maxReadyTime": {
      "type": "integer",
      "minimum": 1,
      "description": "Maximum prep+cook time in minutes"
    },
    "diet": {
      "type": "string",
      "enum": ["vegetarian", "vegan", "gluten-free", "dairy-free"],
      "description": "Dietary restriction filter"
    }
  }
}
```

#### Recipe (API Response — simplified)

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "Recipe",
  "type": "object",
  "properties": {
    "id": { "type": "integer" },
    "title": { "type": "string" },
    "image": { "type": "string", "format": "uri" },
    "readyInMinutes": { "type": "integer" },
    "servings": { "type": "integer" },
    "sourceUrl": { "type": "string", "format": "uri" },
    "summary": { "type": "string", "description": "HTML summary" },
    "ingredients": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "name": { "type": "string" },
          "amount": { "type": "number" },
          "unit": { "type": "string" }
        }
      }
    }
  }
}
```

---

### Project 04 — AI Chat Assistant

#### ChatMessage

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "ChatMessage",
  "description": "A single message in the chat interface",
  "type": "object",
  "required": ["id", "role", "content", "timestamp"],
  "properties": {
    "id": {
      "type": "string",
      "description": "UUID v4"
    },
    "role": {
      "type": "string",
      "enum": ["user", "assistant", "system"],
      "description": "Who sent the message"
    },
    "content": {
      "type": "string",
      "description": "Message text content"
    },
    "timestamp": {
      "type": "string",
      "format": "date-time"
    },
    "isStreaming": {
      "type": "boolean",
      "description": "True while the assistant response is being streamed"
    }
  }
}
```

#### ChatSession

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "ChatSession",
  "description": "A complete chat conversation",
  "type": "object",
  "required": ["id", "messages", "createdAt"],
  "properties": {
    "id": { "type": "string" },
    "title": {
      "type": "string",
      "description": "Auto-generated from first user message"
    },
    "systemPrompt": {
      "type": "string",
      "description": "The AI assistant's personality/instructions"
    },
    "messages": {
      "type": "array",
      "items": { "$ref": "#/definitions/ChatMessage" }
    },
    "createdAt": {
      "type": "string",
      "format": "date-time"
    },
    "model": {
      "type": "string",
      "description": "AI model used (e.g., 'claude-3-5-sonnet-20241022')"
    }
  }
}
```

---

## Operational Schemas

### WaitlistEntry

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "WaitlistEntry",
  "description": "A waitlist sign-up for the workshop",
  "type": "object",
  "required": ["email", "signedUpAt"],
  "properties": {
    "id": { "type": "string" },
    "email": {
      "type": "string",
      "format": "email"
    },
    "name": {
      "type": "string",
      "description": "Optional full name"
    },
    "background": {
      "type": "string",
      "enum": ["designer", "marketer", "founder", "student", "career-change", "curious", "other"],
      "description": "Self-reported background"
    },
    "signedUpAt": {
      "type": "string",
      "format": "date-time"
    },
    "source": {
      "type": "string",
      "description": "How they heard about the workshop"
    },
    "cohortInterest": {
      "type": "string",
      "description": "Which cohort they're interested in"
    }
  }
}
```

### WorkshopParticipant

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "WorkshopParticipant",
  "description": "A registered workshop participant",
  "type": "object",
  "required": ["id", "email", "name", "cohort", "registeredAt"],
  "properties": {
    "id": { "type": "string" },
    "email": { "type": "string", "format": "email" },
    "name": { "type": "string" },
    "githubUsername": { "type": "string" },
    "cohort": {
      "type": "string",
      "description": "e.g., 'summer-2026-01'"
    },
    "paymentStatus": {
      "type": "string",
      "enum": ["pending", "paid", "refunded", "scholarship"]
    },
    "registeredAt": { "type": "string", "format": "date-time" },
    "checkedIn": { "type": "boolean" },
    "projectsCompleted": {
      "type": "integer",
      "minimum": 0,
      "maximum": 4
    },
    "feedbackSubmitted": { "type": "boolean" }
  }
}
```

---

## Phase 3 Schemas

### WorkshopRegistration

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "WorkshopRegistration",
  "description": "A completed workshop registration (post-payment via Stripe)",
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

---

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
    "referralCodeId": { "type": "string" },
    "referredEmail": { "type": "string", "format": "email" },
    "registrationId": { "type": "string" },
    "status": {
      "type": "string",
      "enum": ["registered", "attended", "rewarded", "cancelled"]
    },
    "rewardType": { "type": "string", "enum": ["cash", "credit", "merch", "none"] },
    "rewardAmount": { "type": "number" },
    "rewardPaidAt": { "type": "string", "format": "date-time" },
    "createdAt": { "type": "string", "format": "date-time" }
  }
}
```

---

### AffiliatePartner

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "AffiliatePartner",
  "description": "An approved affiliate or partner in the affiliate program",
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
      "description": "Decimal rate, e.g., 0.15 for 15%"
    },
    "status": { "type": "string", "enum": ["pending", "active", "paused", "terminated"] },
    "payoutMethod": { "type": "string", "enum": ["paypal", "venmo", "bank-transfer", "credit"] },
    "createdAt": { "type": "string", "format": "date-time" }
  }
}
```

---

### ShowcaseProject

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "ShowcaseProject",
  "description": "A participant project approved for public showcase display",
  "type": "object",
  "required": ["id", "participantId", "projectName", "liveUrl", "projectNumber", "cohortId", "consentGiven", "status"],
  "properties": {
    "id": { "type": "string" },
    "participantId": { "type": "string" },
    "projectNumber": { "type": "integer", "minimum": 1, "maximum": 4 },
    "projectName": { "type": "string" },
    "liveUrl": { "type": "string", "format": "uri" },
    "description": { "type": "string", "maxLength": 280 },
    "screenshotUrl": { "type": "string", "format": "uri" },
    "cohortId": { "type": "string" },
    "displayName": { "type": "string", "description": "How participant wants credit displayed" },
    "githubUrl": { "type": "string", "format": "uri" },
    "tags": { "type": "array", "items": { "type": "string" } },
    "consentGiven": { "type": "boolean" },
    "consentWithdrawnAt": { "type": "string", "format": "date-time" },
    "isFeatured": { "type": "boolean", "default": false },
    "status": { "type": "string", "enum": ["pending", "approved", "declined", "withdrawn"] },
    "reviewedAt": { "type": "string", "format": "date-time" },
    "submittedAt": { "type": "string", "format": "date-time" }
  }
}
```

---

*These schemas serve as contracts between UI, backend, and AI tooling. Update when data structures change.*
