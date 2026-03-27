# Prompting Playbook

> A standalone reference for writing effective prompts with AI tools. Designed for the Vibe Coding Workshop — but useful every day after.

---

## Why Prompting Is a Skill

The AI doesn't know what you want. You have to tell it.

The difference between "write me a website" and a prompt that produces exactly what you imagined is the same difference between a rough sketch and a detailed blueprint. Both describe a building. One is a lot easier to build from.

This playbook gives you four patterns that cover 95% of what you'll do in the workshop — and in every project you build after.

---

## Core Principles

### 1. Context first, request second

Bad:
```
Make a dark background.
```

Good:
```
I'm building a personal landing page. It's a single HTML file with no frameworks.
Make the background color #0a0a0a (very dark gray, not pure black).
```

The more context you give, the more accurate the output.

---

### 2. Describe the output format

Bad:
```
Add a chart.
```

Good:
```
Add a bar chart using only vanilla JavaScript — no external libraries.
The chart should use a <canvas> element.
Each bar represents one day. The height represents a mood score from 1–5.
Use the color #7c3aed for the bars.
```

---

### 3. Give constraints

Constraints prevent the AI from over-engineering your request.

Bad:
```
Make the form look nice.
```

Good:
```
Style this form. Constraints:
- No CSS frameworks (no Bootstrap, no Tailwind)
- Inline styles only (no separate CSS file)
- Dark theme: background #111111, text #e8e8e8, accent color #7c3aed
- Mobile-friendly
```

---

### 4. Iterate, don't restart

When the output isn't right, refine it — don't start over.

```
That's close. Change the font size to 18px and add 24px of padding around the button.
Keep everything else the same.
```

The "keep everything else the same" instruction is important. Without it, the AI may change things you liked.

---

## The 4 Prompt Patterns

---

### Pattern 1: DESCRIBE-FIRST

**When to use it:** Starting a new feature or component from scratch.

**Structure:**
```
[Context: what you're building]
[Request: what you want]
[Output format: what kind of file/code]
[Constraints: what NOT to do]
```

**Template:**
```
I'm building [what you're building].
[Current state: what already exists]

Create [what you want] that:
- [Requirement 1]
- [Requirement 2]
- [Requirement 3]

Output: [one HTML file / vanilla JS / React component / etc.]
Constraints: [No frameworks / inline styles only / etc.]
```

**Workshop Project 01 — Landing Page Example:**
```
I'm building a personal landing page. It's a single HTML file with no build tools and no JavaScript.

Create a hero section that includes:
- My name "Alex Chen" in large text (at least 48px)
- A subtitle: "Product Designer & Builder"
- Two buttons: "See My Work" (links to #projects) and "Contact Me" (links to mailto:)
- A professional, modern aesthetic

Design: dark background #0a0a0a, text #e8e8e8, accent color #7c3aed (purple)
Output: just the HTML for the section — I'll add it to my existing file
Constraints: no JavaScript, no CSS frameworks, inline styles only
```

---

### Pattern 2: ERROR-DEBUG

**When to use it:** Something is broken and you don't know why.

**Structure:**
```
[What you were trying to do]
[The error message, exactly as it appears]
[Relevant code]
[Request: explain the bug and fix it]
```

**Template:**
```
I'm working on [what you're building].

I got this error:
---
[paste the exact error message here]
---

Here's the relevant code:
---
[paste the code here]
---

What's causing this error? How do I fix it?
```

**Example:**
```
I'm building a Recipe Finder that calls the TheMealDB API.

I got this error in the browser console:
---
Access to fetch at 'https://www.themealdb.com/api/json/...' from origin 'null' has been
blocked by CORS policy: No 'Access-Control-Allow-Origin' header is present on the
requested resource.
---

Here's my fetch call:
---
fetch('https://www.themealdb.com/api/json/v1/1/filter.php?i=' + ingredient)
  .then(res => res.json())
  .then(data => console.log(data));
---

What's causing this error? How do I fix it? I'm running the file directly from my file system (not a server).
```

---

### Pattern 3: REFINE

**When to use it:** You have working code and want to improve or extend it.

**Structure:**
```
[Here's what I have and what it does]
[Make this one specific change]
[Keep everything else the same]
```

**Template:**
```
I have this [component/page/function] that [does what]:
---
[paste existing code]
---

Make this change: [specific change]

Keep everything else exactly the same.
```

