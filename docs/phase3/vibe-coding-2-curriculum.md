# Vibe Coding 2.0 Curriculum

> The advanced workshop for alumni who've shipped their first apps and want to go deeper — backends, databases, authentication, and real-world deployment patterns.

---

## Overview

**Vibe Coding 2.0** is the follow-up to the original one-day workshop. It's designed for people who've completed Vibe Coding 1.0 and want to build apps that:

- Persist data (not just in-browser state)
- Support real user accounts (authentication)
- Talk to their own APIs (not just third-party ones)
- Scale beyond a single HTML file

**Audience:** Vibe Coding 1.0 alumni (or equivalent experience: can ship a simple front-end app with Claude)  
**Format:** 2-day in-person intensive or 4-week live cohort (2 sessions/week)  
**Outcome:** Each participant ships a full-stack app with auth, a database, and a real API

---

## Prerequisites

Participants should be comfortable with:

- Building and deploying front-end apps using Claude and Cursor
- The Prompt → Output → Refine loop
- Basic HTML, CSS, and enough JavaScript to read it (not write it from scratch)
- Git + GitHub (pushing code, basic branches)

If they haven't done Vibe Coding 1.0, they should complete the self-paced course first.

---

## Curriculum Overview

### Module 1 — The Backend Mental Model (2 hours)

**Goal:** Understand why a backend exists and what it does.

