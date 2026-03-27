# Roadmap

> The Vibe Coding Workshop product roadmap — what's done, what's in progress, and what's planned.

---

## 🏁 Status Key

| Symbol | Meaning |
|--------|---------|
| ✅ | Shipped |
| 🔄 | In Progress |
| 📋 | Planned |
| 💡 | Proposed / Under Consideration |
| ❌ | Cancelled / Deprioritized |

---

## Phase 0 — Foundation ✅ (Complete)

- [x] Initial `index.html` marketing site
- [x] Dark theme, responsive layout
- [x] Workshop sections: hero, projects, phases, instructor, FAQ, waitlist
- [x] README.md, CONTRIBUTING.md, CODE_OF_CONDUCT.md, SECURITY.md, PRIVACY.md
- [x] Documentation suite (docs/ directory)
- [x] CLAUDE.md, memory.md, gemini.md, agents.md
- [x] 100 Persona profiles
- [x] 50 Project templates
- [x] 25 Guidebooks
- [x] Playbooks
- [x] Presentations (10 decks)
- [x] SETUP.md

---

## Phase 1 — Pre-Launch (Summer 2026)

### Site Improvements
- [x] Add Open Graph + Twitter Card meta tags for social sharing
- [x] Add `<meta name="description">` for SEO
- [x] Add `aria-label` to nav links and form inputs
- [ ] Implement proper waitlist form with email service backend (e.g., Resend, Mailchimp)
- [x] Add favicon and apple-touch-icon
- [x] Add `sitemap.xml` and `robots.txt`
- [x] Add `_headers` file for security headers (GitHub Pages / Netlify)
- [x] Testimonials section (from pilot participants)
- [x] Pricing section with early-bird offer

### Content
- [ ] Instructor bio photo
- [ ] Sample project screenshots / demos
- [ ] Video walkthrough of a sample vibe coding session (30 sec)
- [ ] Blog post: "What is vibe coding?" (SEO landing page)

### Infrastructure
- [x] Set up GitHub Actions CI for HTML validation
- [x] Set up Dependabot for any future dependencies
- [ ] Configure GitHub Pages custom domain (`vibecodingworkshop.com`)

---

## Phase 2 — First Cohort (Summer 2026) 🔄 In Progress

> **Documentation created July 2026.** All Phase 2 docs live in `docs/phase2/`. See `docs/phase2/README.md` for the full index.

### Workshop Delivery
- [x] Finalize workshop day schedule and materials (`docs/phase2/workshop-day-schedule.md`)
- [x] Pre-workshop participant onboarding email sequence (`docs/phase2/email-sequences/pre-workshop-onboarding.md`)
- [x] Day-of instructor guide (`docs/phase2/instructor-guide.md`)
- [x] Setup guides for Cursor, Claude, v0, Vercel, Supabase (`docs/phase2/setup-guides/`)
- [ ] Project starter templates for all 4 projects (GitHub Classroom — see `docs/phase2/github-classroom-setup.md`)
- [x] Post-workshop participant feedback survey (`docs/phase2/feedback-survey.md`)

### Digital Materials
- [x] Participant workbook (`docs/phase2/participant-workbook.md`)
- [x] Prompting playbook (`docs/phase2/prompting-playbook.md`)
- [x] GitHub Classroom setup for participant repos (`docs/phase2/github-classroom-setup.md`)

### Community
- [x] Discord server guide (`docs/phase2/community/discord-guide.md`)
- [x] Alumni newsletter template (`docs/phase2/community/alumni-newsletter-template.md`)
- [ ] Discord server created and live
- [ ] Newsletter first edition published

---

## Phase 3 — Scale (Fall 2026 – Spring 2027) 🔄 In Progress

> Planning documentation complete. See [`docs/phase3/`](docs/phase3/README.md) for all Phase 3 specs, guides, and operational playbooks.

### Workshop Expansion
- [x] Remote/virtual workshop format — see [`docs/phase3/virtual-workshop-format.md`](docs/phase3/virtual-workshop-format.md)
- [ ] Second in-person cohort (Fall 2026, increased capacity: 30 seats)
- [x] Multi-day intensive format (2-day version) — see [`docs/phase3/multi-day-intensive.md`](docs/phase3/multi-day-intensive.md)
- [x] Corporate training version (team of 8–12) — see [`docs/phase3/corporate-training-guide.md`](docs/phase3/corporate-training-guide.md)
- [x] Self-paced async course version — see [`docs/phase3/self-paced-course-outline.md`](docs/phase3/self-paced-course-outline.md)

