# Gemini Instructions — Vibe Coding Workshop

> This file provides context and instructions for Google Gemini when working in this repository.

---

## 🏷️ Project Overview

**Vibe Coding Workshop** is a one-day hands-on workshop teaching non-technical people to build real web applications using AI as a co-pilot. The main deliverable is a static HTML marketing site (`index.html`) plus a comprehensive documentation suite.

**Owner:** Kyle Rosebrook  
**Contact:** hello@vibecodingworkshop.com  
**Stack:** Vanilla HTML5 + CSS3 (zero JavaScript, zero build tools)  
**Deployment:** GitHub Pages

---

## 🧭 Gemini's Role in This Project

Gemini is best used for:

1. **Content Generation** — Writing clear, beginner-friendly documentation
2. **SEO Research** — Identifying keywords and meta descriptions
3. **Competitive Analysis** — Comparing similar coding workshops
4. **Curriculum Research** — Finding best practices for teaching AI-assisted coding
5. **Accessibility Review** — Checking ARIA, color contrast, semantic HTML
6. **Email Copy** — Drafting waitlist confirmation and onboarding emails

---

## 📋 Instructions for Gemini

### Editing `index.html`
- Preserve the **dark theme** (CSS custom properties are the source of truth)
- Keep it **zero-dependency** (no npm, no CDNs unless asked)
- Use **semantic HTML5** (`<section>`, `<nav>`, `<article>`, `<main>`)
- Follow the **section pattern**: `.section-label` + `<h2>` + `.section-sub` + content

### Writing Documentation
- **Audience:** Absolute beginners (assume no coding background)
- **Tone:** Direct, honest, warm, builder-first (see tone guide below)
- **Format:** Use Markdown headings, code blocks, and tables appropriately
- **Length:** Thorough but scannable — use lists and headers generously

### Prompt Engineering Tasks
- Structure every prompt: **Context → Task → Output Format → Constraints**
- Always show a bad example vs. good example comparison
- Test prompts against the 4 workshop projects

---

## 🎨 Design System Reference

```
Background:     #0a0a0a  (--bg)
Surface:        #111111  (--surface)
Border:         #222222  (--border)
Text:           #e8e8e8  (--text)
Muted Text:     #888888  (--muted)
Accent Purple:  #7c3aed  (--accent)
Light Purple:   #a78bfa  (--accent-light)
Green:          #10b981  (--green)
```

---

## 🎯 Workshop Details

| Item | Detail |
|------|--------|
| Duration | 1 day |
| Cohort size | 20 seats |
| Location | College of Lake County, Grayslake, IL |
| Next cohort | Summer 2026 |
| Target audience | Non-technical people (designers, marketers, founders, curious beginners) |
| NOT for | Experienced developers, people wanting to learn a specific language deeply |

### 4 Projects Built in 1 Day:
1. Personal Landing Page
2. Mood Tracker with Charts
3. Recipe Finder with API
4. AI Chat Assistant

### Tools Used:
- **Claude** + **Cursor** (primary)
- **v0** (UI scaffolding)
- **Vercel** (deployment)
- **Supabase** (backend for Project 04)

---

## 💬 Brand Tone Guide

| ✅ Use | ❌ Avoid |
|--------|---------|
| Plain, direct language | Jargon and buzzwords |
| "You'll build X" | "You'll leverage X to deliver Y" |
| "That's the point" | "That's a great learning opportunity" |
| "No CS degree required" | "Democratizing software development" |
| Short sentences | Passive voice |

---

## 🚫 What Gemini Should NOT Do

- Add JavaScript to the site without explicit request
- Change the workshop curriculum details without verification
- Add third-party tracking scripts or analytics
- Use marketing copy that overpromises outcomes
- Suggest frameworks (React, Vue, etc.) for the marketing site

---

## 📁 Key Files for Gemini to Know

| File | Description |
|------|-------------|
| `index.html` | The entire website |
| `docs/personas/README.md` | 100 learner persona profiles |
| `docs/templates/README.md` | 50 project starter templates |
| `docs/playbooks/README.md` | Workshop operational playbooks |
| `ROADMAP.md` | Feature and content roadmap |

---

## 🔍 SEO Keywords (for meta tags and content)

**Primary:** vibe coding workshop, AI coding for beginners, learn to code with AI  
**Secondary:** no-code with AI, Claude Cursor workshop, build apps without coding experience  
**Long-tail:** how to build an app without knowing how to code, AI assisted web development workshop Chicago

---

*Last updated: March 2026*
