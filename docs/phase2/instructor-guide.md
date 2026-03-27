# Instructor Guide — Workshop Day

> Your complete companion for running the Vibe Coding Workshop. Read this the night before. Bring it on the day.

---

## Pre-Day Preparation Checklist

### One Week Before

- [ ] Confirm room booking at College of Lake County (building, room number, start/end time)
- [ ] Confirm headcount — final participant list locked
- [ ] Send "Final Setup Check" email (see `email-sequences/pre-workshop-onboarding.md`)
- [ ] Verify all 4 project starter files are in GitHub Classroom (see `github-classroom-setup.md`)
- [ ] Test all accounts on a fresh browser profile: Claude, Cursor, v0, Vercel, Supabase, GitHub
- [ ] Print 20 copies of `participant-workbook.md`
- [ ] Print 20 copies of `prompting-playbook.md` (single page, front/back)
- [ ] Order or arrange lunch and coffee service
- [ ] Prepare your slide deck (see `docs/presentations/README.md`)
- [ ] Create a workshop-day Discord channel for live support questions

### Night Before

- [ ] Send "See you tomorrow!" email (see `email-sequences/pre-workshop-onboarding.md`)
- [ ] Charge your laptop fully
- [ ] Prepare your demo projects: a finished version of all 4 apps, ready to show
- [ ] Pack: laptop charger, phone charger, backup hotspot, power strip, name tags, markers
- [ ] Lay out your clothes. Eat a real meal. Sleep by 10 PM.
- [ ] Run through the opening 5-minute welcome script in your head

### Morning of Workshop

- [ ] Arrive at 7:00 AM — 90 minutes before doors open
- [ ] Room setup complete (see below) by 7:45 AM
- [ ] First participants arrive at 8:00 AM
- [ ] Post the WiFi credentials on the whiteboard

---

## Room Setup Instructions

### Table Configuration
Arrange tables in a **U-shape** or **clusters of 4** — not rows. Participants need to see each other's screens. They're going to help each other today, and that only works if they can turn and look.

```
  [SCREEN / PROJECTOR]

  [table][table]   [table][table]
  [table][table]   [table][table]

     [table][table][table]

           ^
      (U-shape base)
```

### Per-Seat Setup
Each seat should have:
- Printed participant workbook
- Printed prompting playbook (cheat sheet)
- Name tag (blank, with marker nearby)
- Power outlet accessible or power strip on table

### Tech Setup
- Test HDMI/DisplayPort connection to projector or TV
- Test audio if you'll play music or demo anything with sound
- Write WiFi credentials on whiteboard in large, readable letters
- Have your browser open on relevant tabs: Claude, v0, Vercel, GitHub, TheMealDB docs
- Have Cursor open with an empty project ready for the first live demo

### Backup Plan
- Backup hotspot phone charged to 100%
- Know the room's IT support contact (College of Lake County helpdesk number)
- Have the GitHub Classroom assignment links in a shared Google Doc that participants can access even if your screen goes dark

---

## Teaching Techniques by Phase

### Phase 1: Learn the Scales (9:00 AM)

**Goal:** Get everyone to a shared mental model before they start building.

**Techniques:**
- **Think aloud** — narrate what you're doing while you demo. "I'm looking at this error and thinking: what did I ask for vs. what did I get? Let me refine the prompt."
- **Show failure first** — before showing a good prompt, show a bad one. The contrast lands the lesson.
- **Peer recognition** — when a participant writes a great prompt, put it on the screen. "Look at how Alex phrased that. Notice they gave context, a specific output format, and a constraint. That's the move."
- **The 30-second rule** — if someone's been stuck for 30 seconds, offer help. Don't let frustration compound silently.

### Projects 01 & 02 (Guided)

**Goal:** Everyone ships at least 2 projects before lunch and post-lunch break.

**Techniques:**
- **Milestone announces** — at the halfway point of each build block, call out: "Who has X working? If you don't, tell me now." Creates urgency without panic.
- **Walkabout rhythm** — complete one pass of the room every 10 minutes. 20 people × 30 seconds each = roughly 10 minutes. You see everyone, everyone sees you.
- **The pair move** — when someone is stuck, sit next to them for 90 seconds. Often they solve it themselves with you present. You don't have to say anything.
- **Shared debug** — when multiple people hit the same error, call it out for the room. "Three people just hit a CORS error. Let me show you how to fix it once, together."

