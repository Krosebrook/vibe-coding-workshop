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

*These schemas serve as contracts between UI, backend, and AI tooling. Update when data structures change.*
