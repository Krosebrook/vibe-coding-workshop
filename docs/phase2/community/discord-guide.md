# Alumni Discord Server Guide

> How to set up and manage the Vibe Coding Workshop alumni Discord server.

---

## Why Discord

Discord is where builders hang out. It's free, works on every device, has great notification controls, and supports community features like roles, channels, and bots.

Alumni can ask questions, share projects, get unstuck, and celebrate each other — asynchronously, at their own pace.

---

## Step 1: Create the Server

1. Open Discord (desktop app or browser at discord.com)
2. Click the **+** button in the left sidebar (below your servers)
3. Select **Create My Own**
4. Choose **For me and my friends** (you'll configure it properly after creation)
5. Name it: **Vibe Coding Workshop**
6. Upload a server icon (the workshop logo or a purple `{ }` icon works well)
7. Click **Create**

---

## Step 2: Server Structure

Delete the default channels and create this structure:

### Category: 👋 Welcome

| Channel | Type | Purpose |
|---------|------|---------|
| `#welcome` | Text | Server rules + intro message, read-only |
| `#introduce-yourself` | Text | New members post their name + what they built |
| `#announcements` | Text | Official updates from Kyle, read-only for members |

### Category: 🏗️ Building

| Channel | Type | Purpose |
|---------|------|---------|
| `#show-your-work` | Text | Share projects, URLs, screenshots — the main feed |
| `#help` | Text | Ask for help with code, prompts, or tools |
| `#prompt-sharing` | Text | Share prompts that worked surprisingly well |
| `#resources` | Text | Links to useful tools, tutorials, articles |

### Category: 💬 Community

| Channel | Type | Purpose |
|---------|------|---------|
| `#general` | Text | Casual conversation, anything goes |
| `#off-topic` | Text | Non-coding chat |

### Category: 🔔 Workshop Alumni (Cohort-Specific)

Create a new text channel for each cohort after it runs:

| Channel | Purpose |
|---------|---------|
| `#cohort-summer-2026` | Permanent channel for Summer 2026 alumni |
| `#cohort-fall-2026` | (add when that cohort runs) |

Cohort channels let alumni stay connected with their specific group.

---

## Channel Descriptions and Rules

### `#welcome` — Pinned Message Template

```
Welcome to the Vibe Coding Workshop community 🚀

This is the alumni Discord for people who've been through the workshop.
You built things. You shipped them. This is where you keep going.

Rules (short version):
1. Be kind. No exceptions.
2. Share your work — even if it's rough. Especially if it's rough.
3. Ask questions. There are no dumb questions here.
4. Help others when you can.

Start by introducing yourself in #introduce-yourself.

— Kyle
```

### `#introduce-yourself` — Starter Prompt (pin this)

```
Tell us:
- Your name
- What cohort you attended (e.g., Summer 2026)
- One project URL from workshop day
- What you want to build next
```

### `#show-your-work` — Pinned note

```
This is the main feed. Share anything you build — workshop projects,
new ideas, experiments, things that almost work.

Format (optional but helpful):
🔗 [URL]
📝 What it does: [one sentence]
💡 What I used: [tools]
🙋 Would love feedback on: [specific thing]
```

---

## Bot Recommendations

### MEE6 (Recommended)

MEE6 handles moderation, auto-roles, welcome messages, and leveling. Free tier covers everything you need.

**Setup:**
1. Go to [mee6.xyz](https://mee6.xyz)
2. Click **Add to Discord**
3. Select your server
4. Authorize

**Recommended MEE6 settings:**

| Feature | Setting |
|---------|---------|
| Welcome message | "Welcome to the Vibe Coding community, {member}! Introduce yourself in #introduce-yourself." |
| Auto-role on join | None (manual review is fine for a small community) |
| Auto-moderation | Block links in `#welcome` and `#announcements` |
| Leveling | Enable in `#show-your-work` and `#general` — encourages participation |

### Carl-bot (Alternative)

Carl-bot is more powerful than MEE6 for reaction roles and advanced moderation. Not necessary until the server grows.

---

## Onboarding Flow for New Alumni

Every new workshop participant gets added to Discord as part of the closing ceremony.

**Workshop day onboarding:**
1. During the Closing Ceremony, display the Discord invite QR code
2. Kyle sends the invite link in the `#announcements` channel after posting it in the closing email
3. Post a welcome message in `#introduce-yourself` for the new cohort

**Automated flow (via MEE6):**
1. New member joins → MEE6 sends DM: "Welcome! Say hi in #introduce-yourself."
2. New member posts in `#introduce-yourself` → Kyle or a moderator reacts with 🚀
3. After 48 hours, MEE6 can send a reminder if they haven't posted

---

## Community Engagement Strategies

### Weekly Prompts (Post every Monday)

Post a prompt in `#show-your-work` to spark activity:

```
🏗️ Build Challenge Monday

What are you working on this week?
Share a URL, a screenshot, or just tell us in a sentence.
```

### "Alumni Spotlight" (Monthly)

Feature one alumni's project in `#announcements`:

```
🌟 Alumni Spotlight — [Name]

[Name] built [project description] and deployed it to [URL].
[One quote from them about the experience.]

[screenshot or link]
```

### "Prompt of the Week" (Post every Wednesday)

Share a prompt that worked particularly well:

```
💡 Prompt of the Week

This prompt from our archives produces great results for [use case]:

---
[prompt]
---

What would you use this for?
```

---

## Monthly Event Ideas

| Month | Event |
|-------|-------|
| Month 1 (post-cohort) | Virtual Show & Tell — alumni demo their projects (30 min Zoom) |
| Month 2 | Prompt Workshop — 60 min live session on a specific technique |
| Month 3 | Build Challenge — same prompt, everyone builds something different |
| Month 4 | Alumni Interview — Kyle interviews one alumnus about what they built |
| Month 6 | 6-Month Showcase — everyone shares what they've built since the workshop |

---

## Moderation Guidelines

### The Standard

Be direct but kind. Remove content that's harmful or off-brand. Give warnings before bans.

### What to Remove Immediately

- Spam or promotional content (not your own projects)
- Anything discriminatory or harassing
- API keys, passwords, or sensitive credentials posted accidentally

### What Gets a Warning First

- Repeated off-topic content in the wrong channel
- Dismissive or condescending responses to beginners' questions
- Link drops without context

### Escalation

| Offense | Action |
|---------|--------|
| First violation | DM warning from Kyle or moderator |
| Second violation | 24-hour timeout |
| Third violation | Server ban |
| Immediate ban offenses | Hate speech, doxxing, harassment |

---

## Invite Link Management

- Create a permanent invite link: Server Settings → Invites → Create → Never expires
- Use this link in all emails, the workshop closing ceremony, and the website
- Periodically check that the link is still active

---

*See also: `alumni-newsletter-template.md`, `docs/phase2/email-sequences/post-workshop-followup.md`*
