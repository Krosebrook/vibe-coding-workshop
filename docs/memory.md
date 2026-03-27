# Memory File — Vibe Coding Workshop

> This file provides persistent memory and context for AI assistants working in this repository. It is meant to be read at the start of every AI session.

---

## 🏷️ Project Summary

**Vibe Coding Workshop** is a one-day in-person workshop that teaches non-technical people to build real, deployed web applications using AI tools (Claude, Cursor, v0). The site is a static HTML marketing page. The instructor is Kyle Rosebrook.

---

## 🔑 Key Facts

| Key | Value |
|-----|-------|
| Owner | Kyle Rosebrook (`@Krosebrook`) |
| Contact | hello@vibecodingworkshop.com |
| Location | College of Lake County, Grayslake, IL |
| Cohort | Summer 2026, 20 seats |
| Stack | Vanilla HTML5 + CSS3, no JS, no build tools |
| Deployment | GitHub Pages |
| Primary AI tool in workshop | Claude + Cursor |
| Other tools used | v0, Vercel, Supabase |

---

## 📁 Repository Layout

```
/
├── index.html              ← Entire website
├── README.md               ← Project overview + audit
├── CLAUDE.md               ← Claude context
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── SECURITY.md
├── PRIVACY.md
├── ROADMAP.md
├── SETUP.md
└── docs/
    ├── memory.md           ← This file
    ├── gemini.md
    ├── agents.md
    ├── skills/
    ├── plugins/
    ├── repo-agents/
    ├── copilot-skills/
    ├── schemas/
    ├── personas/           ← 100 learner personas
    ├── templates/          ← 50 project templates
    ├── guidebooks/         ← 25 guidebooks
    ├── playbooks/
    └── presentations/      ← 10 slide decks
```

---

## 🎯 Workshop Curriculum

### Projects (4 in 1 day)
1. **Personal Landing Page** — prompt → output → refine loop
2. **Mood Tracker with Charts** — state + data viz
3. **Recipe Finder with API** — API integration + error handling
4. **AI Chat Assistant** — AI integration + deployment

### Workshop Phases
- **Morning:** Learn the Scales (AI fundamentals, prompting patterns)
- **Late Morning:** Build Projects 01 & 02 (guided)
- **Afternoon:** Build Projects 03 & 04 (open-ended)
- **End of Day:** Ship It (deploy to live URLs)

---

## 🎨 Design System

```css
--bg: #0a0a0a           /* Page background */
--surface: #111111      /* Card backgrounds */
--border: #222222       /* Borders */
--text: #e8e8e8         /* Primary text */
--muted: #888888        /* Secondary text */
--accent: #7c3aed       /* Purple — CTAs, interactive */
--accent-light: #a78bfa /* Light purple — labels, highlights */
--green: #10b981        /* Success, terminal output */
--font: 'Inter', system-ui, sans-serif
--mono: 'JetBrains Mono', 'Fira Code', monospace
```

---

## 🧑‍🏫 About the Instructor

**Kyle Rosebrook** is a self-taught Staff Engineer specializing in AppSec and AI. He came up through bartending and quality control before teaching himself to code. Now he teaches senior engineers at a managed services firm. He has 240+ AI tools configured. His teaching philosophy: meet learners where they are, no gatekeeping.

---

## 📋 Open Tasks (from ROADMAP.md)

**Phase 1 (Pre-Launch, Summer 2026) — remaining:**
- Connect waitlist form to email backend (Resend, Mailchimp, etc.)
- Add favicon and apple-touch-icon
- Add `sitemap.xml` and `robots.txt`
- Add `_headers` file for CSP security headers
- Testimonials section + Pricing section

**Phase 1 (Pre-Launch, Summer 2026) — completed:**
- ✅ Added `<meta name="description">` for SEO
- ✅ Added Open Graph + Twitter Card meta tags
- ✅ Added `aria-label` to nav links and email input
- ✅ Added `<main role="main">` wrapper
- ✅ Added visually-hidden `<label>` for email input
- ✅ Added `id="bring"` to "What to Bring" section

---

## 🚫 What NOT to Change Without Asking

- Workshop curriculum details (projects, phases, pricing concepts)
- Instructor bio content
- Contact email
- Dark theme / color scheme
- Zero-JS constraint on the website

---

## 💬 Tone Guide

The voice of this project is:
- **Direct** — say what you mean
- **Honest** — no hype, no overselling
- **Warm** — especially toward beginners
- **Builder-first** — practical over theoretical
- **Non-condescending** — never make someone feel dumb

Example phrases that fit the brand:
- ✅ "You don't need a CS degree."
- ✅ "This is where the vibe clicks."
- ✅ "Ship it."
- ❌ "Leverage synergies"
- ❌ "Paradigm shift"
- ❌ "It's simple — just..."

---

## 📅 Session Log

| Date | Changes Made | AI |
|------|--------------|----|
| March 2026 | Initial documentation suite created | GitHub Copilot |
| March 2026 | Audit of all 4 workshop phases; fixed SEO, accessibility, and semantic HTML in `index.html`; updated ROADMAP.md with Phases 5–9; refreshed README.md audit summary and memory.md | GitHub Copilot |

---

*Update this file whenever significant decisions or changes are made.*
