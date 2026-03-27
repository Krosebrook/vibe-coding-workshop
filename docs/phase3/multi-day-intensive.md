# Multi-Day Intensive Format

> The 2-day expanded workshop — more projects, more depth, more time to build something real.

---

## Overview

The Multi-Day Intensive takes the one-day workshop and stretches it into two full days. Day 1 is the original curriculum. Day 2 introduces backend concepts (Supabase, authentication, AI APIs with more power) and culminates in each participant shipping a more ambitious project — often their actual app idea.

**Audience:** Participants who've done the original workshop (or have equivalent exposure) and want to go deeper.  
**Capacity:** 15–20 participants  
**Format:** In-person preferred, virtual possible  
**Outcome:** Each participant ships a full-stack or AI-enhanced app with real data persistence

---

## Why Two Days?

One day is enough to learn the fundamentals and build four proof-of-concept apps. But almost every participant leaves with a bigger idea that they couldn't finish. Two days lets them:

1. Consolidate Day 1 skills — the concepts "land" differently on Day 2 morning
2. Add a real database — Supabase makes this accessible
3. Ship something they'll actually keep using
4. Get unstuck on their real idea with expert support

---

## Day 1 — The Foundation

Day 1 is identical to the standard one-day workshop. See [docs/playbooks/README.md — PB01](../playbooks/README.md#pb01---workshop-day-playbook) for the full playbook.

**Projects:**
1. Personal Landing Page
2. Mood Tracker with Charts
3. Recipe Finder with API
4. AI Chat Assistant

**Day 1 Closing Addition (7:30 – 8:00 PM)**

Add a 30-minute "What do you want to build tomorrow?" session:
- Each participant writes their Day 2 project idea (one paragraph)
- Instructor reviews and provides a starting prompt for everyone
- Distribute the Day 2 Project Brief template (see below)
- Share a Supabase quickstart guide as pre-reading

---

## Day 2 — Go Deeper

Day 2 shifts from guided building to supported independent building, with instructor-led sessions on new concepts.

### Day 2 Schedule

#### 9:00 AM — Warm-Up: Yesterday's Wins (30 min)

- Quick round: one thing from yesterday that clicked
- Common follow-up questions from Day 1 (address the top 3)
- Today's goal: ship your real project

---

#### 9:30 AM — Databases 101 with Supabase (60 min)

**Concepts (no code yet):**
- What a database is — the spreadsheet analogy
- Rows, columns, tables, relationships
- Real-time vs. request/response
- Why you need a database (persistence, sharing, auth)

**Live Demo (30 min):**
1. Create a Supabase project from scratch
2. Create a `tasks` table with title, done, created_at
3. Insert rows from the Supabase dashboard
4. Connect it to a simple HTML page via the JavaScript client

**Participants follow along** with their own Supabase project.

---

#### 10:30 AM — Authentication with Supabase Auth (45 min)

**Concepts:**
- Why auth matters even for simple projects
- Sessions, tokens, and what "logged in" means
- Email + password vs. magic link vs. OAuth

**Live Demo (30 min):**
1. Enable Supabase Auth in the same project
2. Build a simple login form using the Supabase JS client
3. Show how the UI changes when a user is logged in
4. Show how to restrict database access to authenticated users (Row Level Security)

---

#### 11:15 AM — Break (15 min)

---

#### 11:30 AM — Advanced AI: Going Beyond Claude in the Browser (45 min)

**Topics:**
- Using the Claude API (vs. claude.ai)
- System prompts: giving your AI assistant a personality and constraints
- Streaming responses for a better UX
- Tool use basics: giving your AI access to your database

**Live Demo:**
1. Make a raw Claude API call via fetch
2. Show streaming in action
3. Build a simple AI assistant that can read from a Supabase table

---

#### 12:15 PM — Lunch + Project Planning (60 min)

During lunch, participants refine their Day 2 project idea:
- Review the prompt the instructor drafted last night
- Identify the 3 core features (MVP only)
- Write the first Cursor prompt

**Instructor circulates** to help finalize project scopes. Key message: "Smaller than you think. You can always add more."

---

#### 1:15 PM — Build Your Real Project (2.5 hours)

**Unstructured build time.** Instructor and any TAs circulate and support.

Participants work on their personal Day 2 project — the actual app idea they came with. This is the moment the workshop was building toward.

**Common Day 2 projects:**
- Habit tracker with Supabase persistence
- Simple inventory management tool for a small business
- Personal knowledge base / bookmarks manager
- AI assistant with memory (stores past conversations)
- Landing page with a working waitlist form (Supabase + email)

**Instructor check-ins every 30 min:**
- "What are you building? What's the next thing?"
- "Is your AI giving you what you need? Show me the prompt."
- "What's blocking you?"

---

#### 3:45 PM — Final Push + Deploy (45 min)

- Everyone moves to ship mode
- Deploy to Vercel (same process as Day 1)
- Instructor helps unblock deployment issues

**Instructor script:**
> "It doesn't have to be perfect. It has to be live. A real URL is worth more than a perfect mock."

---

#### 4:30 PM — Demo Day (45 min)

**Each participant demos their Day 2 project to the group.**

Format:
- 3 minutes per person
- Show the live URL
- "What does it do? Who is it for? What would you add next?"
- Applause after each demo

**This is the most powerful moment of the 2-day experience.** People who said they could never build an app are showing off something real that they made in one afternoon.

---

#### 5:15 PM — Closing (45 min)

- Post-workshop resources
- What Vibe Coding 2.0 covers next (if applicable)
- Alumni Discord / community
- "What do you build next?" each person answers one sentence
- Group photo + celebration

---

## Day 2 Project Brief Template

Distribute this at the end of Day 1:

```
My Day 2 Project:
Name: ___________________________
Who it's for: ___________________________
What it does in one sentence: ___________________________
The 3 features I'll build: 
  1. ___________________________
  2. ___________________________
  3. ___________________________
Does it need a database? Yes / No
Does it need login? Yes / No
My first Cursor prompt: ___________________________
```

---

## Instructor Notes: What's Different on Day 2

1. **Energy is different.** Participants are more confident but also more frustrated — they have bigger ideas. Normalize the gap between vision and Day 2 output.

2. **Scope creep is real.** Help participants cut scope aggressively. A small shipped thing beats a large unshipped thing every time.

3. **Pair programming emerges naturally.** Let it. Participants helping each other is a feature.

4. **The Supabase section is the hardest part.** Database concepts are genuinely new for most participants. Go slow. Use the spreadsheet analogy repeatedly.

5. **Demo Day is sacred.** Do not cut it for time. Even if projects are incomplete, everyone demos what they have.

---

## Logistics: 2-Day Format

### Venue
- Same room as Day 1 if possible — participants already know the space
- If different venue: run the same morning setup checklist (PB01)

### Catering
- Provide lunch both days if budget allows — it keeps energy up
- Coffee and snacks in the room throughout

### Materials
- Day 2 Project Brief (print 1 per participant; hand out end of Day 1)
- Supabase quickstart card (print 1 per participant)
- Same printed checklists as Day 1

---

*Owner: Kyle Rosebrook · Part of [Phase 3 documentation](./README.md)*
