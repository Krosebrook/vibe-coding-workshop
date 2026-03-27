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

---

## Phase 4 Schemas

### PromptLibraryEntry

Used by the Prompt Library web app (`docs/phase-4/tools/prompt-library.md`).

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "PromptLibraryEntry",
  "description": "A single prompt in the Vibe Coding Prompt Library",
  "type": "object",
  "required": ["id", "title", "description", "prompt", "tags", "category", "aiTools", "skillLevel"],
  "properties": {
    "id": {
      "type": "string",
      "pattern": "^[a-z]+-[0-9]{3}$",
      "description": "Unique prompt ID (e.g., 'debug-001')",
      "example": "debug-001"
    },
    "title": {
      "type": "string",
      "maxLength": 80,
      "description": "Short human-readable title"
    },
    "description": {
      "type": "string",
      "maxLength": 200,
      "description": "One or two sentence description of what the prompt does"
    },
    "prompt": {
      "type": "string",
      "description": "The prompt body. Use {{VARIABLE_NAME}} for replaceable variables."
    },
    "variables": {
      "type": "array",
      "items": {
        "type": "object",
        "required": ["name", "description"],
        "properties": {
          "name": { "type": "string" },
          "description": { "type": "string" },
          "example": { "type": "string" }
        }
      },
      "description": "Variables in the prompt that users replace"
    },
    "tags": {
      "type": "array",
      "items": { "type": "string" },
      "minItems": 1,
      "description": "Searchable tags"
    },
    "category": {
      "type": "string",
      "enum": [
        "debugging", "scaffolding", "ui-generation", "api-integration",
        "accessibility", "seo", "deployment", "refactoring",
        "documentation", "prompting", "security", "performance"
      ]
    },
    "aiTools": {
      "type": "array",
      "items": {
        "type": "string",
        "enum": ["claude", "cursor", "chatgpt", "gemini", "copilot", "windsurf", "v0", "all"]
      },
      "description": "Which AI tools this prompt works well with"
    },
    "skillLevel": {
      "type": "string",
      "enum": ["beginner", "intermediate", "advanced"]
    },
    "workshopProject": {
      "type": "array",
      "items": {
        "type": "string",
        "enum": ["01", "02", "03", "04"]
      },
      "description": "Which workshop projects this prompt applies to"
    },
    "exampleOutput": {
      "type": "string",
      "description": "Sample of what a good AI response looks like"
    },
    "author": {
      "type": "string",
      "description": "GitHub username or full name"
    },
    "version": {
      "type": "string",
      "pattern": "^[0-9]+\\.[0-9]+\\.[0-9]+$",
      "description": "Semver version"
    },
    "createdAt": {
      "type": "string",
      "format": "date"
    },
    "updatedAt": {
      "type": "string",
      "format": "date"
    }
  }
}
```

**Example:**
```json
{
  "id": "debug-001",
  "title": "Error-First Debugging",
  "description": "Give AI an error and your code to get a specific, actionable fix.",
  "prompt": "I got this error:\n\n```\n{{ERROR_MESSAGE}}\n```\n\nHere is the code:\n\n```{{LANGUAGE}}\n{{CODE_BLOCK}}\n```\n\nExplain what caused this in plain English, then give me the corrected code.",
  "variables": [
    { "name": "ERROR_MESSAGE", "description": "Exact error message" },
    { "name": "LANGUAGE", "description": "js, html, css, python, etc." },
    { "name": "CODE_BLOCK", "description": "Code that produced the error" }
  ],
  "tags": ["debugging", "beginner", "error-handling"],
  "category": "debugging",
  "aiTools": ["claude", "cursor", "chatgpt"],
  "skillLevel": "beginner",
  "workshopProject": ["01", "02", "03", "04"],
  "author": "Krosebrook",
  "version": "1.0.0",
  "createdAt": "2026-03-01",
  "updatedAt": "2026-03-01"
}
```

---

### SponsorPackage

Used by the sponsorship management workflow (`docs/phase-4/revenue/sponsorship-packages.md`).

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "SponsorPackage",
  "description": "A sponsorship agreement with an AI/dev tool company",
  "type": "object",
  "required": ["id", "companyName", "tier", "cohort", "status", "agreedAt"],
  "properties": {
    "id": { "type": "string" },
    "companyName": { "type": "string" },
    "contactEmail": { "type": "string", "format": "email" },
    "tier": {
      "type": "string",
      "enum": ["bronze", "silver", "gold", "title"]
    },
    "cohort": {
      "type": "string",
      "description": "Cohort ID or 'all-YYYY' for annual title sponsors"
    },
    "amount": {
      "type": "number",
      "description": "Agreed sponsorship amount in USD"
    },
    "status": {
      "type": "string",
      "enum": ["prospecting", "negotiating", "agreed", "paid", "delivered", "complete", "declined"]
    },
    "benefits": {
      "type": "array",
      "items": { "type": "string" },
      "description": "List of agreed benefit deliverables"
    },
    "agreedAt": { "type": "string", "format": "date" },
    "paymentReceivedAt": { "type": "string", "format": "date" },
    "notes": { "type": "string" }
  }
}
```

