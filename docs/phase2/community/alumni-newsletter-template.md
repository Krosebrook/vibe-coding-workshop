# Alumni Newsletter Template

> Template and content calendar for the Vibe Coding Workshop alumni newsletter.

---

## Purpose

The newsletter keeps alumni connected to each other and to the workshop community. It ships once a month. It's worth reading every time.

**What it is not:** A broadcast channel for announcements. Not a sales newsletter. Not a content marketing funnel. It's a community update from someone who cares about what alumni are building.

---

## Platform Setup (Substack — Recommended)

**Why Substack:**
- Free to publish
- Built-in email list management
- Clean reading experience
- "Notes" feature for quick updates between issues
- Discoverable by new readers

**Setup:**

1. Go to [substack.com](https://substack.com)
2. Click **Start writing**
3. Name your publication: **Vibe Coding Workshop** or **The Vibe** (shorter, catchier)
4. URL: `vibecodingworkshop.substack.com`
5. Description: "A monthly newsletter for people who build things with AI. For alumni of the Vibe Coding Workshop."
6. Set publication to **Free** (paid upgrades are optional later)

**Importing your email list:**
1. Go to **Settings → Subscribers → Import subscribers**
2. Upload a CSV with participant emails (collect consent at workshop registration)

---

## Newsletter Structure

Each edition follows this structure:

```
1. Subject line + preview text
2. Header: edition number + date
3. Opening note (3–5 sentences, personal, from Kyle)
4. Alumni Spotlight (1 person, 1 project)
5. What We're Building (3–5 community links/projects)
6. Tool or Prompt of the Month
7. Upcoming (events, next cohort, news)
8. Closing line + sign-off
```

---

## Monthly Edition Template

---

```markdown
# The Vibe — [Month Year] · Issue #[N]

---

Hey [first name or "builders"],

[3–5 sentences. Personal. Something true about what you've been thinking about,
building, or noticing. Not a formal intro — more like a text from a friend who
also happens to run a workshop. Example: "I spent the last week trying to get a
Supabase realtime subscription to work. Took me 4 days. Then I wrote one prompt
and it worked in 15 minutes. That's still surprising to me."]

---

## 🌟 Alumni Spotlight

**[Name]** — *[Cohort]*

[2–3 sentences about what they built. What the app does. What's interesting about it.
Quote from them if you have one.]

🔗 [Live URL]

[Screenshot if available — just describe it in text for the template]

---

## 🏗️ What We're Building

Things alumni have shipped or shared this month:

- **[Name]** built [description]. [URL]
- **[Name]** is working on [description]. [URL if available]
- **[Name]** shared this prompt that got great results: `[short prompt snippet]`
- **[Name]** asked a question that sparked a good thread: "[question]" — [summary of answers]

[Minimum 3 entries. If the community is quiet, reach out directly to 3 alumni and ask.]

---

## 💡 Tool or Prompt of the Month

**[Tool name or "Prompt Pattern"]**

[2–3 sentences introducing the tool or technique.]

[If a prompt: show the actual prompt in a code block.]

```
[prompt here]
```

[What it's useful for. How to use it. One concrete example.]

---

## 📅 Upcoming

- **[Event name]** — [Date] — [1-sentence description and link]
- **Next workshop cohort** — [Date or "TBD"] — [waitlist link or registration link]
- **[Anything else]**

---

Keep building.

Kyle

*[Unsubscribe link]*
*Vibe Coding Workshop · hello@vibecodingworkshop.com · [Website URL]*
```

---

## Content Calendar — 12 Months

| Month | Theme | Alumni Spotlight Focus | Tool/Prompt Focus |
|-------|-------|----------------------|------------------|
| Month 1 (post-cohort) | "First Builds" | First deployed project from cohort | DESCRIBE-FIRST prompt pattern |
| Month 2 | "Going Further" | Alumni who extended a workshop project | REFINE pattern — how to iterate |
| Month 3 | "New Projects" | Alumni who started something outside the workshop | ARCHITECTURE pattern — planning first |
| Month 4 | "Fixing Things" | Alumni who debugged something hard | ERROR-DEBUG deep dive |
| Month 5 | "Design" | Beautiful UI built with v0 | v0 + Cursor workflow |
| Month 6 | "6-Month Check-In" | Where are they now? Survey results | What tools stuck around |
| Month 7 | "Data" | Alumni who added Supabase to a project | Supabase basics for non-devs |
| Month 8 | "APIs" | Alumni who integrated a new API | How to read API docs |
| Month 9 | "AI Features" | Alumni who built something with Claude API | System prompt patterns |
| Month 10 | "Sharing" | Alumni who shared their work publicly | Deploying on custom domain |
| Month 11 | "Community Picks" | Reader-voted best project of the year | Top prompts of the year |
| Month 12 | "Year One" | Biggest transformation story | Full workflow recap |

---

## Subject Line Formulas

Write 2–3 variations for each edition and A/B test if your platform supports it.

| Formula | Example |
|---------|---------|
| **Question** | "What are you building this month?" |
| **Outcome** | "Alex went from zero to 4 deployed apps in one day" |
| **Number list** | "3 prompts worth stealing this month" |
| **Contrarian** | "You don't need to understand the code" |
| **Direct** | "Issue #3: March builds + a Supabase tip" |
| **Personal** | "I broke my own project on purpose. Here's why." |

**Avoid:**
- Clickbait ("You won't believe what...")
- Generic ("Monthly newsletter")
- Vague teasers without a payoff promise

---

## Sample First Edition

```markdown
# The Vibe — Issue #1 · August 2026

---

Hey builders,

We ran the first cohort two weeks ago. Twenty people walked in with laptops and ideas.
They left with 4 live apps each and (I counted) 87 combined live URLs.

That's 87 things that didn't exist before workshop day.

I've been thinking about that. It's easy to take it for granted — "oh, it was just
a workshop, they built simple stuff." But simple stuff that exists is more valuable
than complex stuff that's still in your head. Every one of those URLs is real.

Here's what some of you have been up to since.

---

## 🌟 Alumni Spotlight

**Jordan M.** — *Summer 2026 Cohort*

Jordan came to the workshop wanting to build a portfolio site for their freelance
design work. They shipped Project 01 on the day — and then spent the next two weeks
extending it into a full portfolio with a case study section and a contact form
connected to Formspree.

"I've been meaning to redo my website for 2 years. I did it in a week."

🔗 [jordanmdesign.com] *(fictional URL for template)*

---

## 🏗️ What We're Building

Things alumni have shipped or shared this month:

- **Alex** extended the mood tracker into a habit tracker with 5 custom metrics. [URL]
- **Sam** added authentication to their recipe finder using Supabase Auth. [URL]
- **Morgan** built a prompt that generates color palettes from mood descriptions. Try it: [URL]
- **Taylor** asked: "How do I add a contact form to a static HTML site?" Best answer: use Formspree (free). Here's the prompt that sets it up in 3 minutes.

---

## 💡 Prompt of the Month

**The DESCRIBE-FIRST pattern — a reminder**

This is the one that unlocks everything else. Context first, request second.

```
I'm building [what you're building].
[What already exists / what you have so far]

Create [what you want] that:
- [Requirement 1]
- [Requirement 2]

Output: [format]
Constraints: [limits]
```

The more specific your description, the better the output. That's it. That's the pattern.

---

## 📅 Upcoming

- **Virtual Show & Tell** — September 12, 7 PM CT — Zoom call, share your screen for 3 min, demo what you built. [Link TBD]
- **Next workshop cohort** — Fall 2026 (date TBD) — [Waitlist link]

---

Keep building.

Kyle

---
*Vibe Coding Workshop · Grayslake, IL · hello@vibecodingworkshop.com*
*[Unsubscribe] · [View in browser]*
```

---

## Substack Setup Checklist

- [ ] Publication name and URL set
- [ ] Publication description written
- [ ] Profile photo uploaded
- [ ] Email list imported (with consent)
- [ ] Welcome email customized (sent to new subscribers)
- [ ] First edition scheduled or published
- [ ] Newsletter linked in website footer and Discord `#announcements`

---

*See also: `discord-guide.md`, `docs/phase2/email-sequences/post-workshop-followup.md`*
