# Project Showcase Gallery

> How alumni projects are collected, featured, and maintained — the social proof engine for the Vibe Coding Workshop.

---

## Overview

The Project Showcase Gallery is a public (or semi-public) collection of real apps built by Vibe Coding Workshop alumni. It serves multiple purposes:

1. **Social proof** — shows prospective participants what's possible
2. **Alumni pride** — gives graduates a place to show what they built
3. **Community** — connects alumni around their work
4. **Inspiration** — shows diverse project types and ideas

**Phase 3 goal:** Launch a showcase with at least 20 featured projects from the first two cohorts by the end of 2026.

---

## Gallery Structure

### Public Gallery (Marketing Site)

A section on the main marketing site (or a dedicated `/showcase` page) showing:

- Project cards with screenshot/preview, project name, creator name, and live URL
- Filter by: cohort, project type, technology
- Link to full participant portal for "see all alumni projects"

### Full Gallery (Participant Portal)

The complete showcase inside the participant portal, showing:

- All submitted projects with opt-in public visibility
- Participant profile links
- Cohort tags
- Search by project type or keyword

---

## Consent & Privacy

Every participant must explicitly opt in to showcase visibility. Defaults are private.

### Consent Framework

| Field | Visibility | Default |
|-------|-----------|---------|
| Live project URL | Public (if opted in) | Private |
| Project description | Public (if opted in) | Private |
| First name + last initial | Public (if opted in) | Private |
| Full name | Public (if opted in) | Private |
| GitHub username | Public (if opted in) | Private |
| Photo/screenshot of project | Public (if opted in) | Private |
| Cohort name | Public (if opted in) | Private |

**Collection point:** Project submission form in the participant portal includes a checkbox:
> "✅ I'd like my project featured in the public Vibe Coding Workshop showcase."

Consent can be withdrawn at any time — the entry is removed within 48 hours.

---

## Project Submission Flow

1. Participant logs into the portal
2. Navigates to `/dashboard/submit`
3. Fills out submission form:
   - Project number (1–4)
   - Project name (what they call it)
   - Live URL
   - 1–3 sentence description
   - Screenshot (optional — system also auto-generates a screenshot via URL screenshot API)
   - Showcase consent checkbox
4. Submits
5. Project appears in "My Projects" immediately
6. If consent given: appears in showcase after review (see below)

---

## Curation & Review

### Review Criteria

Projects are approved for the showcase if:

- [ ] Live URL works (not 404 or broken)
- [ ] Project is clearly something the participant built (not a tutorial copy)
- [ ] No harmful, offensive, or inappropriate content
- [ ] Participant consent is on record

### Review Process

1. New submissions with showcase consent flagged in admin portal
2. Admin (Kyle or TA) reviews within 72 hours
3. Approve → shows in showcase
4. Decline → email to participant: "Your project didn't meet our guidelines for the showcase. Here's why: [reason]. You can resubmit after [action]."

**Review is lightweight** — most projects pass. The goal is to catch broken links and anything obviously problematic.

---

## Featured Projects (Curated Selection)

Beyond the full gallery, maintain a curated "Featured Projects" section of 6–10 exceptional builds for the marketing site. Criteria:

- **Surprising:** Not the obvious app (not another todo list)
- **Real:** Something the person will actually use or has shared with others
- **Diverse:** Range of domains (health, finance, creative, productivity), not just tech
- **Good story:** Participant can say "I built this because..."

To request a feature slot, contact participants directly:

> "Hey [Name] — your [Project X] is one of the most creative things I've seen come out of a workshop. Would you be comfortable being featured on the main site? I'd use just your first name and a screenshot of the live app."

---

## Data Model

### ShowcaseProject

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "ShowcaseProject",
  "description": "A participant project approved for public showcase",
  "type": "object",
  "required": ["id", "participantId", "projectName", "liveUrl", "projectNumber", "cohortId", "consentGiven", "status"],
  "properties": {
    "id": { "type": "string" },
    "participantId": { "type": "string", "description": "References profiles.id" },
    "projectNumber": {
      "type": "integer",
      "minimum": 1,
      "maximum": 4,
      "description": "Which workshop project (1–4)"
    },
    "projectName": { "type": "string" },
    "liveUrl": { "type": "string", "format": "uri" },
    "description": {
      "type": "string",
      "maxLength": 280,
      "description": "Participant-written 1–3 sentence description"
    },
    "screenshotUrl": { "type": "string", "format": "uri" },
    "cohortId": { "type": "string", "description": "e.g., 'summer-2026-01'" },
    "displayName": {
      "type": "string",
      "description": "How participant wants to be credited: 'First name only', 'Full name', 'Anonymous'"
    },
    "githubUrl": { "type": "string", "format": "uri" },
    "tags": {
      "type": "array",
      "items": { "type": "string" },
      "description": "Category tags, e.g., ['productivity', 'AI', 'health']"
    },
    "consentGiven": { "type": "boolean" },
    "consentWithdrawnAt": { "type": "string", "format": "date-time" },
    "isFeatured": { "type": "boolean", "default": false },
    "status": {
      "type": "string",
      "enum": ["pending", "approved", "declined", "withdrawn"]
    },
    "reviewedAt": { "type": "string", "format": "date-time" },
    "submittedAt": { "type": "string", "format": "date-time" }
  }
}
```

---

## Marketing Site Integration

### Showcase Section on `index.html`

Add a "What alumni built" section to the marketing site. Static HTML implementation:

- Show 6 featured project cards (manually curated)
- Each card: project screenshot, project name, creator first name, domain tag
- Link to the full showcase in the portal
- "See what the next cohort builds →" CTA to the waitlist

**Update cadence:** After each cohort, update the static section with new featured projects. No dynamic loading on the marketing site (stays JS-free).

### Sample Card Structure

```html
<div class="showcase-card">
  <img src="[screenshot-url]" alt="[project-name]" loading="lazy" />
  <div class="showcase-card-body">
    <span class="showcase-tag">[domain tag]</span>
    <h3>[Project Name]</h3>
    <p>[1-2 sentence description]</p>
    <span class="showcase-credit">Built by [First Name] · [Cohort]</span>
  </div>
</div>
```

---

## Screenshots

### Auto-Generation

Use a URL screenshot API to automatically capture project screenshots on submission:

**Option A: Microlink** — `https://api.microlink.io/?url=[project-url]&screenshot=true`  
**Option B: ScreenshotOne** — Paid, higher quality, more control  
**Option C: Manual** — Instructor takes screenshots during Ship It ceremony

**Phase 3 v1 recommendation:** Manual screenshots during Ship It (zero infrastructure). Automate in v2.

---

## Launch Checklist

- [ ] Project submission form live in participant portal
- [ ] Consent checkbox added with clear language
- [ ] Review workflow: admin notification on new showcase submission
- [ ] Showcase gallery page in portal (`/dashboard/showcase`)
- [ ] 6-card static featured section added to `index.html`
- [ ] Consent withdrawal process documented and working
- [ ] 20+ approved projects in the gallery before marketing the showcase

---

*Owner: Kyle Rosebrook · Part of [Phase 3 documentation](./README.md)*
