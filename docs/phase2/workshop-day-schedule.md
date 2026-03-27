# Workshop Day Schedule

> Complete hour-by-hour timeline for the Vibe Coding Workshop. Use this alongside `instructor-guide.md` on the day.

---

## At a Glance

| Time | Block | Duration |
|------|-------|---------|
| 7:00 AM | Instructor arrives / room setup | 60 min |
| 8:00 AM | Doors open / informal arrivals | 30 min |
| 8:30 AM | Welcome + introductions | 30 min |
| 9:00 AM | Phase 1: Learn the Scales | 90 min |
| 10:30 AM | ☕ Break 1 | 15 min |
| 10:45 AM | Project 01: Personal Landing Page | 75 min |
| 12:00 PM | 🍕 Lunch | 45 min |
| 12:45 PM | Project 02: Mood Tracker with Charts | 75 min |
| 2:00 PM | ☕ Break 2 | 15 min |
| 2:15 PM | Project 03: Recipe Finder with API | 90 min |
| 3:45 PM | ☕ Break 3 | 15 min |
| 4:00 PM | Project 04: AI Chat Assistant | 90 min |
| 5:30 PM | Ship It: Deploy all 4 projects | 45 min |
| 6:15 PM | Show & Tell | 30 min |
| 6:45 PM | Debrief + Closing Ceremony | 30 min |
| 7:15 PM | Open networking / help desk | 45 min |
| 8:00 PM | Doors close | — |

**Total instructional time:** ~9.5 hours  
**Total breaks + transitions:** ~2.5 hours

---

## Detailed Schedule

---

### 7:00 AM — Instructor Setup (60 min)

**Goals:** Room is ready before the first participant arrives.

**Activities:**
- [ ] Configure tables in U-shape or clusters of 4 (not rows)
- [ ] Test projector and external display
- [ ] Verify WiFi speed (`speedtest.net` — need >25 Mbps per 20 users)
- [ ] Write WiFi SSID and password on the whiteboard
- [ ] Place printed participant workbooks at each seat
- [ ] Place printed prompting playbooks at each seat
- [ ] Have name tag station at the entrance
- [ ] Test your laptop: Cursor open, Claude logged in, v0 open in browser
- [ ] Load the welcome slide on screen
- [ ] Set up backup hotspot

**Instructor note:** Eat before you arrive. Once participants start coming in you won't have a free moment until lunch.

---

### 8:00 AM — Doors Open / Informal Arrivals (30 min)

**Goals:** Participants feel welcome and start getting comfortable.

**Activities:**
- Greet participants at the door by name (you know the list)
- Point them to name tags; let them make their own
- Have coffee/water available
- Slide on screen: "Find a seat. Open your laptop. Say hi."
- Circulate and ask: "Have you used Cursor before?" (gauges the room)

**Instructor note:** This time reveals your setup problems. If someone can't log in to Claude, handle it now. Don't wait until 9 AM.

**Transition cue:** At 8:28, call out: "Two minutes — let's get started!"

---

### 8:30 AM — Welcome + Introductions (30 min)

**Goals:** Participants know who's in the room, what they're building, and what "shipping" means.

**Activities:**

**8:30–8:35 — Opening (5 min)**
- "Good morning. My name is Kyle. Today you're going to ship 4 apps."
- "If you've never written a line of code before, you're in exactly the right place."
- "The only thing you need today is a working laptop and an idea you want to build."

**8:35–8:50 — Round of Introductions (15 min)**
- Each person: name + "what one thing do you want to build someday?"
- Keep it moving — 30–40 seconds per person max
- Write down interesting ideas on a whiteboard — they become examples throughout the day

**8:50–8:58 — Workshop Overview (8 min)**
- Show the agenda slide: four projects, one day
- Define "shipping": a live URL that anyone can visit
- Preview the tools: Claude (AI), Cursor (code editor), v0 (UI generator), Vercel (deploy), Supabase (database)
- "You do not need to understand how all of this works. You need to know how to use it."

**8:58–9:00 — Transition (2 min)**
- "Open Cursor. Open Claude in your browser. Let's learn to play."

**Instructor note:** The energy in this block sets the tone for everything. Bring it. Be genuinely excited. If they can feel that you believe in them, they'll believe in themselves.

---

### 9:00 AM — Phase 1: Learn the Scales (90 min)

**Goals:** Participants understand the prompting model and can produce their first working output.

**Sub-blocks:**

#### 9:00–9:20 — What Is Vibe Coding? (20 min)
- The mental model: intent → prompt → output → refine
- Show a live demo: type a prompt into Claude, get code, paste into Cursor, preview it
- "Vibe coding is not magic. It's a skill. You're going to practice it today."
- Cover the 4 prompt patterns from the prompting playbook:
  - DESCRIBE-FIRST
  - ERROR-DEBUG
  - REFINE
  - ARCHITECTURE

**Live demo script:** See `instructor-guide.md` → Live Demo Scripts section.