**Workshop Project 02 — Mood Tracker Example:**
```
I have this mood tracker that logs mood entries and stores them in localStorage.
It currently shows entries as a plain text list.

Make this change: Replace the text list with a bar chart using the <canvas> element.
Each entry should show as one bar. Bar height = mood score (1–5).
Bar color: #7c3aed. X-axis labels: the date of each entry.
Use only vanilla JavaScript — no chart libraries.

Keep everything else exactly the same — the form, the localStorage logic, the page layout.
```

---

### Pattern 4: ARCHITECTURE

**When to use it:** Before writing any code on a complex feature. Lets the AI plan with you first.

**Structure:**
```
[What you're building and why]
[What you already have]
[Ask it to outline the approach before writing code]
```

**Template:**
```
I'm building [what] as part of [bigger project].

Here's what I already have: [describe or paste current state]

Before writing any code, outline the approach you'd take to build this:
- What files/components would you create?
- What data structures would you use?
- What are the potential problems?

Don't write code yet. Just the plan.
```

**Workshop Project 04 — AI Chat Assistant Example:**
```
I'm building an AI chat assistant as a single HTML file with vanilla JavaScript.
It will call the Claude API using a Vercel serverless function (to keep my API key secret).

Before writing any code, outline the approach:
- What files do I need?
- How does the frontend communicate with the serverless function?
- How do I keep the API key secure?
- What are the potential failure points?

Don't write code yet. Just the architecture plan.
```

---

## Project Prompt Templates

### Project 01 — Personal Landing Page

**Starting prompt:**
```
Build a personal landing page as a single HTML file. No frameworks, no JavaScript, no build tools.

Include:
- A hero section: my name [YOUR NAME], subtitle [YOUR SUBTITLE], a short bio (2–3 sentences)
- A "What I Do" section with 3–4 skill or interest cards
- A "Contact" section with email and social links

Design system:
- Background: #0a0a0a
- Text: #e8e8e8
- Accent: #7c3aed (purple)
- Font: Inter, system-ui, sans-serif

Must be mobile-responsive. Use a single <style> block in the <head>. No external CSS files.
```

---

### Project 02 — Mood Tracker

**Starting prompt:**
```
Build a mood tracker web app as a single HTML file with vanilla JavaScript.

Features:
1. A form to log a mood entry: mood score (1–5), optional note, date (auto-filled to today)
2. Entries stored in localStorage so they persist on refresh
3. A list of recent entries (last 7 days)
4. A bar chart using <canvas> showing mood over time

Design: dark background #0a0a0a, text #e8e8e8, accent #7c3aed
No external libraries. One HTML file only.
```

---

### Project 03 — Recipe Finder

**Starting prompt:**
```
Build a recipe finder web app as a single HTML file with vanilla JavaScript.

Features:
1. A search input where the user types an ingredient
2. A "Find Recipes" button that calls the TheMealDB API:
   https://www.themealdb.com/api/json/v1/1/filter.php?i={ingredient}
3. Results displayed as cards with: meal thumbnail, meal name, "View Recipe" button
4. "View Recipe" links to https://www.themealdb.com/meal/{idMeal}.html
5. A loading state while the API call is in progress
6. An error message if no results are found

Design: dark background #0a0a0a, text #e8e8e8, accent #7c3aed
No external libraries. One HTML file only.
```

---

### Project 04 — AI Chat Assistant

**Starting prompt:**
```
Build an AI chat assistant web app using a single HTML file for the frontend
and a Vercel serverless function (api/chat.js) for the backend.

Frontend (index.html):
- A chat interface with a message input and send button
- Messages displayed in a scrollable chat window
- User messages right-aligned, assistant messages left-aligned
- A loading indicator while waiting for a response

Backend (api/chat.js):
- Receives the user's message
- Calls the Anthropic Claude API using ANTHROPIC_API_KEY from environment variables
- Returns the assistant's response

The assistant's name is "[YOUR ASSISTANT NAME]".
System prompt: "[YOUR SYSTEM PROMPT]"

Design: dark background #0a0a0a, text #e8e8e8, accent #7c3aed
Do not put the API key anywhere in the frontend code.
```

---

## Common Mistakes and Fixes

