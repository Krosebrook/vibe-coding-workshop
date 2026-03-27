# Vibe Code Jam — Annual Community Build Event

> A 24-hour community build event where anyone can ship something real using AI tools. Online, inclusive, and unapologetically beginner-friendly.

---

## What Is the Vibe Code Jam?

The Vibe Code Jam is an annual 24-hour online build event where participants use AI tools to ship a working app from idea to deployed URL. It's not a hackathon where 20-year CS veterans compete for prizes. It's a community event where a marketing manager and a junior developer and a self-taught designer all have an equal shot at shipping something they're proud of.

**The one rule:** Use AI tools to build. Ship before the clock runs out.

---

## Event Format

### Duration
24 hours, fully online.

### Tracks

| Track | Description | Who It's For |
|-------|-------------|-------------|
| **Solo Builder** | Build alone. Ship one app. | Workshop alumni, solo makers |
| **Team Builder** | Build with up to 3 people. | Friends, colleagues, Discordmates |
| **First Timer** | First time building anything. Special recognition category. | Absolute beginners |
| **Remix** | Take an existing app idea and make it better. | Alumni with working apps to extend |

### Timeline (Sample — Eastern Time)

| Time | Event |
|------|-------|
| Fri 8:00 PM | Kick-off livestream. Theme announced. Registration closes. |
| Fri 9:00 PM | Building begins. Discord support channels open. |
| Sat 8:00 AM | Mid-point check-in livestream. Show and tell. |
| Sat 7:00 PM | Final hour countdown begins. |
| Sat 8:00 PM | Time's up. Submissions close. |
| Sat 9:00 PM | Showcase livestream begins. |
| Sat 11:00 PM | Winners announced. |

---

## The Theme

Each Code Jam has a theme announced at kick-off — but it's a loose constraint, not a strict requirement. Past themes (planned):

| Year | Theme | Interpretation |
|------|-------|----------------|
| 2027 | "Solve your own problem" | Build something you would actually use |
| 2028 | "For someone who isn't you" | Build something for a specific other person |
| 2029 | "Remix the mundane" | Take a boring daily task and make it delightful |

---

## Judging

All submissions are judged by a panel of 3–5 judges drawn from workshop alumni, instructors, and sponsors.

### Criteria

| Criterion | Weight | Description |
|-----------|--------|-------------|
| **Ships** | 30% | Does it have a live URL? Does it work? |
| **Solves Something** | 25% | Is there a real use case? Would you use it? |
| **Vibe** | 20% | Is it fun, surprising, beautiful, or weird in a good way? |
| **AI-First Approach** | 15% | Did AI do the heavy lifting? (We want this to be high.) |
| **Accessible** | 10% | Can someone with a disability use it? |

### What We Don't Judge On
- Code quality (don't show us the code unless you want to)
- Technology choices (HTML or Next.js — doesn't matter)
- Prior experience

---

## Recognition

No cash prizes in year one — recognition only. We may revisit as sponsorship grows.

| Category | Recognition |
|----------|------------|
| Best Solo Build | Trophy + feature on the website |
| Best Team Build | Trophy + feature on the website |
| Best First Timer | Trophy + free seat at next workshop |
| Most Unexpected | Community choice + feature |
| Best Vibe | Community choice + feature |

---

## Logistics

### Registration

- Opens 4 weeks before the event
- Free to participate (no cost)
- Optional Discord membership for support channels
- Teams register together; solo builders register solo

### Submission

Participants submit via a form at the end of the 24 hours:

```json
{
  "projectName": "string",
  "liveUrl": "string (required)",
  "githubUrl": "string (optional)",
  "description": "string (max 280 characters)",
  "track": "solo | team | first-timer | remix",
  "teamMembers": ["string"],
  "aiToolsUsed": ["claude", "cursor", "v0", "chatgpt", "..."],
  "wouldYouUseThis": "boolean"
}
```

### Support During the Event

Live Discord channels during the 24 hours:

| Channel | Purpose |
|---------|---------|
| `#general` | General conversation |
| `#help-im-stuck` | Real-time debugging help |
| `#show-your-progress` | Share screenshots and updates |
| `#find-a-team` | Team up with other participants |
| `#resources` | Links to APIs, templates, docs |

---

## Operations Playbook

### 8 Weeks Before

- [ ] Announce event date and open registration
- [ ] Open team formation Discord channel
- [ ] Recruit judges (min 3, target 5)
- [ ] Confirm streaming platform (YouTube / Twitch)
- [ ] Prepare submission form (Typeform or custom)

### 4 Weeks Before

- [ ] Send reminder to registered participants
- [ ] Confirm all judges
- [ ] Prepare kick-off livestream script
- [ ] Test streaming setup
- [ ] Prepare showcase presentation template

### 1 Week Before

- [ ] Send logistics email to all registered participants
- [ ] Set up Discord channels
- [ ] Test submission form
- [ ] Prepare mid-point check-in script
- [ ] Brief judges on scoring rubric

### Day Before

- [ ] Final test of streaming setup
- [ ] Verify Discord channels are active
- [ ] Prepare theme reveal (keep it secret until kick-off)
- [ ] Confirm support volunteers for Discord

### During the Event

- [ ] Go live at kick-off (8 PM ET)
- [ ] Announce theme
- [ ] Monitor `#help-im-stuck` every 2 hours; assist or triage
- [ ] Mid-point stream at 8 AM
- [ ] Send 1-hour warning announcement
- [ ] Close submissions at 8 PM
- [ ] Showcase stream at 9 PM

### After the Event

- [ ] Announce winners at showcase
- [ ] Post all project links to website/newsletter
- [ ] Email all participants a "You shipped it" message
- [ ] Share judging scores with participants (private)
- [ ] Write retrospective blog post
- [ ] Update this document with lessons learned

---

## Year One Goals

| Goal | Target |
|------|--------|
| Registered participants | 100 |
| Submissions | 60+ |
| First-timer track submissions | 20+ |
| Countries represented | 10+ |
| Livestream viewers | 500 |

---

*See also: [Regional Workshops](regional-workshops.md) | [University Partnerships](university-partnerships.md) | [Phase 4 Overview](../README.md)*
