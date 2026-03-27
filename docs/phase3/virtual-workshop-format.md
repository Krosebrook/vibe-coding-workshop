# Virtual Workshop Format

> A complete guide for delivering the Vibe Coding Workshop remotely — everything from tool setup to facilitating live builds over video.

---

## Overview

The virtual format delivers the same 4-project, one-day experience as the in-person workshop, adapted for synchronous video delivery. It targets the same audience (non-technical people who want to build real apps) with a few key adaptations:

- **Platform:** Zoom (or equivalent) with breakout rooms for small-group troubleshooting
- **Capacity:** 20–30 participants (same as in-person)
- **Duration:** 8 hours live + 1 hour async wrap-up
- **Tech bar:** Participants need only a laptop and internet — no physical setup required

---

## Why Virtual Works for This Workshop

Vibe coding is inherently screen-based. Participants are working in Cursor and Claude — they can do that from anywhere. The in-person energy is real, but the fundamentals translate well to video because:

1. Screen sharing replaces looking over shoulders
2. Chat and emoji reactions surface participation
3. Breakout rooms replicate the "sit next to a neighbor" fallback
4. Recorded sessions let participants catch up on missed moments

---

## Platform Requirements

| Tool | Purpose | Notes |
|------|---------|-------|
| Zoom (Business/Pro) | Main delivery | Needs breakout rooms, screen share, recording |
| Discord server | Community + support | Workshop-day channel for links, live help |
| GitHub Classroom | Participant repos | Same as in-person |
| Loom | Pre-recorded explainers | Optional — for async segments |
| Miro or FigJam | Visual exercises | Optional — for icebreakers and planning |

---

## Pre-Workshop Setup (Instructor)

### 2 Weeks Before