#### 9:20–9:40 — Hands-On: Your First Prompt (20 min)
- Participants write their first prompt in Cursor's Composer (Cmd+I)
- Prompt: "Create a simple HTML page with a dark background and my name in the center in large white text."
- Goal: everyone sees their code run in a browser preview within 20 minutes
- Circulate. Help. Celebrate the first one that shows up.

#### 9:40–10:00 — Prompt Patterns Workshop (20 min)
- Walk through the prompting playbook cheat sheet together
- Practice the ERROR-DEBUG pattern: intentionally break something, fix it with AI
- Practice the REFINE pattern: improve an existing output with a follow-up prompt

#### 10:00–10:20 — Q&A + Concept Check (20 min)
- Open floor for questions
- Cover: "What if the AI gets it wrong?" → always debug, never give up
- Cover: "What if my idea is too hard?" → scope it down, ship the MVP
- Preview Project 01

#### 10:20–10:30 — Buffer (10 min)
- Help anyone still struggling with Cursor setup
- Answer individual questions before the break

**Instructor note:** Watch for the participant who "gets it" immediately — they become a peer resource. Publicly acknowledge when that happens. "See how Alex just refined that prompt? That's the move."

**Transition cue:** "Take a 15-minute break. When you come back, we're building your first real project."

---

### 10:30 AM — Break 1 (15 min)

**Goals:** Rest, reset, let the concepts sink in.

- Keep coffee/water accessible
- Walk around and see if anyone has questions they're too shy to ask in a group
- Check: does everyone have a working Cursor window with a browser preview?

---

### 10:45 AM — Project 01: Personal Landing Page (75 min)

**Goals:** Participants build and deploy a personal landing page — their first shipped project.

**Project brief:** A single-page personal site with your name, a one-line bio, and links to your social profiles or portfolio. Mobile-friendly. Looks professional.

**Sub-blocks:**

#### 10:45–10:55 — Project 01 Kickoff (10 min)
- Show a finished example on screen
- Walk through the project worksheet in their workbooks
- "Your job in the next 60 minutes: ship this page to a real URL."

#### 10:55–11:50 — Build Time (55 min)
- Participants build independently, with help available
- Instructor circulates every 8–10 minutes
- Common block: participants overthink the design — remind them to prompt v0 first
- Milestone check at 11:30: "Who has a working page in Cursor? Who's deployed?"

#### 11:50–12:00 — Deploy to Vercel (10 min)
- Walk through Vercel deployment as a group (one person shares screen)
- "Push to GitHub → Vercel picks it up → live URL in 60 seconds."
- Celebrate the first live URL with the group

**Instructor note:** This is where the magic happens for the first time. When someone sees their name live at a real URL, their whole posture changes. Make a big deal of it.

**Transition cue:** "Lunch! You just shipped your first app. Let that sink in."

---

### 12:00 PM — Lunch (45 min)

**Goals:** Real break. Food. Decompression.

- Don't work through lunch — model the behavior you want
- Let conversations happen naturally; participants will compare what they built
- Be available for informal questions, but don't structure anything
- Use the last 5 minutes to do a personal energy check — how are you doing?

---

### 12:45 PM — Project 02: Mood Tracker with Charts (75 min)

**Goals:** Participants understand state, data persistence, and data visualization by building a functional mood tracker.

**Project brief:** A simple app that lets you log your mood each day (1–5 scale, optional note) and shows a chart of your mood over time.

**Sub-blocks:**

#### 12:45–12:55 — Project 02 Kickoff (10 min)
- Show finished example
- Introduce new concepts: state (data that changes), local storage, chart libraries
- "This is where you realize AI can write code you don't understand — and that's okay."

#### 12:55–1:50 — Build Time (55 min)
- More complex than Project 01 — participants will hit errors
- This is where the ERROR-DEBUG pattern pays off
- Milestone at 1:30: "Who has the mood form working? Who has the chart rendering?"

#### 1:50–2:00 — Group Review (10 min)
- One or two participants share their screen
- Point out: "Notice how they iterated. Prompt → error → debug prompt → fix. That's the loop."

**Instructor note:** Some participants will get stuck on the chart. Have a fallback prompt ready: "Add a simple bar chart using only vanilla JavaScript and no external libraries." Works every time.

---

### 2:00 PM — Break 2 (15 min)

- Stand up, move around, get fresh air if possible
- Check in with any participants who seem frustrated

---

### 2:15 PM — Project 03: Recipe Finder with API (90 min)

**Goals:** Participants integrate a real external API and handle errors gracefully.

**Project brief:** An app that takes an ingredient as input and fetches matching recipes from the Spoonacular API (or TheMealDB free API). Displays results with images and links.

**Sub-blocks:**

#### 2:15–2:30 — Project 03 Kickoff + API Concepts (15 min)
- What is an API? (explain as: "a way to ask another website for data")
- Show the TheMealDB API documentation — "you don't need to understand all of this, just the search endpoint"
- Walk through getting an API key (TheMealDB free tier or MealDB no-key endpoint)

