# Self-Paced Course Outline

> The async, on-demand version of the Vibe Coding Workshop — for people who can't make a live cohort but want the same transformation.

---

## Overview

The self-paced course delivers the core Vibe Coding Workshop as an on-demand product. Learners work through the material at their own pace, with pre-recorded video lessons, written guides, and hands-on projects they submit for async review.

**Audience:** Non-technical people who can't attend a live cohort due to schedule, geography, or preference for self-directed learning  
**Format:** Video + written guides + projects + community  
**Timeline:** Recommended 4–6 hours (one focused weekend day), but completable over 1–2 weeks  
**Outcome:** Same as live: 4 deployed apps, real prompting skills, portfolio of shipped work

---

## Why Self-Paced Works

Vibe coding is inherently self-directed — you're describing what you want to an AI, not following a syntax tutorial. The instruction is about mindset and strategy, not memorizing commands. That translates well to async because:

1. The "aha moment" comes from building, not from watching
2. Learners can pause, rewind, and re-prompt as much as they need
3. The community provides the social accountability that a live room provides

---

## Course Structure

### Module 0 — Before You Start (30 min)

**Goal:** Get set up and understand what you're about to do.

#### Lessons
- **0.1** — What this course is (and isn't)
- **0.2** — The tools you'll use: Claude, Cursor, Vercel
- **0.3** — Setting up your accounts (GitHub, Cursor, Claude, Vercel)
- **0.4** — How to use Cursor for the first time
- **0.5** — Your mission: describe your app idea in one sentence

#### Project 0
> "Open Cursor and ask Claude to build a page that says 'Hello, [your name].' Deploy it to Vercel. Paste the URL in the community Discord."

---

### Module 1 — Learn the Scales (60 min)

**Goal:** Understand how AI coding tools work and how to communicate with them effectively.

#### Lessons
- **1.1** — How AI models process your prompts
- **1.2** — Why "write me an app" doesn't work
- **1.3** — The Prompt → Output → Refine loop (video demo)
- **1.4** — Prompting for structure: Context, Instruction, Format, Constraints
- **1.5** — What hallucination is and how to handle it
- **1.6** — Reading code you didn't write

#### Exercises
- Write 3 different prompts for the same simple app. Note what changes.
- Find one error in AI-generated code and ask Claude to fix it.

---

### Module 2 — Project 01: Personal Landing Page (60 min)

**Goal:** Build and ship your first real web page.

#### Lessons
- **2.1** — Anatomy of a web page (HTML + CSS in 5 minutes)
- **2.2** — Using the T01 template prompt
- **2.3** — Iterating on design: colors, layout, fonts
- **2.4** — Deploying to Vercel (step-by-step walkthrough)

#### Project 01
Use the T01 template prompt from `docs/templates/`. Build a personal landing page with:
- Your name
- A 2–3 sentence bio
- 3 things you care about / want to build
- A way to contact you

**Deploy to Vercel and submit your URL.**

---

### Module 3 — Project 02: Mood Tracker (60 min)

**Goal:** Build an app that stores and visualizes data.

#### Lessons
- **3.1** — What JavaScript state means (the sticky note analogy)
- **3.2** — localStorage: saving data in the browser
- **3.3** — Data visualization basics: charts from a list of numbers
- **3.4** — Using the T02 template prompt
- **3.5** — Swapping the mood tracker for your own tracker idea

#### Project 02
Use the T02 template prompt. Build a tracker of your choice:
- Default: Mood Tracker (1–5 scale with daily chart)
- Your variation: Could be a habit tracker, water intake log, workout log, etc.

**Deploy and submit your URL.**

---

### Module 4 — Project 03: Recipe Finder with API (75 min)

**Goal:** Connect your app to external data.

#### Lessons
- **4.1** — What an API is (the restaurant analogy)
- **4.2** — Reading API documentation
- **4.3** — Fetch and async/await in one minute
- **4.4** — Error handling: what to do when the API fails
- **4.5** — Using the T03 template prompt

#### Project 03
Use the T03 template prompt. Build a search interface for an API of your choice:
- Default: Recipe Finder (TheMealDB API — no key required)
- Alternatives: Movie finder, Pokémon lookup, Weather app, Book finder

**Deploy and submit your URL.**

---

### Module 5 — Project 04: AI Chat Assistant (75 min)

**Goal:** Build an app powered by AI, with a custom personality.

#### Lessons
- **5.1** — How the Claude API works
- **5.2** — System prompts: giving your assistant a personality
- **5.3** — Setting up Claude API key safely (environment variables)
- **5.4** — Streaming responses for better UX
- **5.5** — Using the T04 template prompt

#### Project 04
Use the T04 template prompt. Build an AI assistant with a custom personality:
- Default: General-purpose helpful assistant
- Ideas: Recipe coach, journaling companion, study buddy, business idea sparring partner

**Deploy and submit your URL.**

---

### Module 6 — What's Next (30 min)

**Goal:** Know where to go from here.

#### Lessons
- **6.1** — What you built (and what it means)
- **6.2** — How to keep building after the course
- **6.3** — The post-workshop toolkit (guidebooks, Discord, templates)
- **6.4** — What Vibe Coding 2.0 covers next
- **6.5** — Sharing your work: portfolio vs. project vs. product

---

## Community Component

The async course works best with a community layer:

| Community Element | Purpose |
|-------------------|---------|
| Discord `#self-paced` channel | Ask questions, share projects, get unstuck |
| Weekly async AMA (Loom video) | Instructor answers top questions weekly |
| Project showcase thread | Share your 4 live URLs when you finish |
| Peer review pairs | Optional: pair with another self-paced learner for feedback |

---

## Completion Certificate

Participants who complete all 4 projects and submit live URLs receive:
- A digital completion certificate (PDF)
- Addition to the alumni Discord with the `self-paced` role
- Access to the Project Showcase Gallery

**Verification process:**
1. Submit all 4 live URLs in the Discord `#project-submissions` channel
2. Instructor or TA verifies each URL is live and matches the project
3. Certificate issued within 48 hours

---

## Course Production Notes

### Video Format
- Screen recording with instructor voice-over
- Target: 5–10 min per lesson (no lesson over 15 min)
- Captions for accessibility
- Show hands-on prompting in real time — don't cut the "bad" attempts

### Written Guides
- Each module has a companion written guide (markdown, exportable to PDF)
- Matches the Guidebook style in `docs/guidebooks/`
- Code examples use the same CSS design system as the main site

### Hosting Platform Options
- **Phase 3 v1:** Gumroad (digital product, low friction, no custom platform needed)
- **Phase 3 v2:** Participant portal (see [participant-portal-spec.md](./participant-portal-spec.md))
- **Phase 4:** LMS integration (Teachable, Maven, or custom)

### Pricing
- Self-paced course: $97–$197 one-time
- Bundle with live cohort alumni access: $247
- Corporate license (unlimited employees, 1 year): See [corporate-training-guide.md](./corporate-training-guide.md)

---

## Content Reuse Matrix

| Asset | Live Workshop | Self-Paced Course |
|-------|--------------|-------------------|
| Project templates (T01–T04) | ✅ Same | ✅ Same |
| Prompting playbook | ✅ Printed | ✅ PDF download |
| Guidebooks | ✅ Reference | ✅ Module companions |
| Instructor demos | ✅ Live | ✅ Pre-recorded |
| Discord community | ✅ Alumni | ✅ `#self-paced` channel |

---

*Owner: Kyle Rosebrook · Part of [Phase 3 documentation](./README.md)*