- [ ] Create Zoom meeting with waiting room enabled
- [ ] Set up breakout rooms (pre-assign: 4–5 rooms of 5–6 participants each)
- [ ] Test screen sharing with a co-facilitator
- [ ] Create Discord workshop-day channel
- [ ] Send participant onboarding email (see [PB09 — Virtual Workshop Delivery](../playbooks/README.md#pb09---virtual-workshop-delivery))
- [ ] Record a 5-minute "here's how today works" video for late joiners

### 1 Week Before

- [ ] Host a 15-min optional "Tech Check" Zoom call
  - Test each participant's screen share
  - Verify Cursor + Claude accounts work
  - Check microphone and camera
- [ ] Confirm all accounts are ready (GitHub, Cursor, Claude, Vercel, Supabase)

### Day Before

- [ ] Send "See you tomorrow" email with:
  - Zoom link (add to calendar)
  - Discord join link
  - Final tool checklist
  - "Have your app idea ready — one sentence"

---

## Day-Of Schedule

All times are Eastern. Adjust for your cohort's timezone.

### 9:00 AM — Open Room + Welcome (30 min)

**9:00–9:05 — Open the Zoom waiting room**
- Admit participants as they join
- Play lo-fi background music to set the vibe
- Have the workshop welcome slide visible

**9:05–9:20 — Intros**
- Each participant: name, where they're calling from, one-sentence app idea
- Instructor: brief bio, today's goals, "what shipping means today"

**9:20–9:30 — Tech and format walkthrough**
- Show screen layout: Cursor on left, Claude on right
- Explain Discord: drop links here, ask questions here
- Breakout room explainer: "When you see 'Go to your room', that's a small group work session"

---

### 9:30 AM — Phase 1: Learn the Scales (60 min)

**Instructor screen share throughout.**

Topics (same as in-person):
- How AI coding tools work — the model doesn't "know" your project
- Hallucination: what it is, how to spot it
- The Prompt → Output → Refine loop (live demo)
- Prompting for structure, not just output

**Virtual adaptations:**
- Use chat for real-time reactions: "Drop a 🔥 if this just clicked"
- Pause every 15 min: "Any questions? Drop them in chat or unmute."
- Do the "bad prompt → good prompt" demo — this is the key aha moment

---

### 10:30 AM — Project 01: Personal Landing Page (60 min)

**Breakout rooms: 4–5 rooms of 5–6 participants.**

- Assign each room a co-facilitator (TA or experienced participant)
- Give the T01 prompt on screen before breakouts
- Check in on each room every 15 min via host controls
- After 50 min: bring everyone back for a 10-min share-out

**Share-out prompt:**
- "Drop your Cursor screenshot in the Discord channel"
- Pick 2–3 to demo on screen

---

### 11:30 AM — Project 02: Mood Tracker (60 min)

**Repeat breakout format.**

- Share T02 prompt on screen
- This is the first JavaScript project — expect more questions
- Use Discord for async help (participants can help each other)
- Instructor circulates between rooms via Zoom co-host join feature

---

### 12:30 PM — Lunch Break (45 min)

- Keep the Zoom open but go on mute
- Pin "Back at 1:15 PM" message in chat
- Share this week's prompt tip in Discord during break
- Optional: Stay on for anyone who wants to keep building

---

### 1:15 PM — Project 03: Recipe Finder / API (75 min)

**Full group for the API intro, then breakouts.**

- 15-min full group: API concepts, the restaurant analogy
- Breakout: 60 min with T03 template
- Instructor visits each room — show browser DevTools over screen share

---

### 2:30 PM — Project 04: AI Chat Assistant (90 min)

**Most open-ended project — participants choose their AI's personality.**

- Brief full group: Claude API setup walkthrough (15 min)
- Extended breakout: 75 min
- This is where participants diverge most — celebrate the variety
- TAs should be most active here: this project has the most variation

---

### 4:00 PM — Ship It Ceremony (30 min)

**Full group back together.**

1. Everyone deploys to Vercel (15 min with instructor screen share)
2. Each participant pastes their live URL in the Discord channel
3. Instructor pulls up 3–4 URLs and gives them a "first look" live
4. Group celebration — drop your emoji in chat

---

### 4:30 PM — Closing (30 min)

- Feedback form link pinned in chat (5 min to fill out before leaving)
- Recap: what you built, what you learned, what's possible now
- Post-workshop resources email will land tonight
- "One thing to build this week" — ask 3 participants to share

---

## Co-Facilitator (TA) Guide

If you have a co-facilitator (TA), here's their role:

| Time | TA Role |
|------|---------|
| Pre-workshop | Co-host tech check call, monitor Discord setup |
| Welcome | Monitor chat, admit late arrivals from waiting room |
| Phase 1 | Watch chat for questions, surface the best ones to instructor |
| Projects 01–02 | Own one or two breakout rooms, provide direct support |
| Lunch | Moderate Discord channel |
| Projects 03–04 | Rotate between breakout rooms as needed |
| Ship It | Help participants who get stuck on Vercel deploy |
| Closing | Monitor feedback form completion, close Discord channel after |

**No TA? That's okay.** Do the breakout rooms without room-specific support. Use Discord as the async help channel. The participants will help each other more than you expect.

---

## Handling Common Virtual Problems

### Participant Camera/Mic Issues
- Always have backup: "If you can't get your mic working, use chat — that's fine."
- Never hold up the whole group for one person's tech issue
- DM them the Zoom link to rejoin if they drop

### Participant Gets Lost / Behind
- Don't pause the group for one participant
- Breakout rooms exist for this: assign the stuck participant to a TA room
- If someone is too far behind: "Keep working — the recording will help."

### Zoom Drops (Instructor)
- Co-host takes over immediately
- Post in Discord: "Back in 2 min — keep building"
- Keep a backup Zoom link ready (alternate meeting ID)

### Participant Can't Deploy
- Skip the personal deploy for now; deploy together from instructor's screen
- Share the Vercel docs link in Discord for later
- "You shipped it locally — that counts today."

---

## Virtual vs. In-Person: Key Differences

| Aspect | In-Person | Virtual |
|--------|-----------|---------|
| Energy | Organic, room energy | Built through chat, emoji, music |
| Troubleshooting | Walk over to them | Zoom breakout + screen share |
| Focus | Physical presence | Camera policy (cameras on recommended) |
| Networking | Natural sidebars | Facilitated intro, Discord |
| Tech setup | Check in-room | Pre-workshop tech check call |
| Ship It moment | Read URL aloud together | Paste URLs in Discord channel |

---

## Post-Workshop (Virtual-Specific)

- [ ] Send recording link within 24 hours (Zoom cloud recording)
  - Trim intro/break/closing if needed
  - Password-protect and share with participants only
- [ ] Archive Discord workshop-day channel (pin or export key links)
- [ ] Run the same PB08 follow-up sequence as in-person

---

*Owner: Kyle Rosebrook · Part of [Phase 3 documentation](./README.md)*
