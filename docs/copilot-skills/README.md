# Custom GitHub Copilot Skills

> Specialized Copilot skills (custom instructions) for the Vibe Coding Workshop repository and workshop participants.

---

## What Are Copilot Skills?

GitHub Copilot Skills are custom AI instructions configured to perform specific, repeatable tasks relevant to your project. They can be invoked via natural language in Copilot Chat.

---

## Workshop Copilot Skills

### Skill: `explain-error`

**Trigger:** "@workspace explain this error"  
**Purpose:** Translate programming errors into plain English for beginners

**Custom Instruction:**
```
When a user pastes an error message, explain it as if talking to someone who has never coded before. 

Format your response as:
1. **What happened** (one sentence, plain English)
2. **Why it happened** (the underlying cause, no jargon)
3. **How to fix it** (step-by-step, numbered)
4. **How to prevent it** (one tip)

Never say "simple," "just," or "obviously."
```

---

### Skill: `fix-accessibility`

**Trigger:** "@workspace check accessibility"  
**Purpose:** Find and fix WCAG 2.1 AA accessibility issues in HTML

**Custom Instruction:**
```
Review the provided HTML for accessibility issues. Check for:

1. Missing alt text on images (alt="" for decorative, descriptive for meaningful)
2. Missing aria-label on buttons/links with no visible text
3. Missing <label> elements for form inputs
4. Insufficient color contrast (must meet WCAG 2.1 AA: 4.5:1 for text, 3:1 for large text)
5. Missing role attributes where needed
6. Improper heading hierarchy (h1 → h2 → h3, no skipping)
7. Missing lang attribute on <html>
8. Links that just say "click here" or "read more"

For each issue found:
- Quote the offending HTML
- Explain why it's a problem
- Provide the fixed version
```

---

### Skill: `add-seo-tags`

**Trigger:** "@workspace add SEO tags"  
**Purpose:** Add complete Open Graph, Twitter Card, and standard meta tags

**Custom Instruction:**
```
Add SEO meta tags to the provided HTML <head> section. Include:

Standard meta:
- <meta name="description" content="[150-160 chars]">
- <meta name="keywords" content="[relevant, comma, separated]">
- <link rel="canonical" href="[URL]">

Open Graph (Facebook/LinkedIn):
- og:title
- og:description  
- og:image (1200x630px recommended)
- og:url
- og:type (usually "website")
- og:site_name

Twitter Card:
- twitter:card (use "summary_large_image")
- twitter:title
- twitter:description
- twitter:image

Ask for: site URL, site name, description, and image URL if not provided.
```

---

### Skill: `write-readme`

**Trigger:** "@workspace write readme"  
**Purpose:** Generate a project README from code or description

**Custom Instruction:**
```
Generate a README.md for the described project. Include these sections:

# [Project Name]
> One-sentence description

## What It Does
Brief explanation in plain English (2-3 sentences)

## Live Demo
[Link or "Coming soon"]

## Tech Stack
- List of technologies

## Getting Started
Step-by-step setup instructions

## How to Use
Key user flows

## Features
- Bullet list of features

## Contributing
Brief contribution note + link to CONTRIBUTING.md

## License
[License type]

Use the same direct, beginner-friendly tone used throughout this workshop.
```

---

### Skill: `deploy-checklist`

**Trigger:** "@workspace deploy checklist"  
**Purpose:** Pre-deployment safety check for workshop projects

**Custom Instruction:**
```
Run a pre-deployment checklist on the provided code. Check for and fix:

🔐 Security:
- [ ] No API keys or secrets in code (use environment variables)
- [ ] No hardcoded passwords
- [ ] No console.log with sensitive data

🧹 Cleanup:
- [ ] Remove all console.log debug statements
- [ ] Remove commented-out old code
- [ ] Remove TODO comments (or convert to GitHub Issues)

🔗 Links & Assets:
- [ ] All image src and href paths work
- [ ] No localhost URLs hardcoded
- [ ] All external links use https://

📱 Responsiveness:
- [ ] Test on 375px width (iPhone SE)
- [ ] Test on 768px width (tablet)
- [ ] Test on 1280px width (desktop)

♿ Accessibility:
- [ ] All images have alt text
- [ ] Form inputs have labels
- [ ] Page has a single h1

Report any issues found with the file and line number.
```

---

### Skill: `vibe-prompt`

**Trigger:** "@workspace vibe prompt for [feature]"  
**Purpose:** Generate an optimized prompt for a common workshop feature

**Custom Instruction:**
```
Generate an AI prompting template for the requested feature. The template should be usable by a coding beginner with Claude or Cursor.

Format:
## Prompt for: [Feature Name]

**Context block:**
[Set up the context — what project this is, what already exists]

**Task block:**
[Clear instruction for what to build]

**Output format block:**
[Describe what you want back — code only, with explanation, etc.]

**Constraints block:**
[List any constraints — no JS, match existing style, etc.]

**Example usage:**
[Show a filled-in example of the prompt]

Keep the template beginner-friendly. Use [PLACEHOLDERS] for things the user needs to fill in.
```

---

### Skill: `add-dark-mode`

**Trigger:** "@workspace add dark mode"  
**Purpose:** Add a dark/light mode toggle to a project

**Custom Instruction:**
```
Add dark mode support to this HTML/CSS project. Steps:

1. Add CSS custom properties for both themes to :root and [data-theme="dark"]
2. Add a theme toggle button with accessible label
3. Write minimal JavaScript to toggle data-theme on <html>
4. Save preference to localStorage
5. Respect prefers-color-scheme media query by default

Keep the implementation simple — beginners should be able to understand every line.
```

---

### Skill: `chart-component`

**Trigger:** "@workspace add chart"  
**Purpose:** Add a data visualization to a project

**Custom Instruction:**
```
Add a chart component using Chart.js (CDN, no build required).

Ask for:
- Chart type (bar, line, pie, doughnut)
- Data source (static, from state variable, from API)
- Color preferences

Generate:
1. CDN script tag to add to <head>
2. <canvas> element with appropriate id and aria-label
3. JavaScript to initialize the chart
4. Brief explanation of how to update the data

Ensure the chart has:
- A title
- Accessible color contrast
- Responsive sizing
```

---

## Configuring These Skills

### Via `.github/copilot-instructions.md`

Create this file to give Copilot persistent context:

```markdown
# Copilot Instructions for Vibe Coding Workshop

This repository is for a hands-on coding workshop for beginners.

Key context:
- Primary file: index.html (static HTML + CSS, no JavaScript)
- Audience: Non-technical people learning to build with AI
- Tone: Direct, warm, beginner-friendly
- Design: Dark theme (#0a0a0a bg, #7c3aed accent)

When suggesting code:
- Explain every change in plain English
- Prefer readable over clever
- Add comments to all new code blocks
- Never add npm packages without asking

When generating documentation:
- Assume zero technical background
- Define jargon when it must be used
- Use the voice in CLAUDE.md
```

---

*See also: [docs/agents.md](../agents.md) | [docs/skills/README.md](../skills/README.md)*
