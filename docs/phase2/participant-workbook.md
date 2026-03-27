# Participant Workbook — Vibe Coding Workshop

> **Your name:** _______________________________  
> **Workshop date:** ___________________________  
> **Your laptop:** Mac / Windows (circle one)

---

## Welcome

You're here because you have an idea — something you've wanted to build but didn't know how. Today you're going to build 4 real apps and deploy them to live URLs.

You don't need to know how to code. You need to know how to describe what you want.

That's vibe coding.

---

## Today's Agenda

| Time | What's Happening |
|------|-----------------|
| 8:30 AM | Welcome + introductions |
| 9:00 AM | Learn the Scales: AI fundamentals and prompting |
| 10:45 AM | **Project 01:** Personal Landing Page |
| 12:00 PM | Lunch |
| 12:45 PM | **Project 02:** Mood Tracker with Charts |
| 2:15 PM | **Project 03:** Recipe Finder with API |
| 4:00 PM | **Project 04:** AI Chat Assistant |
| 5:30 PM | Ship It: Deploy all 4 projects |
| 6:15 PM | Show & Tell |
| 6:45 PM | Debrief + Closing |

---

## The Tools

| Tool | What It Does | Free? |
|------|-------------|-------|
| **Claude** | AI that writes and explains code | Yes (free tier) |
| **Cursor** | Code editor with AI built in | Yes (free tier) |
| **v0** | AI that generates UIs from text | Yes (free tier) |
| **Vercel** | Deploys your app to a live URL | Yes (free tier) |
| **Supabase** | Database for your app | Yes (free tier) |
| **GitHub** | Stores your code, connects to Vercel | Free |

---

## The Mental Model

Everything today follows this loop:

```
DESCRIBE → PROMPT → GET OUTPUT → TEST → REFINE → REPEAT
```

If something breaks: describe the error → prompt with the error → fix → test again.

The AI is not magic. It's a collaborator. Your job is to describe what you want clearly.

---

## Phase 1 Notes: AI Fundamentals

*Use this section during the morning session. Write down anything that clicks.*

### What is vibe coding?

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

### The 4 Prompt Patterns (fill in as Kyle explains each one)

**1. DESCRIBE-FIRST**

What it is: ___________________________________________________

Example from today: ___________________________________________

---

**2. ERROR-DEBUG**

What it is: ___________________________________________________

Example from today: ___________________________________________

---

**3. REFINE**

What it is: ___________________________________________________

Example from today: ___________________________________________

---

**4. ARCHITECTURE**

What it is: ___________________________________________________

Example from today: ___________________________________________

---

### My first prompt (write it here exactly as you typed it)

```
[your prompt here]
```

**What happened:**

_____________________________________________________________

**What I changed on the second try:**

_____________________________________________________________

---

### Things I want to remember from Phase 1

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

---

## Project 01 — Personal Landing Page

**Goal:** A single-page personal site with your name, bio, and links. Mobile-friendly. Deployed to a live URL.

---

### My idea for this project

What will my landing page say about me?

_____________________________________________________________

_____________________________________________________________

Links I want to include: _______________________________________

---

### My prompts (write down the prompts you used)

**Starting prompt:**

```
[write your prompt here]
```

**Refinement prompt 1:**

```
[write your refinement here]
```

**Refinement prompt 2:**

```
[write your refinement here]
```

---

### Errors I hit + how I fixed them

| Error | How I fixed it |
|-------|---------------|
| | |
| | |
| | |

---

### What I learned on Project 01

_____________________________________________________________

_____________________________________________________________

---

### Project 01 — Ship It ✅

- [ ] Page works in browser preview in Cursor
- [ ] Pushed to GitHub
- [ ] Deployed to Vercel
- [ ] Live URL works on my phone

**🚀 My Project 01 URL:** ___________________________________

---

## Project 02 — Mood Tracker with Charts

**Goal:** An app that logs your daily mood (1–5 scale) and shows a chart of mood over time. Data saved in local storage so it persists between visits.

---

### My idea for this project

What does my mood tracker need?
- [ ] Mood rating (1–5)
- [ ] Optional notes
- [ ] Chart (bar, line, or other)
- [ ] Other: _______________________________________________

---

### My prompts

**Starting prompt:**

```
[write your prompt here]
```

**Refinement prompt 1:**

```
[write your refinement here]
```

**The hardest part of this project:**

_____________________________________________________________

**How I solved it:**

_____________________________________________________________

---

### New things I learned on Project 02

| Concept | What it means |
|---------|--------------|
| Local storage | |
| State | |
| Chart library | |

---