#### Topics
1. What a server is (and isn't)
2. Request → Response: how the web actually works
3. REST APIs: what you've been using, now you'll build one
4. Serverless vs. traditional servers — why serverless is perfect for vibecoders
5. Environment variables: secrets that don't end up in GitHub

#### Live Demo
Build a simple "Hello World" serverless function with Vercel Functions and call it from a front-end fetch.

#### Hands-On
Participants build a serverless function that returns a random quote from a hardcoded list. They call it from their Day 1 portfolio page.

---

### Module 2 — Databases with Supabase (4 hours)

**Goal:** Store and retrieve data that persists.

#### Topics
1. Relational databases: tables, rows, columns
2. The spreadsheet analogy — really understanding it
3. SQL basics: SELECT, INSERT, UPDATE, DELETE (Claude writes the SQL, you understand it)
4. Supabase: the managed Postgres platform that vibecoders can use
5. The Supabase JavaScript client
6. Real-time subscriptions: when data changes, the UI updates

#### Live Demos
1. Create a Supabase project and table from scratch
2. Build a tasks app that saves to Supabase (replaces localStorage)
3. Show real-time: two browser tabs, one saves, the other updates instantly

#### Project: Persistent Task Manager
Build a task manager that:
- Saves tasks to Supabase
- Shows tasks across browser sessions and devices
- Has basic filtering (done / not done)
- Updates in real time when another tab adds a task

---

### Module 3 — Authentication (3 hours)

**Goal:** Build apps with real user accounts.

#### Topics
1. What authentication is — the nightclub analogy
2. Sessions and tokens — how "staying logged in" works
3. Supabase Auth: email + password, magic link, OAuth (GitHub, Google)
4. Row Level Security: how each user only sees their own data
5. Auth UI patterns: login form, redirect after login, protected pages

#### Live Demo
Add auth to the tasks app from Module 2:
- Login with email + magic link
- Each user sees only their own tasks
- Row Level Security policy in Supabase

#### Project: Personal Dashboard
Build a personal dashboard that:
- Requires login
- Shows data specific to the logged-in user
- Has at least one "private" resource (tasks, notes, bookmarks, etc.)
- Can be shared: "login to see your data"

---

### Module 4 — Building Your Own API (3 hours)

**Goal:** Stop consuming APIs and start building them.

#### Topics
1. What a REST API is (and why you'd build one)
2. API routes in Next.js / Vercel Functions
3. Request methods: GET, POST, PUT, DELETE
4. Input validation: don't trust what comes in
5. Error handling: return useful errors, not 500s
6. CORS: why your browser is blocking your request

#### Live Demo
Build an API for the Personal Dashboard:
- `GET /api/tasks` — return all tasks for the logged-in user
- `POST /api/tasks` — create a new task
- `DELETE /api/tasks/[id]` — delete a task

#### Project Extension
Connect the Personal Dashboard to your new API instead of calling Supabase directly from the front end.

---

### Module 5 — AI Integration (Deeper) (3 hours)

**Goal:** Build AI features that go beyond a chat box.

#### Topics
1. The Claude API: beyond claude.ai, beyond the browser
2. Tool use: giving Claude the ability to call your API
3. Structured outputs: getting JSON back, not just text
4. Agents: what they are and a simple example
5. Streaming: why it matters for UX
6. Cost and rate limits: building responsibly

#### Live Demo
Build an AI assistant that:
- Has access to the user's task list (via tool use)
- Can add tasks when the user asks
- Returns structured data (not just a message)
- Streams the response

#### Project: Smart Personal Dashboard
Upgrade the Personal Dashboard:
- Add an AI assistant that can read and write your data
- Add one AI-powered feature: smart categorization, natural language search, or a daily summary

---

### Module 6 — Ship It for Real (2 hours)

**Goal:** Deploy with production best practices.

#### Topics
1. Environment variables in production (not `.env.local`)
2. Vercel deployment config: preview vs. production
3. Custom domains: pointing your domain to Vercel
4. Basic monitoring: uptime checks, error tracking (Sentry free tier)
5. Database backups in Supabase
6. What "production-ready" actually means for a vibe-coded MVP

#### Final Project: Deploy Your Real App
Participants deploy their full-stack app from this workshop to a custom domain (or vibecodingworkshop.com subdomain as a fallback). They present it in a 3-minute demo to the group.

---

## Project Summary

By the end of Vibe Coding 2.0, each participant has shipped:

| Project | What it demonstrates |
|---------|---------------------|
| Serverless function | Backend fundamentals |
| Persistent Task Manager | Supabase database |
| Personal Dashboard | Auth + Row Level Security |
| Smart Personal Dashboard | Full-stack + AI integration |
| Final personal app | Their real idea, with everything combined |

---

## Teaching Approach: What's Different in 2.0

### More Autonomy, Less Scaffolding
2.0 participants already know how to use Claude. The templates are starting points, not guardrails. Encourage deviation.

### Reading the Code
2.0 spends more time reading and understanding AI-generated code than 1.0. Participants need to be able to debug things that Claude gets wrong. Not write it — but read it.

### The "Why" Matters More
In 1.0, "it works" is enough. In 2.0, participants should understand why something works — enough to debug it and describe the problem to Claude accurately.

### Real Problems Welcome
Many 2.0 participants come with a real app idea they've been thinking about since 1.0. Route them toward building that in the free-build modules. The projects above are defaults for participants without a specific idea.

---

## Format Options

### Option A: 2-Day In-Person Intensive
- Day 1: Modules 1–3 (backend, database, auth)
- Day 2: Modules 4–6 (API, AI integration, production deploy)
- Capacity: 15–20 participants
- Same venue format as the multi-day intensive

### Option B: 4-Week Live Cohort (Online)
- Week 1: Modules 1–2 (2 × 90-min sessions)
- Week 2: Module 3 (2 × 90-min sessions)
- Week 3: Modules 4–5 (2 × 90-min sessions)
- Week 4: Module 6 + final demos (2 × 90-min sessions)
- Capacity: 20–30 participants
- Async work between sessions (1–2 hours/week)

### Option C: Self-Paced (Future Phase 4)
Pre-recorded version of Option B. Add to the self-paced course platform.

---

## Pricing

| Format | Suggested Price | Alumni Discount |
|--------|----------------|----------------|
| 2-Day In-Person | $497–$597 | $50 off |
| 4-Week Live Cohort | $297–$397 | $50 off |
| Self-Paced (Phase 4) | $147–$197 | $30 off |

---

## Prerequisites Checklist (Send to Enrollees)

Before attending Vibe Coding 2.0, participants should be able to:

- [ ] Build a simple HTML/CSS/JS page from a Claude prompt
- [ ] Deploy a project to Vercel
- [ ] Use GitHub (commit, push, open a repo)
- [ ] Read a JavaScript file and understand what it generally does (not write it)
- [ ] Describe a project idea in one paragraph

If they can't check all of these, recommend the self-paced Vibe Coding 1.0 course first.

---

*Owner: Kyle Rosebrook · Part of [Phase 3 documentation](./README.md)*
