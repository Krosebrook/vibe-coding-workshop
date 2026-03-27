# AI Agents — Vibe Coding Workshop

> Documentation for AI agents configured to assist with this repository and workshop operations.

---

## Overview

This document catalogs all AI agents relevant to the Vibe Coding Workshop project — their roles, capabilities, configuration, and usage patterns.

---

## Agent Roster

### 1. GitHub Copilot (Repository Agent)

**Role:** In-editor code completion and documentation generation  
**Scope:** This GitHub repository  
**Capabilities:**
- HTML/CSS completion and suggestions
- Markdown documentation drafting
- Commit message suggestions
- PR description generation
- Code review comments

**Configuration Files:**
- `.github/copilot-instructions.md` (if present)
- `CLAUDE.md` (context file, also read by Copilot)

**Usage in This Repo:**
- Generating and editing `index.html` structure
- Drafting documentation in `docs/`
- Reviewing accessibility and SEO improvements

---

### 2. Claude (Anthropic)

**Role:** Primary AI coding assistant for both the repo and the workshop  
**Context File:** [`CLAUDE.md`](../CLAUDE.md)  
**Capabilities:**
- Code generation and explanation
- Documentation writing
- Prompt engineering for workshop exercises
- Accessibility and security review
- Curriculum content development

**Workshop Usage:**
- Primary tool for Projects 01–04
- Students use Claude.ai or Claude via Cursor
- Streaming responses demonstrated in Project 04

---

### 3. Cursor (AI Code Editor)

**Role:** IDE-level AI coding assistant  
**Type:** Desktop application (wraps VS Code + Claude/GPT)  
**Workshop Usage:** Primary development environment for all 4 projects  

**Key Features Used:**
- `Cmd+K` — inline code edit with natural language
- `Cmd+L` — chat panel for architectural questions
- `Composer` — multi-file editing via conversation
- `.cursorrules` — project-specific AI behavior rules

**Cursor Rules for Workshop Projects:**
```
You are a patient coding mentor helping someone who has never written code.
Always explain what you're doing in plain English.
Prefer simple, readable code over clever code.
Use comments to explain every block.
When you make a change, describe what changed and why.
```

---

### 4. v0 (Vercel AI)

**Role:** UI component generation from text descriptions  
**Workshop Usage:** Used in Project 01 (Personal Landing Page) for rapid iteration  
**URL:** https://v0.dev

**When to Use v0:**
- Generating initial UI layouts from a text description
- Getting React components to copy into a project
- Rapid visual prototyping before refinement

---

### 5. Gemini (Google)

**Role:** Research, content generation, SEO, competitive analysis  
**Context File:** [`docs/gemini.md`](gemini.md)  
**Workshop Usage:** Not used directly in workshop projects; used for repo management

---

### 6. Copilot Skills (Custom)

**Role:** Specialized skills for common workshop tasks  
**Documentation:** [`docs/copilot-skills/`](copilot-skills/)  

**Available Skills:**
- `explain-error` — explain a programming error in plain English
- `fix-accessibility` — find and fix ARIA/accessibility issues
- `add-seo-tags` — add Open Graph and meta tags to HTML
- `write-readme` — generate a README for a project
- `deploy-checklist` — pre-deployment checklist for Vercel

---

## Agent Interaction Patterns

### Pattern 1: Prompt → Refine Loop

Used in all 4 workshop projects:
```
1. User describes desired feature in plain English
2. Claude/Cursor generates code
3. User runs code and evaluates result
4. User refines prompt ("make it more X, less Y")
5. Repeat until satisfied
```

### Pattern 2: Debug with AI

When something breaks:
```
1. Copy the error message
2. Paste into Claude: "I got this error: [error]. Here is my code: [code]. What's wrong?"
3. Claude explains and suggests a fix
4. Apply fix
5. If still broken, paste new error back (context carries over in conversation)
```

### Pattern 3: Architecture Consultation

For bigger decisions:
```
1. Describe what you want to build (not the code — the concept)
2. Ask: "What's the simplest way to build this?"
3. Let Claude propose an approach
4. Ask clarifying questions until you understand the structure
5. Then ask Claude to write the first file
```

### Pattern 4: Code Explanation

For understanding code you didn't write:
```
1. Paste the code into Claude
2. Ask: "Explain this code to me like I'm not a programmer"
3. Ask follow-up questions about any parts that are still unclear
```

---

## Agent Governance

### What Agents Can Do
- Generate and modify code files in this repo
- Create and edit documentation
- Suggest improvements to HTML, CSS, and content

### What Agents Cannot Do
- Commit directly to `main` without PR review
- Change workshop curriculum dates or pricing
- Add analytics or tracking scripts
- Store user data

### Review Requirements
All AI-generated code that modifies the live marketing site requires:
- [ ] Visual review in browser
- [ ] Accessibility check (keyboard nav, screen reader)
- [ ] Cross-browser check (Chrome + Firefox)
- [ ] One human approval in PR

---

## Prompting Best Practices

### For Site Changes
```
Context: I have a static HTML marketing site for a coding workshop.
Task: Add [X feature/section].
Constraints: No JavaScript. No external dependencies. Match the existing dark theme (--accent: #7c3aed).
Output: The HTML and CSS to add, with a comment showing where to insert it.
```

### For Documentation
```
Context: This is documentation for [audience] who [background/goal].
Task: Write [type of document] about [topic].
Tone: Direct, honest, beginner-friendly. No jargon.
Length: [approximate].
```

### For Workshop Exercises
```
Context: I'm a student at a one-day coding workshop. I have no coding experience.
Task: Help me build [Project X].
Teaching mode: Explain every step. Don't just give me code — tell me what it does.
Goal: A working [outcome] by end of workshop.
```

---

*See also: [docs/copilot-skills/](copilot-skills/) | [CLAUDE.md](../CLAUDE.md) | [docs/gemini.md](gemini.md)*