### Site & Platform
- [x] Participant portal spec — see [`docs/phase3/participant-portal-spec.md`](docs/phase3/participant-portal-spec.md)
- [ ] Participant portal (login, project submissions, resources) — build from spec
- [x] Payment processing and registration spec — see [`docs/phase3/payment-registration-spec.md`](docs/phase3/payment-registration-spec.md)
- [ ] Payment processing live on site
- [x] Referral program design — see [`docs/phase3/referral-program.md`](docs/phase3/referral-program.md)
- [ ] Referral program launched to alumni
- [x] Affiliate / partnership program design — see [`docs/phase3/affiliate-partnership-program.md`](docs/phase3/affiliate-partnership-program.md)
- [ ] Affiliate program live with first 3 partners

### Content Expansion
- [x] Advanced workshop: "Vibe Coding 2.0" curriculum — see [`docs/phase3/vibe-coding-2-curriculum.md`](docs/phase3/vibe-coding-2-curriculum.md)
- [ ] Vibe Coding 2.0 first cohort delivered
- [x] Guest instructor program design — see [`docs/phase3/guest-instructor-program.md`](docs/phase3/guest-instructor-program.md)
- [ ] First guest instructor cohort run
- [x] Project showcase gallery spec — see [`docs/phase3/project-showcase-gallery.md`](docs/phase3/project-showcase-gallery.md)
- [ ] Showcase gallery live with 20+ projects

---

## Phase 4 — Product Ecosystem (2027+)

### Tools
- [x] "Vibe Starter" — an opinionated project scaffolding tool (spec complete → [docs](docs/phase-4/tools/vibe-starter.md))
- [x] Prompt library web app (spec complete → [docs](docs/phase-4/tools/prompt-library.md))
- [x] AI tool comparison guide (initial guide published → [docs](docs/phase-4/tools/ai-tool-comparison.md))

### Community
- [x] Annual "Vibe Code Jam" — 24-hour community build event (operations doc complete → [docs](docs/phase-4/community/code-jam.md))
- [x] Regional workshops (framework and instructor certification program → [docs](docs/phase-4/community/regional-workshops.md))
- [x] University partnership program (tiers, targets, and process → [docs](docs/phase-4/community/university-partnerships.md))

### Revenue Diversification
- [x] Sponsorship packages for AI/dev tool companies (tiers and policies → [docs](docs/phase-4/revenue/sponsorship-packages.md))
- [x] Licensing workshop curriculum to coding bootcamps (tiers and process → [docs](docs/phase-4/revenue/curriculum-licensing.md))
- [x] Book: "Vibe Coding: Build Anything with AI" (chapter outline and publishing plan → [docs](docs/phase-4/revenue/book-outline.md))

---

## Phase 5 — Advanced Curriculum & Specializations (2027)

### New Workshop Tracks
- [ ] "Vibe Coding: Backend" — databases, auth, REST APIs (1-day intensive)
- [ ] "Vibe Coding: Mobile" — React Native / Expo with AI (1-day intensive)
- [ ] "Vibe Coding: Data" — Python notebooks, AI analysis, dashboards
- [ ] Modular curriculum: mix-and-match workshop days

### Credentials & Recognition
- [ ] Completion certificate (digital, shareable on LinkedIn)
- [ ] Alumni badge for GitHub profile
- [ ] Skill assessment: pre/post workshop prompt-quality scoring

### Partnerships
- [ ] Formal MOU with College of Lake County for recurring venue
- [ ] Pilot with 1–2 coding bootcamps to license curriculum

---

## Phase 6 — Enterprise Training & Licensing (2027–2028)

### Corporate Offering
- [ ] "Vibe Coding for Teams" — half-day workshop for companies (8–20 devs)
- [ ] Custom industry tracks (marketing, design, finance, ops)
- [ ] Enterprise licensing package for corporate L&D departments
- [ ] Train-the-trainer program (certify 5 facilitators)

### Revenue Streams
- [ ] Corporate workshop day rate (flat fee + materials)
- [ ] Annual curriculum license for bootcamps / universities
- [ ] Sponsored cohorts (AI tool companies sponsor seats for underrepresented builders)

### Infrastructure
- [ ] CRM for corporate pipeline (HubSpot or similar)
- [ ] Proposal & SoW templates for enterprise sales
- [ ] Facilitator certification portal (simple LMS)

