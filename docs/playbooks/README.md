# Playbooks

> Operational playbooks for running the Vibe Coding Workshop and managing the project.

---

## Playbook Index

| Playbook | Purpose |
|----------|---------|
| [PB01 — Workshop Day Playbook](#pb01---workshop-day-playbook) | Run a flawless workshop day |
| [PB02 — Waitlist to Registered Playbook](#pb02---waitlist-to-registered-playbook) | Convert waitlist to paid seats |
| [PB03 — Incident Response Playbook](#pb03---incident-response-playbook) | Handle day-of problems |
| [PB04 — Content Publishing Playbook](#pb04---content-publishing-playbook) | Publish blog posts and updates |
| [PB05 — Site Update Playbook](#pb05---site-update-playbook) | Make changes to index.html safely |
| [PB06 — New Cohort Launch Playbook](#pb06---new-cohort-launch-playbook) | Launch a new workshop cohort |
| [PB07 — Participant Onboarding Playbook](#pb07---participant-onboarding-playbook) | Prepare participants for the day |
| [PB08 — Post-Workshop Follow-Up Playbook](#pb08---post-workshop-follow-up-playbook) | Follow up after a workshop |
| [PB09 — Virtual Workshop Delivery](#pb09---virtual-workshop-delivery) | Run a live remote/virtual cohort |
| [PB10 — Corporate Training Delivery](#pb10---corporate-training-delivery) | Deliver a corporate team engagement |
| [PB11 — Guest Instructor Onboarding](#pb11---guest-instructor-onboarding) | Onboard and prepare a guest instructor |
| [PB12 — Referral & Affiliate Operations](#pb12---referral--affiliate-operations) | Manage referrals, commissions, and partner payouts |

---

## PB01 — Workshop Day Playbook

### Overview
Everything that needs to happen on workshop day to ensure participants have a great experience.

---

### T-minus 1 Week

- [ ] Confirm room booking at College of Lake County
- [ ] Send final details email to all participants (see template in `docs/templates/`)
- [ ] Verify all 4 project starter files are in the shared GitHub Classroom
- [ ] Test Claude, Cursor, v0, Vercel, Supabase accounts with fresh credentials
- [ ] Print participant checklists (1 per person)
- [ ] Order catering (lunch + coffee) if applicable
- [ ] Prepare slide deck (see `docs/presentations/`)
- [ ] Create workshop day Discord channel for live support

---

### T-minus 24 Hours

- [ ] Send "See you tomorrow!" reminder email
  - Start time, exact address, parking info
  - "What to have installed" final check
  - What to bring (laptop charger, notebook, idea)
- [ ] Charge all equipment
- [ ] Prepare your own machine: fresh Cursor install, all accounts logged in
- [ ] Print name tags
- [ ] Prepare welcome slide on screen

---

### Morning Setup (T-minus 90 min)

- [ ] Arrive 90 minutes before start
- [ ] Set up room: tables configured for seeing each other's screens
- [ ] Test projector/screen
- [ ] Verify WiFi credentials and speed (run speedtest.net)
- [ ] Have backup hotspot ready
- [ ] Write WiFi credentials on whiteboard/screen
- [ ] Put printed checklists at each seat
- [ ] Test audio if demos will be projected

---

### Welcome (0:00 – 0:30)

**Script outline:**
1. Welcome and intro (5 min)
   - "You're going to ship 4 apps today."
   - "If you've never written a line of code — perfect."
2. Quick round of introductions: name + "what app idea did you come with?" (15 min)
3. Tool setup check — everyone should have Cursor + Claude open (5 min)
4. Workshop overview — phases, projects, what "shipping" means today (5 min)

**Watch for:** Anyone who can't get Cursor or Claude open. Pair them with a neighbor or help directly.

---

### Phase 1: Learn the Scales (0:30 – 1:30)

**Topics:**
- How AI coding tools work (the model doesn't "know" your project — you set context)
- What hallucination is and how to recognize it
- The Prompt → Output → Refine loop (live demo)
- Prompting for structure, not just output

**Live Demo:**
1. Open a fresh Cursor window
2. Ask Claude to build a basic page — narrate your thought process aloud
3. Make it bad on purpose (vague prompt), then fix it (specific prompt)
4. Show how to read and understand the code you didn't write

**Timing:** Keep this to 60 min. Start Project 01 no later than 1:30.

---

### Phase 2: Project 01 — Personal Landing Page (1:30 – 2:30)

- Give participants 5 minutes to think about their page
- Walk through the T01 template prompt together
- Build your own alongside theirs (pair-program with the room)
- At 30 min, ask 2–3 participants to share what they have
- Help stuck participants: most common issue is the prompt being too vague

---

### Phase 3: Project 02 — Mood Tracker (2:30 – 3:30)

- Quick 10-min intro to JavaScript state concepts (no code — analogy only)
- Walk through T02 template prompt
- Focus on: adding localStorage, the Chart.js import
- Encourage participants to swap the mood tracker for their own idea

---

### Lunch Break (3:30 – 4:15)

**Facilitate a discussion:**
- "What's surprised you so far?"
- "What does your app idea look like after this morning?"
- "What's the thing you want to build when you get home?"

---

### Phase 4: Project 03 — Recipe Finder / API (4:15 – 5:30)

- Intro to APIs (15 min): The restaurant analogy
- Walk through T03 template
- Key teaching moment: reading API documentation
- Show how to use browser DevTools to inspect API responses

---

### Phase 5: Project 04 — AI Chat (5:30 – 7:00)

- More freedom: participants choose their assistant's personality
- Demo the Claude API setup with environment variables
- Let participants customize — this is where the vibe really clicks
- Instructors circulate constantly in this phase

---

### Ship It Ceremony (7:00 – 7:30)

- Everyone deploys to Vercel (15 min)
- Each person reads their live URL aloud
- Share live URLs in the Discord channel
- Group photo

---

### Closing (7:30 – 8:00)

- Feedback form link on screen (5 min to fill out)
- Post-workshop resources email (already scheduled to send tonight)
- "What do you build next?"
- Celebrate everyone

---

### Post-Day Checklist

- [ ] Send post-workshop email (use PB08)
- [ ] Review feedback forms
- [ ] Note what broke, what went over time, what participants loved
- [ ] Archive participant GitHub repos
- [ ] Log lessons learned in `docs/playbooks/lessons-learned.md`

---

## PB02 — Waitlist to Registered Playbook

### Overview
Convert waitlist sign-ups to paid registrations when a new cohort opens.

### Steps

1. **Announce cohort opening** to entire waitlist (48 hrs early access)
   - Email subject: "Your spot is ready — [cohort name] is open"
   - Include: date, location, price, link to registration

2. **Early bird window** (48 hours)
   - Early bird price active for first 48 hours
   - Monitor sign-ups

3. **General opening** (after 48 hours)
   - Send email to remaining waitlist
   - Update website with "Now Open" badge

4. **Fill confirmation** (when 20 seats sold)
   - Email remaining waitlist: "Sold out — you're on the next cohort list"
   - Close registration link

5. **Pre-workshop onboarding** (2 weeks before)
   - Use PB07

---

## PB03 — Incident Response Playbook

### Scenarios and Responses

#### WiFi Down

**Immediate:**
1. Activate personal hotspot on instructor's phone
2. Share credentials with room
3. Test speed — if too slow for class, have participants pair

**Prevention:** Always have hotspot ready. Test WiFi day before.

---

#### Participant Can't Get Tool Working

**Immediate:**
1. Pair them with nearest neighbor (same OS preferred)
2. If truly stuck, provide workshop machine as backup

**Prevention:** Pre-workshop setup guide (PB07) + follow-up call for anyone who doesn't confirm setup.

---

#### API Is Down (During Project 03)

**Immediate:**
1. Switch to backup API from the free APIs list in G07
2. Have TheMealDB pre-tested as primary backup (no key needed)

**Prevention:** Test all APIs the morning of the workshop.

---

#### Participant Is Frustrated / Wants to Quit

**Approach:**
1. One-on-one: "What's the thing you wanted to build today?"
2. Reframe the struggle: "Getting unstuck with AI is the skill — you're learning it right now."
3. Simplify their goal: "What's the smallest version of that?"
4. Sit with them for 10 minutes

---

#### Room Double-Booking / Venue Issue

**Backup plan:**
- Pre-arranged agreement with a local coffee shop with strong WiFi
- Virtual fallback: Zoom meeting + participants work from home

---

## PB04 — Content Publishing Playbook

### Blog Posts

1. Draft in Google Docs (share with Kyle for review)
2. Add to `docs/` as a Markdown file for version control
3. Kyle approves via PR review
4. Publish to website (Phase 1 roadmap item)

### Social Media

1. Workshop day: post live updates with participant permission
2. Photos: get verbal consent before sharing photos of participants
3. Ship It moment: post with participant's app URL (their permission)
4. Weekly: one tip from the skills library

---

## PB05 — Site Update Playbook

### For Any Change to `index.html`

1. **Create a branch:**
   ```bash
   git checkout -b feat/describe-change
   ```

2. **Make the change locally and test:**
   - Open `index.html` in browser
   - Test on mobile (Chrome DevTools responsive mode)
   - Check keyboard navigation
   - Run Lighthouse audit

3. **Commit and push:**
   ```bash
   git add index.html
   git commit -m "type: describe change"
   git push origin feat/describe-change
   ```

4. **Open PR on GitHub:**
   - Include before/after screenshots for visual changes
   - Reference any related issue

5. **Get review and merge**

---

## PB06 — New Cohort Launch Playbook

### 8 Weeks Before

- [ ] Confirm venue and date
- [ ] Update `index.html` with new cohort details
- [ ] Set up registration form (email link or Typeform)
- [ ] Prepare waitlist announcement email

### 4 Weeks Before

- [ ] Send waitlist announcement
- [ ] Post on social media
- [ ] Track registrations

### 2 Weeks Before

- [ ] Send participant onboarding email (PB07)
- [ ] Confirm room setup
- [ ] Test all tech (API keys, tools)

### 1 Week Before

- [ ] Send "see you soon" email
- [ ] Finalize headcount for catering

### Day Before

- [ ] Final logistics check
- [ ] Print materials

---

## PB07 — Participant Onboarding Playbook

### 2 Weeks Before Workshop

**Email: "Get Ready for Workshop Day"**

Contents:
- Confirm registration
- Accounts to create (GitHub, Cursor, Claude, Vercel, Supabase)
- Software to install (Cursor)
- What to bring
- What NOT to do (don't try to learn coding beforehand)
- Your workshop day idea prompt: "Think of one thing you'd build if you could build anything."

### 1 Week Before

**Email: "Final Setup Check"**

Contents:
- Did you create all accounts?
- Verify Cursor installed
- Address, parking, start time
- Contact for questions

### Day Before

**Email: "See You Tomorrow"**

Contents:
- Start time
- Exact address + Google Maps link
- Bring: laptop, charger, your idea
- WiFi will be provided
- Excitement! ✨

---

## PB08 — Post-Workshop Follow-Up Playbook

### Same Night

**Email: "You shipped it. 🚀"**

Contents:
- Congratulations on 4 deployed apps
- Their GitHub repo link
- Discord alumni community link
- Post-Workshop guidebook link
- Feedback form link

### One Week After

**Email: "How's the building going?"**

Contents:
- Check in on solo projects
- Share this week's prompt tip
- Remind about Discord community

### One Month After

**Email: "What did you build since the workshop?"**

Contents:
- Prompt to share what they've built
- Preview of next cohort (if they have friends to refer)
- "What's your next project?"

---

---

## PB09 — Virtual Workshop Delivery

### Overview
Everything needed to run a virtual (remote) Vibe Coding Workshop cohort — from pre-event setup through the live day and follow-up.

For the full guide, see [docs/phase3/virtual-workshop-format.md](../phase3/virtual-workshop-format.md).

---

### Pre-Event Checklist (2 Weeks Before)

- [ ] Create Zoom meeting with waiting room enabled
- [ ] Set up breakout rooms (4–5 rooms of 5–6 participants each)
- [ ] Create Discord workshop-day channel
- [ ] Send participant onboarding email (accounts, tech setup, "what to expect")
- [ ] Record 5-min "how today works" video for late joiners
- [ ] Schedule optional 15-min tech check call for the week before

### Pre-Event Checklist (1 Week Before)

- [ ] Host tech check Zoom call
  - Test participant screen share
  - Verify Cursor + Claude accounts work
  - Check audio/camera for each participant
- [ ] Confirm all participant accounts are ready (GitHub, Cursor, Claude, Vercel)
- [ ] Assign TAs to specific breakout rooms

### Day Before

- [ ] Send final email: Zoom link, Discord link, tool checklist, "have your app idea ready"
- [ ] Test Zoom meeting and breakout room config
- [ ] Verify Discord channel is live and accessible

---

### Day-Of Runsheet

| Time (ET) | Segment | Notes |
|-----------|---------|-------|
| 8:30 AM | Open Zoom, admit TAs | Sound check, slide ready |
| 9:00 AM | Open waiting room | Admit participants, lo-fi music |
| 9:00–9:30 | Welcome + Intros | Screen share workshop slide deck |
| 9:30–10:30 | Phase 1: Learn the Scales | Full group, instructor screen share |
| 10:30–11:30 | Project 01 breakouts | Breakout rooms, TA-led |
| 11:30–12:30 | Project 02 breakouts | Breakout rooms, TA-led |
| 12:30–1:15 | Lunch (Zoom open) | Pin "Back at 1:15" in chat |
| 1:15–2:30 | Project 03 (API) | Full group intro, then breakouts |
| 2:30–4:00 | Project 04 (AI Chat) | Extended breakouts |
| 4:00–4:30 | Ship It Ceremony | Full group, paste URLs in Discord |
| 4:30–5:00 | Closing | Feedback form, resources, celebration |

---

### Post-Event Checklist

- [ ] Send Zoom recording link to all participants (within 24 hours)
- [ ] Archive Discord workshop-day channel
- [ ] Run PB08 follow-up sequence
- [ ] Log any tech or facilitation issues for next cohort

---

## PB10 — Corporate Training Delivery

### Overview
Step-by-step for delivering the Vibe Coding Workshop to a private corporate team. Covers pre-engagement, day-of, and follow-up.

For the full guide, see [docs/phase3/corporate-training-guide.md](../phase3/corporate-training-guide.md).

---

### Pre-Engagement Checklist (6 Weeks Before)

- [ ] Discovery call with team lead:
  - Confirm format (in-person or virtual), date, headcount
  - Collect 2–3 internal problem statements for customized prompts
  - Identify IT contact for tool approval
- [ ] Draft customized project prompts using their context
- [ ] Send engagement letter / SOW
- [ ] Receive 50% deposit

### Pre-Engagement Checklist (4 Weeks Before)

- [ ] Send participant pre-work email (accounts, setup, app idea prompt)
- [ ] Confirm IT approval for Cursor and Claude
- [ ] Finalize customized templates for 2 of the 4 projects

### Pre-Engagement Checklist (2 Weeks Before)

- [ ] Host optional participant tech check (virtual only)
- [ ] Confirm headcount for catering (in-person)
- [ ] Review customized prompts with team lead

### 1 Week Before

- [ ] Final logistics email to all participants
- [ ] Confirm venue / Zoom setup

---

### Day-Of Adaptations

**Welcome (Corporate Version):**
> "Today you're not here to become a developer. You're here to understand what's possible — and to have proof that you can prototype ideas yourself."

**Ship It (Corporate Version):**
- Invite team lead to final 30 minutes
- Have participants share live URLs in company Slack channel
- Frame: "This is what your team can now prototype in a day."

---

### Post-Engagement Checklist

- [ ] Send recap email with all live URLs (same day)
- [ ] Send recording if virtual (within 24 hours)
- [ ] Send feedback form (NPS + qualitative)
- [ ] Process remaining 50% payment
- [ ] Schedule 1-week check-in call

---

## PB11 — Guest Instructor Onboarding

### Overview
How to recruit, vet, prepare, and run a workshop day with a guest instructor.

For the full guide, see [docs/phase3/guest-instructor-program.md](../phase3/guest-instructor-program.md).

---

### Recruitment Checklist

- [ ] Identify 3–5 candidates (alumni, network, creator outreach)
- [ ] Send outreach email using the template in the guest instructor guide
- [ ] Schedule initial 20-min call

### Selection Checklist

- [ ] Initial call completed
- [ ] Trial demo completed (15 min, informal)
- [ ] Decision communicated within 48 hours
- [ ] Offer sent (verbal → written agreement)

### Onboarding Checklist (4 Weeks Before)

- [ ] Instructor agreement signed
- [ ] Full curriculum package shared (playbooks, guidebooks, templates, presentations)
- [ ] Prep call scheduled

### Onboarding Checklist (2 Weeks Before)

- [ ] Prep call completed (60 min):
  - Full day schedule reviewed together
  - Segments ownership clarified
  - Participant personas reviewed
  - Incident scenarios discussed
- [ ] GitHub read access granted
- [ ] Added to workshop Discord

### Day-Of

- [ ] Arrive/join together (30 min before participants)
- [ ] Quick huddle: energy, contingencies, hand-off signals

### Post-Engagement

- [ ] Debrief call (30 min) within 3 days
- [ ] Compensation processed within 7 days
- [ ] Added to guest instructor roster in [guest-instructor-program.md](../phase3/guest-instructor-program.md)

---

## PB12 — Referral & Affiliate Operations

### Overview
How to manage the referral program for alumni and the affiliate program for partners — tracking, payouts, and communication.

For full specs, see [referral-program.md](../phase3/referral-program.md) and [affiliate-partnership-program.md](../phase3/affiliate-partnership-program.md).

---

### Monthly Referral Payout Process

1. Pull referral report from portal admin or Rewardful dashboard
2. Filter for status = `attended` and `rewardPaidAt` = null
3. Process payouts via Venmo/PayPal
4. Update referral records: status → `rewarded`, `rewardPaidAt` = today
5. Send payout confirmation email to each alumni

**Email template:**
```
Subject: Your referral reward is on its way 🎉

Hi [Name],

[Referred person's first name] attended the workshop — your $25 referral 
reward has been sent to [Venmo/PayPal handle].

Thanks for spreading the word. You're helping more people ship.

Kyle
```

---

### New Affiliate Partner Onboarding

- [ ] Review application (audience fit, authentic content, FTC compliance capability)
- [ ] Decision within 5 business days
- [ ] If approved:
  - [ ] Sign affiliate agreement
  - [ ] Create affiliate code in Rewardful (or custom system)
  - [ ] Send welcome email with promotional assets kit
  - [ ] Add to monthly affiliate newsletter list
- [ ] If declined: send polite decline with reasoning

---

### Monthly Affiliate Operations

- [ ] Review Rewardful dashboard: new referrals, pending commissions
- [ ] Process monthly payouts (for affiliates with > $50 in earned commission)
- [ ] Send affiliate newsletter:
  - Upcoming cohort dates
  - Any new promotional assets
  - Top performer shoutout (optional, with permission)

---

*For questions about these playbooks, contact [hello@vibecodingworkshop.com](mailto:hello@vibecodingworkshop.com)*

---

## PB09 — Code Jam Operations Playbook

### Overview
How to plan, run, and follow up on the annual Vibe Code Jam build event.

### 8 Weeks Before

- [ ] Confirm event date and announce via newsletter + Discord
- [ ] Open registration (free, via Typeform or custom form)
- [ ] Recruit 3–5 judges (alumni, sponsor reps, or community members)
- [ ] Reserve streaming platform (YouTube Live or Twitch)
- [ ] Set up Discord channels: `#code-jam`, `#help-im-stuck`, `#find-a-team`
- [ ] Draft kick-off livestream script

### 4 Weeks Before

- [ ] Send reminder to registered participants
- [ ] Confirm all judges and send scoring rubric
- [ ] Test streaming and submission form setup
- [ ] Brief sponsors (if Code Jam has a title sponsor)
- [ ] Prepare mid-point check-in script

### 1 Week Before

- [ ] Send logistics email: Discord link, schedule, theme hint ("something unexpected is coming")
- [ ] Prepare theme reveal (keep secret until kick-off)
- [ ] Confirm support volunteers for Discord during the event
- [ ] Test submission form end-to-end

### Day Before

- [ ] Final streaming setup test
- [ ] Set up all Discord channels and pin rules
- [ ] Prepare kick-off presentation

### Event Day (Friday)

- [ ] Go live at 8:00 PM ET
- [ ] Announce theme
- [ ] Open Discord support channels
- [ ] Monitor `#help-im-stuck` every 2 hours

### Event Day (Saturday)

- [ ] Mid-point check-in stream at 8:00 AM ET
- [ ] Circulate Discord to keep energy up
- [ ] Send 1-hour warning at 7:00 PM ET
- [ ] Close submissions at 8:00 PM ET
- [ ] Showcase stream at 9:00 PM ET
- [ ] Announce winners at end of showcase

### Post-Event

- [ ] Email all participants: project gallery link, winner announcements
- [ ] Publish project gallery on website
- [ ] Write retrospective blog post
- [ ] Update Code Jam documentation with lessons learned
- [ ] Log participant count, submission count, countries in event record

---

## PB10 — Sponsorship Outreach Playbook

### Overview
How to prospect, pitch, and close sponsorship deals for AI/dev tool companies.

### Identifying Prospects

Target companies that:
- Make AI development tools (editors, models, assistants)
- Deploy or host web apps
- Sell to non-technical developers or early-stage founders

**Sources:**
- ProductHunt launches in the AI/dev tools category
- Y Combinator portfolio (AI + dev tools companies)
- Existing tools used in the workshop (Anthropic, Cursor, Vercel, StackBlitz)

### Outreach Template

**Subject:** Sponsorship opportunity — Vibe Coding Workshop (Chicago, non-technical AI builder audience)

**Body:**
```
Hi [Name],

I run the Vibe Coding Workshop — a one-day workshop that teaches non-technical 
people to build real apps using AI tools. We've had [N] participants go from 
zero coding experience to deployed apps in one day using [THEIR TOOL / similar tools].

We're opening sponsorship for our [upcoming cohort / 2027 season]. 
Our participants are exactly the audience you want: non-technical people who 
are forming opinions on AI dev tools for the first time.

We have three tiers starting at $500/cohort. Can I send you our sponsorship deck?

— Kyle
hello@vibecodingworkshop.com
```

### Follow-Up Cadence

| Day | Action |
|-----|--------|
| 0 | Send outreach email |
| 5 | Follow up if no reply: one sentence, same thread |
| 12 | Final follow up: "Happy to put you on the next cohort's list when ready" |
| 30+ | Move to next cohort outreach cycle |

### Closing Process

1. Send sponsorship deck PDF (based on `docs/phase-4/revenue/sponsorship-packages.md`)
2. Schedule 20-minute call to walk through benefits
3. Agree on tier and cohort
4. Send Sponsorship Agreement (PDF or DocuSign)
5. Receive payment before cohort date
6. Brief sponsor on workshop day logistics
7. Deliver benefits during/after cohort
8. Send post-cohort report

### CRM Tracking

Log each prospect in sponsor tracking sheet with:
- Company name, contact, tier of interest
- Status: `prospecting → outreach → call → agreement → paid → delivered → complete`
- Last contact date and next action

---

## PB11 — Curriculum Licensing Playbook

### Overview
How to bring a new organization on board as a curriculum licensee.

### Intake

1. Receive inquiry via email
2. Log in licensee tracking sheet
3. Send 30-minute discovery call invite within 3 business days

### Discovery Call Agenda

- Who they are and what they run
- Their intended use (cohort size, frequency, audience)
- Their instructor situation (do they have someone?)
- Their technology setup (can students use Cursor/Claude?)
- Walk through licensing tiers
- Answer questions

### Post-Call

- If good fit: Send licensing proposal within 48 hours
- If not a fit: Send a friendly "not the right time" email with door left open

### Proposal Contents

1. Recommended tier and annual fee
2. What's included (curriculum package + support)
3. Quality standards summary
4. License term (12 months, auto-renewal)
5. Process for getting started

### Onboarding (After Agreement Signed)

- [ ] Collect signed Curriculum License Agreement
- [ ] Collect payment
- [ ] Share Instructor Resource Kit (Google Drive folder)
- [ ] Schedule 60-minute onboarding call
- [ ] Add organization to Slack `#licensees` channel
- [ ] Schedule 4-hour instructor training session
- [ ] Add to `/partners` page on website
- [ ] Set 30-day check-in reminder

### Ongoing Support

| Cadence | Action |
|---------|--------|
| 30 days after first cohort | Check-in call: how did it go? |
| Quarterly | Brief async update: NPS, cohort count |
| Annually | Renewal review + curriculum update briefing |

---

## PB12 — Regional Instructor Certification Playbook

### Overview
How to evaluate, train, and certify a new regional instructor.

### Application Review

Minimum criteria:
- [ ] Completed the Vibe Coding Workshop (workshop alumni)
- [ ] Can commit to at least 2 cohorts per year
- [ ] Has a venue or plan for a venue in their city
- [ ] Has some teaching, mentoring, or facilitation experience

### Step 1: Application Call (30 min)

Review:
- Background and motivation
- City and target audience
- Prior teaching experience
- Technology comfort level

If approved: move to preparation phase.

### Step 2: Preparation Phase (4–6 weeks)

- [ ] Send Instructor Resource Kit
- [ ] Assign Guidebook G22 (Instructor Guide) + G29 (Regional Workshop Guide)
- [ ] Schedule shadow day (attend a Grayslake workshop or virtual equivalent)
- [ ] Candidate runs 1 pilot workshop (5–8 people, informal)
- [ ] Candidate submits: written reflection + a 10-min video recording of one session

### Step 3: Certification Review

- [ ] Review pilot workshop feedback survey results
- [ ] Review video recording
- [ ] 30-minute certification call with Kyle
- [ ] Checklist review: can they run the workshop independently?

### Step 4: Certification

- [ ] Send Certification Letter
- [ ] Sign Regional Instructor Agreement
- [ ] Add to instructor community Slack channel
- [ ] Add to `/instructors` page on website
- [ ] Add to instructor tracking sheet (city, status, cohorts delivered)

### Ongoing Quality

- Annual recertification call (30 minutes)
- NPS monitoring — below 50 triggers a check-in
- Curriculum update notifications via GitHub

---

*For questions about these playbooks, contact [hello@vibecodingworkshop.com](mailto:hello@vibecodingworkshop.com)*