---

### CurriculumLicensee

Used to track organizations that have licensed the workshop curriculum (`docs/phase-4/revenue/curriculum-licensing.md`).

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "CurriculumLicensee",
  "description": "An organization licensed to teach the Vibe Coding Workshop curriculum",
  "type": "object",
  "required": ["id", "organizationName", "contactEmail", "tier", "licenseStart", "status"],
  "properties": {
    "id": { "type": "string" },
    "organizationName": { "type": "string" },
    "organizationType": {
      "type": "string",
      "enum": ["bootcamp", "community-college", "university", "corporate", "non-profit", "maker-space", "other"]
    },
    "contactEmail": { "type": "string", "format": "email" },
    "city": { "type": "string" },
    "country": { "type": "string" },
    "tier": {
      "type": "string",
      "enum": ["starter", "growth", "enterprise", "non-profit"]
    },
    "annualFee": { "type": "number" },
    "licenseStart": { "type": "string", "format": "date" },
    "licenseEnd": { "type": "string", "format": "date" },
    "status": {
      "type": "string",
      "enum": ["prospect", "pilot", "active", "expired", "terminated"]
    },
    "cohortsDelivered": { "type": "integer", "minimum": 0 },
    "totalParticipants": { "type": "integer", "minimum": 0 },
    "averageNps": { "type": "number", "minimum": -100, "maximum": 100 },
    "notes": { "type": "string" }
  }
}
```

---

### CodeJamSubmission

Used for the annual Vibe Code Jam event (`docs/phase-4/community/code-jam.md`).

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "CodeJamSubmission",
  "description": "A project submission for the annual Vibe Code Jam",
  "type": "object",
  "required": ["id", "projectName", "liveUrl", "track", "submittedAt"],
  "properties": {
    "id": { "type": "string" },
    "year": { "type": "integer" },
    "projectName": { "type": "string", "maxLength": 80 },
    "description": { "type": "string", "maxLength": 280 },
    "liveUrl": { "type": "string", "format": "uri" },
    "githubUrl": { "type": "string", "format": "uri" },
    "track": {
      "type": "string",
      "enum": ["solo", "team", "first-timer", "remix"]
    },
    "teamMembers": {
      "type": "array",
      "items": { "type": "string" },
      "maxItems": 3
    },
    "aiToolsUsed": {
      "type": "array",
      "items": { "type": "string" }
    },
    "wouldYouUseThis": { "type": "boolean" },
    "submittedAt": { "type": "string", "format": "date-time" },
    "scores": {
      "type": "object",
      "properties": {
        "ships": { "type": "number", "minimum": 0, "maximum": 5 },
        "solvessomething": { "type": "number", "minimum": 0, "maximum": 5 },
        "vibe": { "type": "number", "minimum": 0, "maximum": 5 },
        "aiFirstApproach": { "type": "number", "minimum": 0, "maximum": 5 },
        "accessible": { "type": "number", "minimum": 0, "maximum": 5 }
      }
    }
  }
}
```

---

*These schemas serve as contracts between UI, backend, and AI tooling. Update when data structures change.*
