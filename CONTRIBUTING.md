# Contributing to Vibe Coding Workshop

Thank you for your interest in contributing! This project is maintained by Kyle Rosebrook and welcomes contributions from the community.

---

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How to Contribute](#how-to-contribute)
- [Types of Contributions](#types-of-contributions)
- [Development Setup](#development-setup)
- [Pull Request Process](#pull-request-process)
- [Commit Message Convention](#commit-message-convention)
- [Style Guide](#style-guide)
- [Reporting Bugs](#reporting-bugs)
- [Suggesting Features](#suggesting-features)
- [Questions](#questions)

---

## Code of Conduct

By participating in this project, you agree to abide by our [Code of Conduct](CODE_OF_CONDUCT.md). Please read it before contributing.

---

## How to Contribute

1. **Fork** the repository
2. **Create** a feature branch: `git checkout -b feat/your-feature-name`
3. **Make** your changes
4. **Test** locally by opening `index.html` in a browser
5. **Commit** your changes: `git commit -m "feat: add descriptive message"`
6. **Push** to your fork: `git push origin feat/your-feature-name`
7. **Open** a Pull Request against `main`

---

## Types of Contributions

### 🐛 Bug Fixes
Fixes to HTML, CSS, or documentation errors. Always welcome — no issue needed for small fixes.

### ✨ Site Improvements
Enhancements to the marketing site (accessibility, SEO, performance). Open an issue first to discuss approach.

### 📚 Documentation
Improvements to any file in `docs/`. Grammar fixes, clarifications, and additions are always welcome.

### 🎨 Design Changes
Changes to colors, layout, or visual design require discussion first. Open an issue describing the proposed change.

### 📝 Curriculum Content
Additions to templates, personas, guidebooks, or playbooks. Follow the format of existing documents in `docs/`.

### 🔌 New Templates or Skills
New workshop project templates or prompting skills. Follow the template format in `docs/templates/README.md`.

---

## Development Setup

See [SETUP.md](SETUP.md) for detailed instructions. In short:

```bash
git clone https://github.com/Krosebrook/vibe-coding-workshop.git
cd vibe-coding-workshop
open index.html  # or use: npx serve .
```

No build step required. The site is a single `index.html` file.

---

## Pull Request Process

1. **Link the related issue** in your PR description using `Closes #123`
2. **Describe your changes** clearly — what you changed and why
3. **Include screenshots** for any visual changes
4. **Keep PRs focused** — one logical change per PR
5. **Respond to review feedback** within 7 days or the PR may be closed
6. PRs require **one approving review** before merge

### PR Title Format
```
type: short description (max 72 chars)

Types: feat | fix | docs | style | refactor | a11y | perf | chore
```

---

## Commit Message Convention

We follow [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>(<scope>): <short description>

<optional body>

<optional footer>
```

**Types:**
- `feat` — new feature
- `fix` — bug fix
- `docs` — documentation only
- `style` — CSS/visual changes
- `a11y` — accessibility improvements
- `perf` — performance improvements
- `refactor` — code refactoring
- `chore` — maintenance tasks

**Examples:**
```
feat(site): add Open Graph meta tags for social sharing
fix(a11y): add aria-label to navigation links
docs(personas): add 10 new learner persona profiles
style(hero): increase hero heading font size on mobile
```

---

## Style Guide

### HTML
- 2-space indentation
- Semantic HTML5 elements (`<nav>`, `<section>`, `<article>`, `<footer>`)
- `alt` text on all images
- `aria-label` on interactive elements without visible text labels
- Keep inline styles minimal; prefer CSS classes

### CSS
- Use CSS custom properties (variables) for all colors and spacing
- Class names are `kebab-case`
- Mobile-first approach where applicable
- No `!important` except in reset styles
- Comment major sections

### Markdown
- Use ATX-style headings (`#`, not underlines)
- Fenced code blocks with language identifier
- Blank line between paragraphs
- 80-character line limit for prose (not code)

---

## Reporting Bugs

1. Check existing [Issues](https://github.com/Krosebrook/vibe-coding-workshop/issues) first
2. Use the Bug Report issue template
3. Include:
   - Browser and version
   - Operating system
   - Steps to reproduce
   - Expected behavior
   - Actual behavior
   - Screenshot (if visual)

---

## Suggesting Features

1. Open a [Feature Request](https://github.com/Krosebrook/vibe-coding-workshop/issues/new) issue
2. Describe the problem it solves
3. Describe your proposed solution
4. Note any alternatives considered

Feature requests are reviewed by Kyle Rosebrook. Features aligned with the workshop curriculum take priority.

---

## Questions

- **General questions:** Open a [Discussion](https://github.com/Krosebrook/vibe-coding-workshop/discussions)
- **Workshop inquiries:** [hello@vibecodingworkshop.com](mailto:hello@vibecodingworkshop.com)
- **Security issues:** See [SECURITY.md](SECURITY.md)

---

*Thank you for helping make Vibe Coding Workshop better for everyone.* 🙌