### Projects 03 & 04 (Open-ended)

**Goal:** Participants apply the pattern independently. Less hand-holding, more coaching.

**Techniques:**
- **Ask before telling** — "What have you tried? What did the AI say?" Before jumping in, understand where they are.
- **Scaffold the prompt** — if someone doesn't know what to prompt, help them describe what they want. "What do you want to happen when you click that button?" Then: "Now say that to Claude."
- **Celebrate iteration** — "How many prompts did it take you to get that chart working?" When the answer is 8, celebrate. "Eight prompts and it's perfect. That's the job."

---

## Handling Common Problems

### "I can't log in to [tool]"

**Before 9 AM:** Drop everything and help immediately. A participant who can't log in will feel behind for the rest of the day.

**During build time:** Ask a neighbor to help. Pair them up while you continue circulating. Return within 5 minutes.

**Fallback:** If Claude's free tier is rate-limited, they can use the Claude web interface for the workshop (not API). If Cursor won't activate, they can code directly in VS Code or use Claude's web interface + copy-paste.

### "The AI keeps giving me wrong answers"

This is a prompting problem, not an AI problem. Walk through the DESCRIBE-FIRST pattern:
1. "What context are you missing from your prompt?"
2. "What specific output format did you ask for?"
3. "What constraint did you forget to mention?"

Usually one of these three is the issue.

### "My code has an error and I don't know how to fix it"

The ERROR-DEBUG pattern. Ask them to:
1. Copy the full error message
2. Paste it to Claude with: "I got this error: [paste]. Here's my code: [paste]. What's wrong and how do I fix it?"

This works 90% of the time. Model this process on screen when it comes up in a group setting.

### "This is too hard. I don't know what I'm doing."

This is the most common feeling at around 2 PM. The response:
- "That feeling is part of learning. It means you're doing something new."
- "You've already shipped 2 projects today. That's already more than most people do."
- "Let's look at what you have. What's one thing you want to fix?"

Keep them focused on the next small step. Don't try to fix everything at once.

### "Someone is way ahead and bored"

Give them a stretch challenge: "Make your landing page fully mobile-responsive. Add a dark mode toggle. Add a contact form. Add animations." Or invite them to help a neighbor — peer teaching accelerates both people's learning.

### Tech failure: WiFi goes down

- Immediately activate your backup hotspot
- Have participants pair up (2 people per hotspot connection)
- Switch to offline-capable portions: reviewing prompting playbook, writing project plans on paper
- If hotspot also fails: run a live prompt-writing workshop on the whiteboard, with participants writing prompts without a computer

### Tech failure: Projector/screen goes down

- Continue the workshop verbally
- Walk around to each cluster of 4 and demo on their screen directly
- This is actually fine — sometimes more personal

### Participant arrives late

- Greet them at the door, hand them workbook + cheat sheet
- Point them to a seat near someone who's clearly comfortable
- Give a 60-second summary of where the group is
- Don't stop the session for a late arrival

---

## Energy Management for a Full-Day Workshop

### The Energy Curve

A 12-hour day has predictable energy valleys:
- **10:00–10:30 AM** — first slump after the opening buzz
- **1:00–1:30 PM** — post-lunch trough
- **3:30–4:00 PM** — mid-afternoon dip

You scheduled breaks at each of these points. Honor them.

### For Yourself

- **Eat breakfast** before you arrive. You won't eat again until lunch.
- **Drink water constantly.** Not coffee — water. Coffee is fine too, but not instead.
- **Move during breaks.** Walk outside if possible. Even 2 minutes helps.
- **Don't solve every problem yourself.** The pair-up technique exists so you can distribute load.
- **Lower your voice to raise attention.** If the room gets chaotic, speak quieter, not louder. People lean in.

### For the Room

- **Music between sessions.** Instrumental or lo-fi. Keeps the energy from going flat.
- **Acknowledge the 2 PM wall.** "I know it's the afternoon and your brain is full. We have one more project. It's the best one. Let's go."
- **Celebrate loudly and frequently.** Claps for first deploys. Shoutouts for creative prompts. The energy you spend on celebration comes back tenfold.
- **Keep transitions tight.** Dead time kills momentum. Know your next sentence before you finish your current one.

---

## Live Demo Scripts

### Demo 1: Your First Prompt (9:00 AM)

**Setup:** Cursor open, empty new file, Claude open in browser sidebar.