### Project 02 — Ship It ✅

- [ ] Can log a mood entry (it appears on screen)
- [ ] Chart renders with at least one data point
- [ ] Data persists after page refresh
- [ ] Deployed to Vercel

**🚀 My Project 02 URL:** ___________________________________

---

## Project 03 — Recipe Finder with API

**Goal:** An app that takes an ingredient as input, calls a recipe API, and shows results with images and links.

---

### My idea for this project

What do I want my recipe finder to do?

_____________________________________________________________

API I'm using: **TheMealDB** (free, no key needed for basic search)

API endpoint: `https://www.themealdb.com/api/json/v1/1/filter.php?i=chicken`

---

### What is an API? (fill in after Kyle explains)

An API is: ___________________________________________________

_____________________________________________________________

---

### My prompts

**Starting prompt:**

```
[write your prompt here]
```

**The hardest thing about this project:**

_____________________________________________________________

**How I solved it:**

_____________________________________________________________

---

### Errors I hit + how I fixed them

| Error | What it meant | How I fixed it |
|-------|--------------|---------------|
| | | |
| | | |

---

### Project 03 — Ship It ✅

- [ ] Search input works
- [ ] Results display with images
- [ ] Links to full recipes work
- [ ] Error state shows if no results found
- [ ] Deployed to Vercel

**🚀 My Project 03 URL:** ___________________________________

---

## Project 04 — AI Chat Assistant

**Goal:** A chat interface connected to the Claude API. Type a message, get a response. Deployed with an API key stored securely in Vercel's environment variables.

---

### My idea for this project

What will my AI assistant do? (You can give it a persona, a specialty, a job)

_____________________________________________________________

_____________________________________________________________

My assistant's name: _________________________________________

My assistant's personality: ____________________________________

---

### My system prompt (this tells Claude how to behave)

```
You are [name], an AI assistant that [does what].
You always [behavior 1].
You never [behavior 2].
Your tone is [adjective].
```

---

### My prompts for building this project

**Starting prompt:**

```
[write your prompt here]
```

**Refinement prompt 1:**

```
[write your refinement here]
```

---

### Environment Variables Checklist

- [ ] Got Claude API key from `console.anthropic.com`
- [ ] Did NOT put the API key directly in my code
- [ ] Added `ANTHROPIC_API_KEY` to Vercel environment variables
- [ ] Verified the app works with the real API key

---

### Project 04 — Ship It ✅

- [ ] Chat interface renders correctly
- [ ] Can send a message and get a response from Claude
- [ ] System prompt is working (assistant has a personality)
- [ ] API key is in Vercel env vars, not in the code
- [ ] Deployed to Vercel

**🚀 My Project 04 URL:** ___________________________________

---

## The "Ship It" Checklist — All 4 Projects

Fill this in before Show & Tell.

| Project | Live URL | Works on Mobile? |
|---------|---------|-----------------|
| 01 — Personal Landing Page | | ☐ Yes  ☐ Not yet |
| 02 — Mood Tracker | | ☐ Yes  ☐ Not yet |
| 03 — Recipe Finder | | ☐ Yes  ☐ Not yet |
| 04 — AI Chat Assistant | | ☐ Yes  ☐ Not yet |

**My GitHub profile:** `github.com/` ____________________________

---

## Post-Workshop Resources

### Keep Building With These Tools

| Resource | URL |
|---------|-----|
| Claude | claude.ai |
| Cursor | cursor.com |
| v0 by Vercel | v0.dev |
| Vercel | vercel.com |
| Supabase | supabase.com |
| GitHub | github.com |
| TheMealDB API | themealdb.com/api.php |
| Anthropic Console | console.anthropic.com |

### Free Learning Resources

| Resource | What You'll Learn |
|---------|------------------|
| MDN Web Docs (developer.mozilla.org) | HTML, CSS, JavaScript reference |
| freeCodeCamp (freecodecamp.org) | Structured web development curriculum |
| The Odin Project (theodinproject.com) | Full-stack web development path |
| Anthropic Cookbook (github.com/anthropics/anthropic-cookbook) | Claude API examples |
| Vercel Docs (vercel.com/docs) | Deployment and environment variables |

### What to Build Next

Ideas from the room today:
_____________________________________________________________
_____________________________________________________________

My next project idea: ________________________________________
_____________________________________________________________

---

## Blank Notes — Page 1

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

---

## Blank Notes — Page 2

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

---

## Blank Notes — Page 3

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

---

*Vibe Coding Workshop · College of Lake County · Taught by Kyle Rosebrook*  
*Questions after today? Email hello@vibecodingworkshop.com*
