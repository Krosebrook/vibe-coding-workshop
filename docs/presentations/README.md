# Presentations (Workshop Slide Decks)

> 10 PowerPoint-style presentation decks for the workshop, marketing, and community events. Formatted as Markdown outlines ready to import into any slide tool (Google Slides, PowerPoint, Keynote, Pitch).

---

## Deck Index

| # | Title | Use Case | Slides |
|---|-------|----------|--------|
| [P01](#p01---welcome-to-vibe-coding) | Welcome to Vibe Coding | Workshop opening | 12 |
| [P02](#p02---how-ai-coding-tools-work) | How AI Coding Tools Work | Morning session | 15 |
| [P03](#p03---the-prompt-anatomy) | The Prompt Anatomy | Morning session | 12 |
| [P04](#p04---project-01-personal-landing-page) | Project 01: Personal Landing Page | Project intro | 8 |
| [P05](#p05---project-02-mood-tracker) | Project 02: Mood Tracker | Project intro | 8 |
| [P06](#p06---apis-for-humans) | APIs for Humans | Afternoon session | 10 |
| [P07](#p07---project-03-recipe-finder) | Project 03: Recipe Finder | Project intro | 8 |
| [P08](#p08---project-04-ai-chat-assistant) | Project 04: AI Chat Assistant | Project intro | 10 |
| [P09](#p09---ship-it-deploying-to-the-real-world) | Ship It: Deploying to the Real World | End of day | 8 |
| [P10](#p10---vibe-coding-workshop-overview) | Vibe Coding Workshop Overview | Marketing / Sales | 15 |

---

## P01 — Welcome to Vibe Coding

**Use:** Workshop opening (0:00–0:30)  
**Duration:** 10–15 min

---

**Slide 1 — Title**
```
VIBE CODING WORKSHOP
Build apps by feel.

[Date] · [Location]
Instructor: Kyle Rosebrook
```

---

**Slide 2 — Today's Promise**
```
By 8:00 PM tonight, you will have:

→  4 deployed web applications
→  4 live URLs you can share
→  The skills to keep building on your own

[No prior coding experience required]
```

---

**Slide 3 — Who's in the Room?**
```
Quick introductions:

1. Your name
2. What brought you here today
3. The one app you'd build if you could build anything

[Facilitator note: go around the room]
```

---

**Slide 4 — What Is Vibe Coding?**
```
Vibe coding:
The practice of building software by describing
what you want — not by writing syntax.

You speak in intent.
The AI translates it to code.
You evaluate and refine.

"Make it feel warmer."
"The chart should update when I click."
"Show a loading spinner while it fetches."
```

---

**Slide 5 — The Loop**
```
THE VIBE CODING LOOP

   ┌──────────────┐
   │    Prompt    │ ← Describe what you want
   └──────┬───────┘
          ↓
   ┌──────────────┐
   │    Output    │ ← AI generates code
   └──────┬───────┘
          ↓
   ┌──────────────┐
   │    Refine    │ ← You evaluate and iterate
   └──────┬───────┘
          ↓
        Ship ✓
```

---

**Slide 6 — What You Build Today**
```
PROJECT 01  →  Personal Landing Page
PROJECT 02  →  Mood Tracker with Charts
PROJECT 03  →  Recipe Finder with API
PROJECT 04  →  AI Chat Assistant

Every project ships to a real URL.
```

---

**Slide 7 — The Schedule**
```
MORNING      Learn the Scales
             (How AI tools work, prompting basics)

LATE MORNING Build Projects 01 & 02
             (Guided, hands-on)

AFTERNOON    Build Projects 03 & 04
             (More freedom, more vibe)

EVENING      Ship It
             (Live URLs, celebration)
```

---

**Slide 8 — What You Bring**
```
YOU BRING                  WE PROVIDE
─────────────────────────────────────────
Laptop + Chrome/Firefox    All AI tool access
GitHub account (free)      The prompting playbook
An idea (even vague)       Your GitHub repo
Willingness to experiment  4 live deployed apps
```

---

**Slide 9 — The Most Important Rule**
```
GETTING STUCK IS THE CURRICULUM.

Getting stuck — and then unstuck — with AI
is the core skill.

Instructors float all day.
Nobody gets left behind.
No question is too basic.
```

---

**Slide 10 — About Your Instructor**
```
KYLE ROSEBROOK
Staff Engineer · AppSec & AI · Self-Taught

Came up through bartending.
Taught myself to code from scratch.
Now a Staff Engineer with 240+ AI tools.
Teaches senior engineers.

"I know what it feels like to stare at this
and think I have no idea where to start."
```

---

**Slide 11 — Let's Check Setup**
```
QUICK SETUP CHECK

□ Cursor is installed and open
□ Claude is accessible (claude.ai or via Cursor)
□ GitHub account is active
□ Vercel account is active

Raise your hand if anything isn't working.
```

---

**Slide 12 — Let's Go**
```
ONE DAY.
FOUR APPS.
YOUR IDEA.

Let's build.
```

---

## P02 — How AI Coding Tools Work

**Use:** Morning session (0:30–1:00)  
**Duration:** 20–25 min

---

**Slide 1 — Title**
```
HOW AI CODING TOOLS WORK
(Just enough to be dangerous)
```

---

**Slide 2 — What AI Actually Does**
```
AI coding tools are pattern completers.

They've read millions of lines of code.
They predict: "Given this prompt + context,
what code would come next?"

They are NOT:
✕ Searching the internet in real time
✕ Executing code before showing it
✕ "Thinking" the way humans do
```

---

**Slide 3 — The Context Window**
```
AI only knows what's in the conversation.

┌─────────────────────────────────────┐
│           CONTEXT WINDOW            │
│                                     │
│  Your system prompt                 │
│  + Your previous messages           │
│  + The code you've shared           │
│  + The files it can see             │
│                                     │
└─────────────────────────────────────┘

More context = better output.
Stale context = confused AI.
```

---

**Slide 4 — Hallucination**
```
AI HALLUCINATION

AI sometimes confidently generates incorrect:
- Code that doesn't work
- API endpoints that don't exist
- Library versions that are outdated
- Documentation that's fabricated

How to catch it:
→ Always run the code
→ Test API endpoints directly
→ Check official docs for critical details
```

---

**Slide 5 — The Tools**
```
CLAUDE (claude.ai / Cursor)
Best for: Complex code, explanations, architecture

CURSOR
Best for: Editing in your project files, multi-file changes

v0 (v0.dev)
Best for: Quick UI generation, visual components

VERCEL
Best for: Deploying — one click, real URL
```

---

**Slide 6 — When to Use Which Tool**
```
DECIDING WHICH TOOL TO USE

"I want to understand what to build" → Claude chat
"I want to build it in my project"   → Cursor
"I want a UI component quickly"      → v0
"I'm ready to deploy"                → Vercel
```

---

**Slide 7 — Live Demo: The Bad Prompt**
```
[DEMO SLIDE — presenter notes]

Show:
- Vague prompt: "make me a website"
- What the output looks like
- Why it's mediocre

Then show:
- Specific prompt with context + intent + constraints
- Much better output

Key lesson: The prompt IS the skill.
```

---

**Slide 8 — Context Is Everything**
```
WITHOUT CONTEXT:
"Add a chart to my page."
→ AI guesses. Often wrong.

WITH CONTEXT:
"I have a mood tracker that stores entries in localStorage.
Add a Chart.js bar chart below the entry list
showing mood scores for the last 7 days.
Use my existing purple accent color (#7c3aed)."
→ AI nails it.
```

---

**Slide 9 — The Golden Rule**
```
THE GOLDEN RULE OF VIBE CODING

Describe the EXPERIENCE you want,
not the implementation.

❌ "Use a CSS flexbox row with gap-4"
✅ "Put these three cards side by side with space between them"

❌ "Create an async fetch function"
✅ "When the user clicks search, call the API and show the results"

You speak product. Let AI speak code.
```

---

**Slide 10 — Iteration Is The Strategy**
```
DONE ISN'T THE FIRST OUTPUT

First prompt → rough draft (expected)
Second prompt → getting closer
Third prompt → looks right
Fourth prompt → done

Most projects take 10–30 prompts.
Each one is fast.
The iteration IS the work.
```

---

**Slide 11 — Working With Errors**
```
WHEN AI BREAKS SOMETHING

1. Copy the error message exactly
2. Paste into Claude:
   "I got this error: [error]
    Here is my current code: [code]
    What's wrong?"

3. Claude explains and fixes it
4. If it's still broken: paste the new error

Debugging is a skill. You're building it today.
```

---

**Slide 12 — What AI Is Bad At**
```
AI LIMITATIONS TO KNOW

✕ Counting (sometimes miscounts items)
✕ Long exact strings (may hallucinate slightly)
✕ Knowing your screen size or design intent
✕ Remembering things from a closed session
✕ Executing side effects (it doesn't click the button)

Work around these:
→ Be specific about numbers
→ Test visually (run the code)
→ Start new sessions with fresh context
```

---

**Slide 13 — Your Mental Model**
```
THINK OF AI AS A NEW TEAM MEMBER

Brilliant but new.
Doesn't know your project until you explain it.
Makes mistakes and corrects when told.
Doesn't take offense.
Never too tired to try again.

You are the product manager.
You have the taste.
AI has the technical skill.
```

---

**Slide 14 — Summary**
```
HOW AI CODING TOOLS WORK: SUMMARY

→ AI predicts code from patterns, not intelligence
→ Context is everything — give more of it
→ Hallucination happens — always test the output
→ Iteration is the strategy, not a fallback
→ You are the product manager
```

---

**Slide 15 — Questions Before We Build**
```
ANY QUESTIONS?

In 5 minutes, we start Project 01.

→ Open Cursor
→ Open a new, empty folder
→ Have Claude ready
```

---

## P03 — The Prompt Anatomy

**Use:** Morning session (1:00–1:30)  
**Duration:** 20 min

---

**Slide 1 — Title**
```
THE PROMPT ANATOMY
Four parts that make any prompt work
```

---

**Slide 2 — The Four Parts**
```
EVERY GREAT PROMPT HAS:

1. CONTEXT     Who you are, what exists already
2. TASK        What you want built or changed
3. FORMAT      How you want the output
4. CONSTRAINTS What not to do
```

---

**Slide 3 — Context**
```
CONTEXT: SET THE SCENE

Bad:  "Add a navigation bar"

Good: "I have a single-page HTML file for my
       personal portfolio. It uses dark background
       (#0a0a0a) with purple accent (#7c3aed).
       There's a hero section, a projects section,
       and a contact section."

Now the AI knows what world it's working in.
```

---

**Slide 4 — Task**
```
TASK: SAY WHAT YOU WANT

Vague:    "Make it better"
Specific: "Add a sticky navigation bar at the top
           with links that jump to each section.
           The active section link should be
           brighter than the others."

Be the client giving a brief,
not the contractor figuring it out.
```

---

**Slide 5 — Format**
```
FORMAT: HOW TO RESPOND

Examples:
"Show me only the CSS changes, not the full file"
"Give me the full updated HTML file"
"Explain what you changed before showing the code"
"Return a JSON object I can paste into my app"

Without format guidance, AI guesses.
Sometimes it guesses right. Not always.
```

---

**Slide 6 — Constraints**
```
CONSTRAINTS: WHAT NOT TO DO

"No JavaScript — HTML and CSS only"
"Don't change the color scheme"
"Keep the existing section structure"
"Use CDN, don't install npm packages"
"Keep it under 20 lines"

Constraints save you from AI going off-script.
```

---

**Slide 7 — Full Example**
```
CONTEXT:
I have a one-page HTML portfolio site.
Dark theme (#0a0a0a), purple accents (#7c3aed).
There's a hero, projects, and contact section.

TASK:
Add a sticky nav bar with links to each section.
The links should smoothly scroll.

FORMAT:
Give me the full updated <nav> HTML
and the CSS to add to my existing style block.

CONSTRAINTS:
No JavaScript. HTML/CSS only.
Don't change any existing styles.
```

---

**Slide 8 — The Refine Prompt**
```
REFINE PROMPTS (after first output)

"The [X] looks [problem]. Make it [goal]."

Examples:
"The nav is too tall. Make it thinner."
"The project cards have no spacing between them. Add gap."
"The hero text is hard to read. Increase font size."
"The button hover is too subtle. Make it more obvious."

You don't need to know CSS properties.
Describe what you see and what you want instead.
```

---

**Slide 9 — Prompting Practice**
```
[ACTIVITY SLIDE]

Try writing a prompt for your landing page
using the 4-part structure.

Share with the person next to you.
Does it have all 4 parts?
Could it be more specific?

2 minutes.
```

---

**Slide 10 — The Debug Prompt**
```
THE DEBUG PROMPT TEMPLATE

"I got this error:
[paste exact error message]

Here is my code:
[paste relevant code]

What's wrong and how do I fix it?
Explain as if I'm not a programmer."

Use this every time something breaks.
```

---

**Slide 11 — Common Prompt Mistakes**
```
COMMON MISTAKES

✕ Asking for everything at once
  → One feature at a time

✕ No context about existing code
  → Always set the scene first

✕ "Make it look better" without specifics
  → Better in what way? Describe it.

✕ Accepting first output without testing
  → Always run it in the browser first

✕ Starting a new chat after every message
  → Keep the conversation going — context is valuable
```

---

**Slide 12 — You're Ready**
```
YOU HAVE THE SKILLS.

Context + Task + Format + Constraints.

The rest is practice.

Let's build Project 01.
```

---

## P04 — Project 01: Personal Landing Page

**Use:** Before Project 01 (1:30)  
**Duration:** 5 min (quick intro)

---

**Slide 1**
```
PROJECT 01
PERSONAL LANDING PAGE

The first vibe coding exercise.
```

**Slide 2**
```
WHAT YOU'RE BUILDING

A personal page that says:
→ Who you are
→ What you do or what you're interested in
→ How to reach you
→ Something about your work or interests

This is YOUR page. Not a template.
```

**Slide 3**
```
THE PROMPT TO START

"Build me a personal portfolio page.
I want:
- My name at the top in large text with a short tagline
- A brief section about me (2-3 sentences)
- A 'Work' or 'Projects' section
- My contact email at the bottom
Style: [describe your ideal feel]
No JavaScript needed."
```

**Slide 4**
```
WHAT TO FOCUS ON

→ Making it feel like YOU
→ The iterate-fast habit
→ One change at a time
→ Asking for what you see, not what you know

45 minutes. Go.
```

**Slide 5**
```
STUCK? TRY THIS:

"I don't like [X]. Change it to feel more [adjective]."

"The [element] is [too big/small/tight/dark].
Fix it."

"Add [element] to the [section]."
```

**Slide 6**
```
SHARE TIME IN 45 MINUTES

Everyone shows their screen.
Show us what you built and one thing
you want to change next.
```

**Slide 7**
```
REMEMBER

The first version is supposed to be rough.
That's not failure. That's the starting point.

Vibe coding is about iteration.
```

**Slide 8**
```
START YOUR TIMERS.
Let's build.
```

---

## P05 — Project 02: Mood Tracker

**Use:** Before Project 02  
**Duration:** 5–7 min

---

**Slide 1**
```
PROJECT 02
MOOD TRACKER WITH CHARTS

Your first interactive app.
This is where the vibe clicks.
```

**Slide 2**
```
NEW CONCEPTS WE'LL USE

→ JavaScript state (storing data)
→ localStorage (saving between refreshes)
→ Chart.js (the charting library via CDN)
→ User interactions (clicking, typing, submitting)
```

**Slide 3**
```
THE STATE CONCEPT

"State" = the current data your app holds.

Mood tracker state:
→ All past entries (array)
→ The current mood value selected

When state changes → the screen updates.

You don't need to understand this fully.
Just know it exists and tell Claude you need it.
```

**Slide 4**
```
THE STARTER PROMPT

"Build a mood tracker app.
- Log mood daily (1–5 scale with emoji labels)
- Optional text note per entry
- List of past entries
- Bar chart showing mood last 7 days (Chart.js CDN)
- Save to localStorage (no backend needed)
Dark theme. Mobile-friendly."
```

**Slide 5**
```
YOUR FREEDOM

Swap "mood" for anything you want to track:

→ Energy levels
→ Anxiety rating
→ Productivity score
→ Pain level (for health tracking)
→ Weather mood (for gardeners, farmers)

Same structure. Your data.
```

**Slide 6**
```
WATCH FOR:

→ The Chart.js CDN import (in <head>)
→ The localStorage.setItem/getItem calls
→ The update function (runs after every change)

You don't need to understand all of it.
When you're curious about a line, ask:
"Explain this line of code."
```

**Slide 7**
```
60 MINUTES. GO.

Focus: Get the core working first.
Then add features.
```

**Slide 8**
```
STILL STUCK?

"The chart isn't showing. Here's my code: [code].
What's missing?"

"I want to add a note field. Where does it go
and how do I save it to localStorage?"
```

---

## P06 — APIs for Humans

**Use:** Afternoon intro to Project 03  
**Duration:** 15 min

---

**Slide 1**
```
APIs FOR HUMANS
No computer science degree required.
```

**Slide 2**
```
WHAT IS AN API?

THE RESTAURANT ANALOGY:

You're the customer (your app).
The kitchen has the food (the data).
The waiter is the API.

You tell the waiter what you want.
The waiter goes to the kitchen.
The waiter brings back your order.

You never see the kitchen.
```

**Slide 3**
```
IN PRACTICE:

You: "Give me recipes with chicken"
       ↓  (HTTP request)
API: [searches its database]
       ↓  (HTTP response)
You: [list of chicken recipes as JSON]

Your app makes the request.
Your app shows the response.
```

**Slide 4**
```
JSON: THE LANGUAGE OF DATA

{
  "name": "Chicken Tikka Masala",
  "category": "Indian",
  "area": "British",
  "ingredients": ["chicken", "yogurt", "spices"],
  "instructions": "..."
}

JSON = key-value pairs, wrapped in {}
Arrays of things wrapped in []

Claude can read JSON. You just tell it
what fields to use.
```

**Slide 5**
```
FREE APIS WE LOVE

TheMealDB      → Recipes (no key!)
Open-Meteo     → Weather (no key!)
PokeAPI        → Pokémon (no key!)
DogAPI         → Dog breeds (free key)
Free Dictionary → Word definitions (no key!)
CoinGecko      → Crypto prices (no key!)
GitHub API     → GitHub data (no key for public)
```

**Slide 6**
```
HOW TO USE AN API IN YOUR APP

1. Find the API endpoint (the URL)
2. Tell Claude: "Call this API when the user searches"
3. Claude writes the fetch() code
4. You test it in the browser (Network tab)
5. Claude handles the loading + error states
```

**Slide 7**
```
THE API PROMPT TEMPLATE

"I want to call this API:
[API URL]

When the user [trigger],
fetch [data] and show it as [UI description].

Show loading while fetching.
Show error message if it fails."
```

**Slide 8**
```
READING API DOCS

Most API docs show:
→ The base URL
→ What parameters to add
→ What the response looks like

Example:
https://www.themealdb.com/api/json/v1/1/search.php?s=chicken

?s=chicken means: search for "chicken"
You change "chicken" to what the user typed.
```

**Slide 9**
```
CHECKING API RESPONSES

Open browser → Network tab
Make an API call in your app
Click the request
Click "Response"
See the actual data

This is debugging like a real developer.
```

**Slide 10**
```
ANY QUESTIONS?

In 5 minutes, we start Project 03.
```

---

## P07 — Project 03: Recipe Finder

**Use:** Before Project 03  
**Duration:** 5 min

---

**Slide 1**
```
PROJECT 03
RECIPE FINDER WITH API

Connect to the real internet.
Real data. Real app.
```

**Slide 2 — Slides 2-8 follow same pattern as P04/P05**
```
API: TheMealDB (free, no key needed)
https://www.themealdb.com/api/json/v1/1/search.php?s=[query]

Features to build:
→ Search box (ingredient or meal name)
→ Recipe cards with image + name
→ Click to expand: ingredients + instructions
→ Loading state
→ Error state
```

---

## P08 — Project 04: AI Chat Assistant

**Use:** Before Project 04  
**Duration:** 10 min

---

**Slide 1**
```
PROJECT 04
AI CHAT ASSISTANT

The capstone.
Your app. Your AI. Your personality.
```

**Slide 2**
```
WHAT YOU'RE BUILDING

A chat interface that uses the Claude API
to power an assistant you design.

You define:
→ The assistant's name
→ Its personality
→ What it specializes in
→ How it speaks

It's not just a chatbot.
It's YOUR chatbot.
```

**Slide 3**
```
THE SYSTEM PROMPT

The system prompt is the personality file.
It tells Claude how to behave before the user
says anything.

Examples:
"You are Penny, a cheerful financial advisor..."
"You are a no-nonsense coding mentor..."
"You are a patient creative writing coach..."
```

**Slide 4**
```
CHOOSE YOUR ASSISTANT TYPE

□ Personal productivity coach
□ Cooking and recipe assistant
□ Writing / grammar coach
□ Study buddy for [subject]
□ Interview practice coach
□ [Your idea]
```

**Slide 5**
```
THE TECH INVOLVED

Claude API (via Anthropic)
Environment variable for the API key
Streaming responses (text appears as it's generated)
Message history (so the AI remembers the conversation)

Claude handles all of this.
You describe what you want.
```

**Slide 6**
```
THE STARTER PROMPT

"Build an AI chat interface using the Claude API.
System prompt: [your assistant's personality]

Features:
- Chat bubble UI (user right, assistant left)
- Input at bottom with send + Enter support
- Loading indicator while waiting
- Clear chat button
- Dark theme"
```

**Slide 7**
```
DEPLOYING WITH THE API KEY

You'll use a .env file to store your API key.
Claude will show you how to set it up in Vercel.

Never paste API keys directly in code.
Always use environment variables.
```

**Slide 8**
```
90 MINUTES TO SHIP.

This is the last project.
Make it yours.
```

**Slide 9**
```
WHEN YOU'RE DONE:

→ Test it thoroughly
→ Change anything that doesn't feel right
→ Then deploy to Vercel

You're about to ship your first AI-powered app.
```

**Slide 10**
```
GO.
```

---

## P09 — Ship It: Deploying to the Real World

**Use:** End of day (7:00)  
**Duration:** 15 min

---

**Slide 1**
```
SHIP IT.
Time to make it real.
```

**Slide 2**
```
WHAT "DEPLOYED" MEANS

Right now your app lives on your laptop.
Nobody else can see it.

After deployment:
→ It lives on a server in the cloud
→ It has a real URL
→ Anyone with the link can use it
→ It works when your laptop is closed
```

**Slide 3**
```
DEPLOYING WITH VERCEL

1. Push code to GitHub
2. Go to vercel.com
3. Import your GitHub repo
4. Click Deploy
5. Get your URL

That's it.
```

**Slide 4**
```
THE DEPLOY CHECKLIST

□ No console.log statements with private data
□ No API keys hardcoded in the code
□ All links and images work
□ Tested on mobile screen size
□ No "localhost" URLs in the code
```

**Slide 5**
```
ENVIRONMENT VARIABLES ON VERCEL

For apps with API keys:
Vercel Dashboard → Your Project → Settings → Environment Variables
Add: ANTHROPIC_API_KEY = [your key]

Never add to the code file.
Never commit to GitHub.
Vercel handles it securely.
```

**Slide 6**
```
YOUR LIVE URL WILL LOOK LIKE:

your-app-name.vercel.app

You can customize it.
You can add a custom domain later.

But the important thing?
It's LIVE. It's REAL. It's YOURS.
```

**Slide 7**
```
THE SHIP IT CEREMONY

In 15 minutes, everyone reads their URL aloud.

Not showing your code.
Showing your app.

The thing you built. The real thing.
```

**Slide 8**
```
AFTER TODAY

You have 4 apps deployed.
You have the skills to build more.
The workshop Discord is open.

"Keep building."
```

---

## P10 — Vibe Coding Workshop Overview

**Use:** Marketing, sales, conference talks  
**Duration:** 20–30 min

---

**Slide 1**
```
VIBE CODING WORKSHOP
Build apps by feel.

A one-day workshop for people
who've always wanted to build software
but thought it wasn't for them.
```

**Slide 2**
```
THE PROBLEM WE SOLVE

There are millions of people with software ideas
who can't build them because:

→ Bootcamps take 3–12 months
→ Hiring developers is expensive
→ No-code tools hit walls fast
→ Tutorials teach syntax, not shipping

They don't need a CS degree.
They need a different approach.
```

**Slide 3**
```
THE OPPORTUNITY

AI tools can now generate working code
from natural language descriptions.

The gap between "idea" and "app"
has never been smaller.

But most people don't know how to use these tools.
And they don't know what they're capable of.

That's the workshop.
```

**Slide 4**
```
WHAT IS VIBE CODING?

Building software by describing what you want,
not by writing syntax.

Intent → Code → Result → Refine

You bring the taste and the idea.
AI brings the technical execution.
You learn to direct, evaluate, and ship.
```

**Slide 5**
```
THE WORKSHOP FORMAT

One day. In person. Hands-on from minute one.

Morning:    Learn the tools
Late AM:    Build Projects 01 & 02
Afternoon:  Build Projects 03 & 04
Evening:    Deploy to live URLs
```

**Slide 6**
```
FOUR PROJECTS IN ONE DAY

01  Personal Landing Page      (prompt → output → refine)
02  Mood Tracker with Charts   (state + data viz)
03  Recipe Finder with API     (APIs + error handling)
04  AI Chat Assistant          (AI integration + deploy)
```

**Slide 7**
```
WHO SHOWS UP

→ Career changers exploring tech
→ Designers who want to prototype
→ Founders who want to build MVPs
→ Marketers who need custom tools
→ Non-profits with limited budgets
→ Anyone who's had an idea they couldn't build

They all ship by end of day.
```

**Slide 8**
```
THE TOOLS

CLAUDE      AI assistant for code + explanation
CURSOR      AI-native code editor
v0          UI component generation
VERCEL      One-click deployment
SUPABASE    Database + auth (Project 04)
GITHUB      Code hosting + sharing
```

**Slide 9**
```
WHAT PARTICIPANTS LEAVE WITH

→ 4 deployed apps on live URLs
→ GitHub repo with all their code
→ The prompting playbook (PDF)
→ Skills to keep building solo
→ Alumni Discord community
```

**Slide 10**
```
ABOUT THE INSTRUCTOR

KYLE ROSEBROOK
Staff Engineer · AppSec & AI · Self-Taught

"I didn't come up through a CS program.
I came up through bartending and rebuilding
my life from scratch.

I know what it feels like to stare at a tool
this powerful and think:
I have no idea where to start.

That's exactly who this workshop is for."
```

**Slide 11**
```
LOGISTICS

📍  College of Lake County · Grayslake, IL
📅  Summer 2026
👥  Limited to 20 seats per cohort
💰  Early bird pricing available
📧  hello@vibecodingworkshop.com
```

**Slide 12**
```
THE TRACK RECORD

"I built my first app and deployed it in one day.
I honestly didn't think that was possible for me."

"The moment it all clicked was when I described
a change in plain English and it just worked.
That's the vibe."

"I came in thinking I'd need 6 months in a bootcamp.
I left with 4 apps."
```

**Slide 13**
```
THE PHILOSOPHY

Everyone who can describe what they want
should be able to build it.

Not just engineers.
Not just technically-minded people.

Everyone.
```

**Slide 14**
```
JOIN THE WAITLIST

vibecodingworkshop.com

Summer 2026 · 20 seats · Beginners welcome

hello@vibecodingworkshop.com
```

**Slide 15**
```
QUESTIONS?

"If you can write an email,
you can vibe code."

Let's talk.
```

---

*These presentations are formatted for import into Google Slides, PowerPoint, Keynote, or Pitch.*  
*Each `---` divides slides. Slide content between backticks is the slide body.*  
*Speaker notes are marked `[presenter note]` where applicable.*