**Script:**
> "I'm going to type a prompt into Cursor's Composer. Watch what happens."

Type in Cursor Composer (Cmd+I):
```
Create a single HTML file with:
- A dark background (#0a0a0a)
- My name "Kyle Rosebrook" centered on the screen
- A subtitle: "Staff Engineer & Workshop Instructor"
- White text, large font
No CSS files, no JS files. Just one HTML file.
```

> "I didn't write a single line of code. I described what I wanted. Watch."

Accept the generated code. Open in browser preview.

> "There it is. That's vibe coding. Your turn."

**Timing:** 3 minutes max.

---

### Demo 2: The ERROR-DEBUG Pattern (9:40 AM)

**Setup:** The landing page from Demo 1 is on screen.

**Script:**
> "Let me break something on purpose."

Add a broken style tag to the HTML manually (e.g., missing a closing brace).

> "Now the page looks wrong. What do I do?"

Open Claude. Type:
```
I have this HTML. The styles aren't working and I don't know why. Here's the code: [paste]
What's the bug and how do I fix it?
```

Show Claude's response identifying the issue.

> "I didn't debug that. I described the problem to someone who knows how. That's the ERROR-DEBUG pattern. Use it every time you see something broken."

**Timing:** 4 minutes.

---

### Demo 3: Deploying to Vercel (11:50 AM — Project 01)

**Setup:** Completed landing page in a GitHub repo.

**Script:**
> "This app works on my computer. Let's make it work for everyone."

Walk through:
1. Push to GitHub (or show that it's already there via Cursor's built-in Git)
2. Go to vercel.com → New Project → Import from GitHub
3. Select the repo → Deploy
4. Watch the build run (30–60 seconds)
5. Click the live URL

> "That URL works on your phone. It works in Tokyo. It's live. You shipped it."

**Timing:** 5 minutes. Make it dramatic.

---

### Demo 4: Environment Variables for API Keys (4:00 PM — Project 04)

**Setup:** A Claude API key obtained from console.anthropic.com.

**Script:**
> "API keys are like passwords. You never put them in your code — not even in a private repo. Here's why and here's how to do it right."

Show:
1. `console.anthropic.com` → API Keys → Create new key
2. Copy it (show it briefly, then hide it)
3. In Vercel: Project Settings → Environment Variables → Add `ANTHROPIC_API_KEY`
4. In code: show `process.env.ANTHROPIC_API_KEY` — never the key itself

> "If you ever accidentally commit an API key to GitHub, rotate it immediately. Bots scan GitHub for keys in real time. This is a real thing that happens to real developers. Now you know the right way."

**Timing:** 6 minutes.

---

## Debrief and Closing Ceremony Guide

### Why the Closing Ceremony Matters

Most participants will arrive today feeling like "non-technical people." They'll leave having built and deployed 4 real apps. That identity shift deserves a proper acknowledgment — not just "okay, we're done."

### Structure (30 min total)

#### Debrief (10 min)
Facilitate an open conversation with these exact questions, in this order:

1. "What clicked today that you didn't expect?"
   - Wait for genuine answers. Don't fill the silence.
   - Validate everything: "Yes, exactly." "That's a real insight."

2. "What was harder than you thought it would be?"
   - Normalize difficulty. "The API integration is hard for everyone the first time."
   - Reframe: "And you pushed through it."

3. "What do you want to build next?"
   - This is the energy-builder. People start talking over each other.
   - Write a few ideas on the whiteboard.

#### What's Next (10 min)
- Share the Discord invite link (QR code on screen)
- Mention the alumni newsletter: "I send a monthly email with tools, tips, and what alumni are building."
- Mention the post-workshop email sequence: "You'll get an email tonight with all your links, resources, and next steps."
- Hand out or show the post-workshop resources page

#### Closing (10 min)
Be genuine here. No script — but hit these beats:
- **Acknowledge what they did:** "You built and deployed 4 real apps in one day. Most developers haven't done that."
- **Name what changed:** "You came in here not knowing if you could do this. Now you know you can."
- **Invite them in:** "You're part of the Vibe Coding community now. We keep building together."
- **Group photo** (ask for consent — "Can I take a group photo for the website?")
- **Final send-off:** "Go build something."

---

*See also: `workshop-day-schedule.md` (timeline), `participant-workbook.md` (participant materials), `docs/playbooks/README.md` PB01 and PB03*