---

## Phase 7 — Platform & Community Maturity (2028)

### Community
- [ ] 500+ active alumni in Discord
- [ ] Monthly alumni "build nights" (virtual co-working)
- [ ] Annual "Vibe Code Jam" — 24-hour community hackathon (virtual + in-person)
- [ ] Alumni showcase gallery on website (real apps built after the workshop)
- [ ] Peer mentorship pairing: recent alumni mentor new cohorts

### Platform
- [ ] Participant portal v2: project portfolio, peer reviews, prompting journal
- [ ] AI-powered prompt feedback tool (evaluate prompt quality in real time)
- [ ] Searchable public prompt library (community-contributed, curated)
- [ ] Workshop replay library (screen recordings from past sessions)

### Content
- [ ] Weekly newsletter: "The Vibe" — AI tool news, participant spotlights, prompt tips
- [ ] YouTube channel: workshop highlight reels, tool walkthroughs
- [ ] Guest instructor series: alumni-turned-builders teaching their specialty

---

## Phase 8 — Global Expansion (2028–2029)

### Geographic Expansion
- [ ] Second US city: Austin, TX or Denver, CO (pilot 2-day event)
- [ ] International pilot: Toronto, London, or Berlin (partner with local co-working space)
- [ ] Translated curriculum: Spanish and Portuguese (Latin American market)
- [ ] Local facilitator network: trained + licensed facilitators in 5 cities

### Accessibility & Inclusion
- [ ] Scholarship program: 2 free seats per cohort for underrepresented builders
- [ ] Accessible workshop materials (screen-reader optimized, WCAG 2.1 AA)
- [ ] Low-bandwidth version of participant portal for emerging markets

### Scale Targets
- [ ] 1,000 cumulative alumni
- [ ] 12 cohorts per year across all locations
- [ ] 10 certified facilitators globally

---

## Phase 9 — Legacy & Impact (2029+)

### Book & Media
- [ ] Publish: *Vibe Coding: Build Anything with AI* (book or interactive digital course)
- [ ] Podcast: "Built Without a CS Degree" — interviews with self-taught builders
- [ ] Documentary short: follow 3 participants from zero to shipped product

### Institutional Impact
- [ ] University partnership program: guest lectures + curriculum licensing at 10+ schools
- [ ] High school pilot: intro vibe coding workshop for ages 14–18
- [ ] Public library program: free community workshops in underserved areas

### Open Source
- [ ] Open-source the core curriculum (CC-BY-SA license)
- [ ] "Vibe Starter" CLI tool — open source project scaffolding with AI prompts baked in
- [ ] Contribute prompt engineering resources to the broader open-source community

### Sustainability
- [ ] Foundation or 501(c)(3) application to support scholarship and public programs
- [ ] Endowment goal: 3 years of operating expenses in reserve
- [ ] Succession plan: transition facilitation ownership to alumni network

---

## 💡 Under Consideration

- Mobile app companion for the prompting playbook
- Podcast: interviews with self-taught developers who use AI
- Certification program for workshop alumni
- International versions (with translated materials)

---

## Milestones

| Milestone | Target Date | Status |
|-----------|------------|--------|
| Marketing site live | Q1 2026 | ✅ |
| Documentation suite complete | Q1 2026 | ✅ |
| Phase 3 planning documentation | Q1 2026 | ✅ |
| Waitlist backend connected | Q2 2026 | 📋 |
| First cohort delivered | Summer 2026 | 📋 |
| Payment processing live | Q3 2026 | 📋 |
| Virtual format first cohort | Q3 2026 | 📋 |
| 50 alumni | Q4 2026 | 📋 |
| Participant portal v1 | Q4 2026 | 📋 |
| Corporate training launched | Q4 2026 | 📋 |
| Vibe Coding 2.0 first cohort | Q1 2027 | 💡 |
| Showcase gallery live | Q1 2027 | 💡 |
| 200 alumni | 2027 | 💡 |
| Enterprise training program | 2027–2028 | 💡 |
| 500 alumni | 2028 | 💡 |
| Global expansion (2 cities) | 2028–2029 | 💡 |
| 1,000 alumni | 2029 | 💡 |
| Open-source curriculum released | 2029+ | 💡 |

---

*Have a feature idea? Open a [GitHub Discussion](https://github.com/Krosebrook/vibe-coding-workshop/discussions) or email [hello@vibecodingworkshop.com](mailto:hello@vibecodingworkshop.com).*