| Mistake | Why it's a problem | Fix |
|---------|-------------------|-----|
| "Make it better" | Too vague — AI doesn't know what "better" means | Be specific: "Make the font larger, increase padding, change color to..." |
| Pasting 200 lines and asking "fix this" | Too much context — AI loses focus | Isolate the broken section and paste only that |
| Starting over on every error | Loses all your working code | Use ERROR-DEBUG pattern on the specific broken part |
| Not specifying constraints | AI adds frameworks, extra files, complexity | Always list constraints: "no frameworks, one file, inline styles only" |
| Vague "add a feature" | Unclear scope | Describe the feature as a user story: "When the user clicks X, Y should happen" |
| Trusting the first output completely | First output is a draft, not a final | Always test, then refine with a follow-up prompt |

---

## Prompt Cheat Sheet (One-Page Reference)

*Print this side of the page and keep it at your desk.*

---

```
┌─────────────────────────────────────────────────────────────────┐
│             VIBE CODING WORKSHOP — PROMPT CHEAT SHEET           │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  DESCRIBE-FIRST (starting something new)                        │
│  ┌───────────────────────────────────────────────────────────┐  │
│  │ "I'm building [X]. Create [Y] that: [requirements].      │  │
│  │  Output: [format]. Constraints: [limits]."               │  │
│  └───────────────────────────────────────────────────────────┘  │
│                                                                 │
│  ERROR-DEBUG (something is broken)                              │
│  ┌───────────────────────────────────────────────────────────┐  │
│  │ "I got this error: [paste error]. Here's my code:        │  │
│  │  [paste code]. What's wrong and how do I fix it?"        │  │
│  └───────────────────────────────────────────────────────────┘  │
│                                                                 │
│  REFINE (improving what you have)                               │
│  ┌───────────────────────────────────────────────────────────┐  │
│  │ "I have this [component]: [paste code]. Make this one    │  │
│  │  change: [change]. Keep everything else the same."       │  │
│  └───────────────────────────────────────────────────────────┘  │
│                                                                 │
│  ARCHITECTURE (planning before building)                        │
│  ┌───────────────────────────────────────────────────────────┐  │
│  │ "I'm building [X]. Before writing code, outline the      │  │
│  │  approach: files, data structures, potential problems."  │  │
│  └───────────────────────────────────────────────────────────┘  │
│                                                                 │
│  GOLDEN RULES                                                   │
│  • Context first, request second                                │
│  • Describe the output format                                   │
│  • Give constraints (what NOT to do)                            │
│  • Iterate, don't restart                                       │
│  • "Keep everything else the same" when refining               │
│                                                                 │
│  COLOR SYSTEM                                                   │
│  Background: #0a0a0a  │  Text: #e8e8e8  │  Accent: #7c3aed    │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## Advanced Techniques

### Chain-of-Thought

Ask the AI to reason through a problem step by step before writing code.

```
Before writing any code, think through this step by step:
1. What does the user need?
2. What's the simplest implementation?
3. What could go wrong?
4. How would you handle errors?

Then write the code.
```

Chain-of-thought prompting produces better code for complex features because the AI plans before it acts.

---

### Few-Shot Prompting

Show the AI examples of what you want before asking for the real thing.

```
I want to create cards for my projects. Here's the style I like:

Example 1:
<div class="card">
  <h3>Project Name</h3>
  <p>Short description here.</p>
  <a href="#">View →</a>
</div>

Now create 3 of these cards for:
1. "Personal Landing Page" — a professional portfolio site
2. "Mood Tracker" — a daily mood logging app
3. "Recipe Finder" — a cooking inspiration tool
```

Few-shot prompting is especially useful for generating content that needs to match a specific format or style.

---

### System Prompts

When using the Claude API directly (Project 04), you set a system prompt that defines how Claude behaves throughout the conversation.

```javascript
const systemPrompt = `You are Mira, a friendly cooking assistant.
You only answer questions about food, recipes, and cooking techniques.
When someone asks about something else, kindly redirect: "I'm a cooking assistant — 
ask me about food!"
Your tone is warm, encouraging, and practical.
Always suggest one variation or substitution when giving a recipe.`;
```

A good system prompt has:
- A name and role for the assistant
- What it will and won't do
- A defined tone
- One or two specific behaviors

---

*See also: `participant-workbook.md` (project worksheets), `docs/templates/README.md` (50 project starters)*
