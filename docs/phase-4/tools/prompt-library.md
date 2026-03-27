# Prompt Library — Searchable Prompt Web App

> A curated, searchable, community-maintained library of prompts for AI-assisted development. Tag, search, copy, and contribute.

---

## What Is the Prompt Library?

The Prompt Library is a lightweight web app that lets anyone browse and search hundreds of battle-tested prompts for building with AI. Every prompt is tagged by category, AI tool, skill level, and use case. No account required to search or copy. Contribute via GitHub.

**Live URL (planned):** [prompts.vibecodingworkshop.com](https://prompts.vibecodingworkshop.com)

---

## Core Features

### v1.0 (Launch)

| Feature | Description |
|---------|-------------|
| Search | Full-text search across prompt title, body, and tags |
| Filter | Filter by category, AI tool, skill level, use case |
| Copy | One-click copy to clipboard |
| Browse | Card-based browsing with pagination |
| Contribute | Link to GitHub for PR-based contributions |
| Static | No backend, no login, 100% static site |

### v2.0 (Post-Launch)

| Feature | Description |
|---------|-------------|
| Favorites | Save prompts locally (localStorage) |
| Collections | Curated thematic collections (e.g., "The Debugging Toolkit") |
| AI Tool Switcher | See the same prompt adapted for Claude vs. GPT-4 vs. Gemini |
| Community Votes | Upvote prompts (anonymous, no account) |
| Embed | Shareable links that deep-link to a single prompt |

---

## Prompt Schema

Each prompt is stored as a JSON file in `docs/phase-4/tools/prompts/`:

```json
{
  "$schema": "../../../schemas/prompt.schema.json",
  "id": "debug-001",
  "title": "Error-First Debugging",
  "description": "Give AI an error and your code to get a specific, actionable fix.",
  "prompt": "I got this error:\n\n```\n{{ERROR_MESSAGE}}\n```\n\nHere is the code that caused it:\n\n```{{LANGUAGE}}\n{{CODE_BLOCK}}\n```\n\nExplain what caused this error in plain English, then give me the corrected code with a comment explaining what changed.",
  "variables": [
    { "name": "ERROR_MESSAGE", "description": "Paste the exact error message" },
    { "name": "LANGUAGE", "description": "Language (js, html, css, python, etc.)" },
    { "name": "CODE_BLOCK", "description": "Paste the code that produced the error" }
  ],
  "tags": ["debugging", "beginner", "error-handling"],
  "category": "debugging",
  "aiTools": ["claude", "cursor", "chatgpt", "gemini"],
  "skillLevel": "beginner",
  "workshopProject": ["01", "02", "03", "04"],
  "exampleOutput": "The error `TypeError: Cannot read properties of undefined (reading 'map')` means...",
  "author": "Kyle Rosebrook",
  "version": "1.0.0",
  "createdAt": "2026-03-01",
  "updatedAt": "2026-03-01"
}
```

---

## Prompt Categories

| Category | Description | Prompt Count (planned) |
|----------|-------------|----------------------|
| `debugging` | Fix errors and unexpected behavior | 20 |
| `scaffolding` | Generate project structure and boilerplate | 15 |
| `ui-generation` | Build UI components from descriptions | 25 |
| `api-integration` | Connect to external APIs | 15 |
| `accessibility` | Add or fix ARIA, keyboard nav, contrast | 10 |
| `seo` | Add meta tags, OG tags, structured data | 10 |
| `deployment` | Prepare for and troubleshoot deployment | 10 |
| `refactoring` | Improve code clarity, reduce duplication | 15 |
| `documentation` | Write README, comments, JSDoc | 15 |
| `prompting` | Meta-prompts for improving your own prompts | 10 |
| `security` | Identify and fix common security issues | 10 |
| `performance` | Improve load time and rendering | 10 |

**Total planned:** 165 prompts at launch

---

## Starter Prompt Pack (v1.0)

These 25 prompts ship at launch, drawn from the workshop skills library:

| ID | Title | Category | Skill Level |
|----|-------|----------|-------------|
| `debug-001` | Error-First Debugging | debugging | beginner |
| `debug-002` | Console.log Strategy | debugging | beginner |
| `debug-003` | Rubber Duck Prompt | debugging | beginner |
| `scaffold-001` | Describe-First Development | scaffolding | beginner |
| `scaffold-002` | One-File HTML App Starter | scaffolding | beginner |
| `scaffold-003` | Project README Generator | scaffolding | beginner |
| `ui-001` | Hero Section Generator | ui-generation | beginner |
| `ui-002` | Card Grid Layout | ui-generation | beginner |
| `ui-003` | Navigation Bar Generator | ui-generation | beginner |
| `ui-004` | Form Component | ui-generation | beginner |
| `ui-005` | Dark Theme System | ui-generation | beginner |
| `api-001` | Basic Fetch Request | api-integration | intermediate |
| `api-002` | Error Handling for APIs | api-integration | intermediate |
| `api-003` | Loading State Pattern | api-integration | intermediate |
| `a11y-001` | Add ARIA Labels | accessibility | beginner |
| `a11y-002` | Keyboard Navigation Audit | accessibility | beginner |
| `seo-001` | Meta Tags Pack | seo | beginner |
| `seo-002` | Open Graph Tags | seo | beginner |
| `deploy-001` | Vercel Deploy Checklist | deployment | beginner |
| `refactor-001` | Extract to Function | refactoring | intermediate |
| `docs-001` | Write a README | documentation | beginner |
| `docs-002` | Add Code Comments | documentation | beginner |
| `prompt-001` | Refine a Vague Prompt | prompting | beginner |
| `prompt-002` | Add Constraints to a Prompt | prompting | beginner |
| `security-001` | Input Sanitization Check | security | intermediate |

---

## Technology Stack (Web App)

| Layer | Choice | Rationale |
|-------|--------|-----------|
| Framework | Vanilla HTML + CSS + JS | Zero dependencies, workshop-aligned |
| Data | Static JSON files | No backend, version-controlled |
| Search | [Lunr.js](https://lunrjs.com/) or client-side filter | Simple, no server needed |
| Hosting | GitHub Pages or Vercel | Free, CI/CD via GitHub Actions |
| Build | None required (v1) | Static files served directly |

---

## Site Structure

```
prompts.vibecodingworkshop.com/
├── /                  ← Browse all prompts (paginated cards)
├── /search            ← Search results page
├── /category/[name]   ← Category filter page
├── /prompt/[id]       ← Single prompt detail page (shareable)
└── /contribute        ← How to contribute a prompt
```

---

## Contribution Process

Anyone can contribute a prompt:

1. Fork the repository
2. Copy `docs/phase-4/tools/prompts/_template.json`
3. Fill in all required fields
4. Add your prompt JSON to `docs/phase-4/tools/prompts/[category]/`
5. Open a PR with title: `prompt: Add [title]`
6. PR checklist:
   - [ ] All required schema fields filled
   - [ ] Prompt tested with at least one AI tool
   - [ ] Tags match existing taxonomy
   - [ ] No profanity, PII, or proprietary content

**Review criteria:**
- Does the prompt produce consistently useful output?
- Is it clear what variables to replace?
- Does it match the category and tags?
- Is the skill level accurate?

---

## Governance

- **Maintainer:** Kyle Rosebrook (`@Krosebrook`)
- **License:** Prompts are CC BY 4.0 — share and adapt with attribution
- **Review SLA:** PRs reviewed within 7 days
- **Versioning:** Each prompt has its own version. Breaking changes (variable renames) bump major version.

---

*See also: [Vibe Starter](vibe-starter.md) | [AI Tool Comparison](ai-tool-comparison.md) | [Phase 4 Overview](../README.md)*