#### 2:30–3:30 — Build Time (60 min)
- ARCHITECTURE pattern becomes important here
- Milestone at 3:00: "Who has search working? Who's getting results back?"

#### 3:30–3:45 — Deploy + Share (15 min)
- Push to GitHub, deploy to Vercel
- Add the URL to their participant workbook

**Instructor note:** API errors are frustrating but great teaching moments. When someone gets a CORS error or a 401, walk through it with the whole group if possible. "This is what real developers deal with. The AI can fix it."

---

### 3:45 PM — Break 3 (15 min)

- This is the energy trough of the day — keep break energy high
- Play music, be upbeat, remind them they have one project left

---

### 4:00 PM — Project 04: AI Chat Assistant (90 min)

**Goals:** Participants build and deploy an AI-powered chat interface connected to the Claude API.

**Project brief:** A simple chat UI that sends messages to Claude via the Anthropic API and displays the responses. Deployed to Vercel with the API key stored as an environment variable.

**Sub-blocks:**

#### 4:00–4:20 — Project 04 Kickoff + API Key Setup (20 min)
- Walk through getting a Claude API key from console.anthropic.com
- Explain environment variables: "a secret your app knows but that you never type in the code"
- Show Vercel environment variable setup
- Security note: "Never put your API key directly in your code. Ever."

#### 4:20–5:20 — Build Time (60 min)
- This project has the highest ceiling — participants can add personalities, system prompts, custom UIs
- Encourage them to make it their own
- Milestone at 5:00: "Who has a working chat interface?"

#### 5:20–5:30 — Final Deploy Check (10 min)
- Everyone pushes to GitHub, Vercel redeploys
- Walk through adding the API key as a Vercel environment variable
- Test with a live message

**Instructor note:** This project is the "wow" moment of the day. Seeing your own AI chat app live at a real URL is the thing they'll tell their friends about. Milk the energy.

---

### 5:30 PM — Ship It: Deploy All 4 Projects (45 min)

**Goals:** Every participant has 4 live URLs before the show & tell.

**Activities:**
- Go around the room: each person lists their 4 URLs in their workbook
- If anyone is missing a deployment, help them now
- Encourage participants to add their projects to their GitHub profile
- Create a shared doc / Discord thread with everyone's links

**Transition cue:** "Okay. Give me a show of hands — who has all 4 URLs live?" Celebrate.

---

### 6:15 PM — Show & Tell (30 min)

**Goals:** Participants see what each other built. Community forms.

**Format:**
- 3–4 volunteers share their screen and give a 2-minute demo of their favorite project
- Open the floor: "What was the prompt that surprised you the most?"
- "What would you build next?"

**Instructor note:** Keep this loose and fun. No judgment, no grades. Genuine celebration only.

---

### 6:45 PM — Debrief + Closing Ceremony (30 min)

**Goals:** Participants leave with a clear sense of what they learned, what's next, and that they belong in this community.

**Sub-blocks:**

#### 6:45–6:55 — Debrief (10 min)
- "What clicked today that you didn't expect?"
- "What was harder than you thought?"
- "What do you want to build next?"

#### 6:55–7:05 — What's Next (10 min)
- Hand out post-workshop resource sheet
- Share Discord invite link
- Mention the alumni newsletter
- "The tools are all free to keep using. The skills are yours."

#### 7:05–7:15 — Closing (10 min)
- Genuine thank-you to the room
- "You did something most people only talk about. You built things. You shipped them."
- Group photo (optional, with consent)
- Distribute feedback survey (Google Form QR code)

---

### 7:15 PM — Open Networking / Help Desk (45 min)

**Goals:** Informal Q&A and connection time.

- Stay available for one-on-one questions
- Help with any lingering deployment issues
- Exchange contacts with participants who want to stay in touch
- Start packing up the room

---

### 8:00 PM — Doors Close

- Room should be fully reset to original configuration
- All printed materials collected or distributed to participants
- WiFi credentials erased from whiteboard
- Post the feedback survey link in the Discord

---

## Emergency Buffer Slots

The schedule includes built-in buffers at:
- **10:20–10:30** — before Break 1 (10 min)
- **Lunch** — can run 12:45 PM if needed (15 min flex)
- **Break 3** — can be shortened to 10 min if behind
- **Ship It block** — the first 15 min can absorb overruns from Project 04

**If you're running 30+ minutes behind:** Cut the Show & Tell to 15 min (2 volunteers only) and shorten Debrief to 10 min. Do not cut the Closing Ceremony.

---

## Notes Column

Use this space on workshop day to capture what worked, what didn't, and participant quotes.

| Time | Note |
|------|------|
| | |
| | |
| | |
| | |

---

*See also: `instructor-guide.md` (day-of companion), `participant-workbook.md` (participant materials), `docs/playbooks/README.md` PB01 (Workshop Day Playbook)*
