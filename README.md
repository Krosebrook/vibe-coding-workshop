# Vibe Coding Workshop 🎸

> **Build apps by feel.** A one-day hands-on workshop where you go from idea to working application using AI as your co-pilot.

[![Live Site](https://img.shields.io/badge/Live%20Site-vibecodingworkshop.com-7c3aed?style=flat-square)](https://krosebrook.github.io/vibe-coding-workshop)
[![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)](LICENSE)
[![Cohort](https://img.shields.io/badge/Next%20Cohort-Summer%202026-a78bfa?style=flat-square)](#roadmap)

---

## 📌 Overview

**Vibe Coding Workshop** is a one-day, in-person workshop held at College of Lake County, Grayslake, IL (Chicago area). Participants go from zero coding experience to shipping four real, deployed web applications — guided by AI tools like Claude and Cursor.

No syntax memorization. No boilerplate hell. Just you, your idea, and the vibe.

**Instructor:** Kyle Rosebrook — Staff Engineer, AppSec & AI  
**Cohort Size:** Limited to 20 seats  
**Next Date:** Summer 2026  
**Contact:** [hello@vibecodingworkshop.com](mailto:hello@vibecodingworkshop.com)

---

## 🗂️ Repository Structure

```
vibe-coding-workshop/
├── index.html                  # Single-page marketing site
├── README.md                   # This file
├── CLAUDE.md                   # Claude AI assistant context
├── CONTRIBUTING.md             # Contribution guidelines
├── CODE_OF_CONDUCT.md          # Community standards
├── SECURITY.md                 # Security policy
├── PRIVACY.md                  # Privacy policy
├── ROADMAP.md                  # Project roadmap
├── SETUP.md                    # Local setup instructions
├── CNAME                       # Custom domain for GitHub Pages
├── robots.txt                  # Search engine crawl rules
├── sitemap.xml                 # Site map for SEO
├── _headers                    # Security headers (Netlify / GitHub Pages)
├── .github/
│   ├── dependabot.yml          # Automated dependency updates
│   └── workflows/
│       └── html-validate.yml   # HTML validation CI
└── docs/
    ├── memory.md               # AI memory/context file
    ├── gemini.md               # Gemini AI instructions
    ├── agents.md               # AI agents documentation
    ├── skills/                 # Vibe coding skills library
    ├── plugins/                # Recommended plugins & extensions
    ├── repo-agents/            # Repository automation agents
    ├── copilot-skills/         # Custom GitHub Copilot skills
    ├── schemas/                # Data schemas & contracts
    ├── personas/               # 100 learner persona portfolios
    ├── templates/              # 50 project starter templates
    ├── guidebooks/             # 25+ in-depth guidebooks
    ├── playbooks/              # Operational playbooks
    ├── presentations/          # Workshop slide decks
    └── phase-4/                # Phase 4 product ecosystem docs
        ├── README.md           # Phase 4 overview
        ├── tools/              # Vibe Starter, Prompt Library, AI Tool Comparison
        ├── community/          # Code Jam, Regional Workshops, University Partnerships
        └── revenue/            # Sponsorship, Curriculum Licensing, Book
```

---

## 🏗️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Vanilla HTML5, CSS3 (custom properties, grid, flexbox) |
| Typography | Inter (body), JetBrains Mono (code) via system fonts |
| Deployment | GitHub Pages (or compatible static host) |
| AI Tools (Workshop) | Claude, Cursor, v0 |
| Deploy (Workshop) | Vercel, Supabase |
| Version Control | Git + GitHub |

---

## 🚀 Quick Start

```bash
# Clone the repository
git clone https://github.com/Krosebrook/vibe-coding-workshop.git
cd vibe-coding-workshop

# Open locally (no build step required)
open index.html
# or
npx serve .
```

See [SETUP.md](SETUP.md) for full local development instructions.

---

## 🎯 What Participants Build

| Project | Description | Skills |
|---------|-------------|--------|
| **01** Personal Landing Page | Describe your ideal portfolio and iterate | Prompt → Output → Refine |
| **02** Mood Tracker with Charts | Interactive app with state & data viz | State management, charting |
| **03** Recipe Finder with API | Real data from a public API | API integration, error handling |
| **04** AI Chat Assistant | Streaming AI chat with message history | AI integration, deployment |

---

## 📋 Workshop Phases

```
Morning      → Learn the Scales        (AI tool fundamentals, prompting patterns)
Late Morning → Build Your First Two    (Projects 01 & 02, guided)
Afternoon    → Go Off-Script           (Projects 03 & 04, open-ended)
End of Day   → Ship It                 (Deploy to live URLs)
```

---

## 🔍 Audit Summary

> Conducted: March 2026 | Auditor: GitHub Copilot | Updated: March 2026

### Phase 1 Audit — Workshop Day Phases (4 Phases)

| Phase | Time of Day | Content | Status |
|-------|-------------|---------|--------|
| 1 — Learn the Scales | Morning | AI tool fundamentals, hallucination, prompt → output → refine loop | ✅ Verified |
| 2 — Build Your First Two | Late Morning | Projects 01 (Landing Page) + 02 (Mood Tracker), guided, hands-on | ✅ Verified |
| 3 — Go Off-Script | Afternoon | Projects 03 (Recipe API) + 04 (AI Chat), open-ended | ✅ Verified |
| 4 — Ship It | End of Day | Deploy all 4 apps to real URLs via Vercel | ✅ Verified |

**Findings:** All 4 phases are logically sound and internally consistent across `index.html`, playbook PB01, and `README.md`. Phase timing in the playbook (8-hour day, 0:00–8:00) aligns with the high-level day structure described in the site.

---

### ✅ Strengths
- Clean, minimal semantic HTML5 with proper `lang` attribute and meta charset
- Responsive design using CSS Grid and Flexbox with media queries
- CSS custom properties (design tokens) for consistent theming
- Accessible color contrast on primary text elements
- Smooth scroll behavior, sticky navigation with blur backdrop
- No external JavaScript dependencies — zero attack surface
- Cohesive visual identity (dark theme, purple accent, monospace terminal)
- SEO meta description, Open Graph, and Twitter Card tags *(added Phase 1)*
- `aria-label` on nav links, form inputs, and landmark `role="main"` *(added Phase 1)*
- Favicon and apple-touch-icon *(added Phase 1)*
- `robots.txt`, `sitemap.xml`, `_headers` security file *(added Phase 1)*
- GitHub Actions CI for HTML validation *(added Phase 1)*
- Dependabot for automated dependency updates *(added Phase 1)*

### ⚠️ Improvement Opportunities
- **Form UX**: Waitlist form needs a real email service backend (Resend, Mailchimp)
- **Content**: Instructor bio photo, project screenshots, demo video still needed
- **SEO**: Blog post / landing page "What is vibe coding?" would improve organic reach
- **Privacy**: Cookie/analytics consent banner if analytics are added
- **PWA**: Add `manifest.json` and service worker for offline support

### 📊 Scores (Estimated Lighthouse)
| Metric | Score |
|--------|-------|
| Performance | 98 |
| Accessibility | 93 (aria-labels, role=main added) |
| Best Practices | 97 |
| SEO | 95 (meta description, OG tags, sitemap added) |

---

## 🤝 Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on how to contribute to this project.

---

## 📜 License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

## 📞 Contact

- **Email:** [hello@vibecodingworkshop.com](mailto:hello@vibecodingworkshop.com)
- **GitHub:** [@Krosebrook](https://github.com/Krosebrook)
- **Location:** Grayslake, IL (Chicago area)

---

*Built for beginners, by builders.* 🛠️
