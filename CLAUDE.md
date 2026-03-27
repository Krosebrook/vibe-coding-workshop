# CLAUDE.md — Vibe Coding Workshop

> This file provides context and instructions for Claude (Anthropic) when working in this repository.

---

## 🏷️ Project Identity

**Name:** Vibe Coding Workshop  
**Type:** Static HTML marketing site + educational workshop curriculum  
**Owner:** Kyle Rosebrook (`@Krosebrook`)  
**Mission:** Make software creation accessible to anyone who can describe an idea — by teaching AI-assisted "vibe coding."

---

## 🧠 Context for Claude

### What This Repo Is
A single-page marketing website (`index.html`) for a one-day in-person coding workshop. The site:
- Promotes the workshop to prospective students
- Explains what participants build (4 projects in 1 day)
- Captures waitlist sign-ups via email link
- Is deployed as a static site (GitHub Pages or similar)

### Who the Audience Is
- Non-technical people curious about building software
- Designers, marketers, and founders who want to prototype
- People who've tried ChatGPT for code but ended up confused
- Absolute beginners — zero coding experience required

### Technology Stack
- **Frontend:** Vanilla HTML5 + CSS3 (no frameworks, no build tools)
- **Fonts:** System fonts with fallbacks (Inter, JetBrains Mono)
- **Deployment:** GitHub Pages
- **Workshop Tools:** Claude, Cursor, v0, Vercel, Supabase

---

## 📋 Instructions for Claude

### When Editing `index.html`
1. **Preserve the dark theme** — CSS custom properties are the single source of truth for colors
2. **Keep it dependency-free** — do not add npm packages, CDN imports, or build steps
3. **Maintain accessibility** — ensure any new elements have proper ARIA attributes
4. **Respect the design system:**
   - `--accent: #7c3aed` (purple) for interactive elements
   - `--accent-light: #a78bfa` for labels and highlights
   - `--green: #10b981` for success/positive states
   - `--muted: #888888` for secondary text
5. **Section pattern:** All sections use `<section>`, have a `.section-label`, an `<h2>`, and a `.section-sub` paragraph
6. **Do not** add JavaScript unless explicitly asked — the site is intentionally JS-free

### When Writing Documentation
1. Use the tone of Kyle Rosebrook — direct, honest, non-condescending, builder-first
2. Write for beginners as the primary audience
3. Avoid jargon. When technical terms are necessary, define them inline
4. Use practical examples, not abstract principles

### When Writing Prompts/Skills/Playbooks
1. Structure prompts as: Context → Instruction → Output format → Constraints
2. Always include a "bad example" and "good example" pair for comparison
3. Test every prompt against the four workshop projects as use cases

### Code Style
```html
<!-- Use 2-space indentation -->
<!-- Use semantic HTML5 elements -->
<!-- Comments describe sections, not lines -->
<!-- Class names are kebab-case, descriptive -->
```

---

## 🚫 What Claude Should NOT Do

- Add external JavaScript libraries without explicit request
- Change the color scheme without explicit request  
- Remove the email-based waitlist form without explicit request
- Add cookies, analytics, or tracking scripts
- Modify the workshop curriculum details without verifying with Kyle
- Make assumptions about pricing, dates, or location changes

---

## 🔑 Key Brand Terms

| Term | Meaning |
|------|---------|
| **Vibe coding** | AI-assisted software development by intent/feel rather than syntax |
| **Vibe** | The flow state of building with AI; when intent and output align |
| **Co-pilot** | AI assistant role in the workflow |
| **Ship it** | Deploy to a real, public URL — a core workshop outcome |
| **Prompting** | The skill of communicating intent to AI tools effectively |

---

## 📁 Key Files

| File | Purpose |
|------|---------|
| `index.html` | Entire marketing website (HTML + CSS inline) |
| `README.md` | Project overview and audit summary |
| `ROADMAP.md` | Feature roadmap and milestone tracking |
| `SETUP.md` | Local development setup |
| `docs/personas/` | 100 learner persona portfolios for curriculum design |
| `docs/templates/` | 50 project starter templates for workshop use |
| `docs/playbooks/` | Operational playbooks for running the workshop |

---

## 🎯 Goals for AI Assistance

1. **Curriculum Development** — Help expand and refine workshop content
2. **Site Improvements** — Accessibility, SEO, performance enhancements
3. **Template Generation** — Create starter project templates for participants
4. **Documentation** — Keep all docs accurate and up-to-date
5. **Prompt Engineering** — Develop and refine prompts used in workshop exercises

---

*Last updated: March 2026*
