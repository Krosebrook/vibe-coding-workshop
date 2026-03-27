# Vibe Coding Skills Library

> A library of learnable skills for AI-assisted software development. Each skill is a named, teachable pattern.

---

## What Is a "Vibe Coding Skill"?

A skill is a repeatable, named technique for working effectively with AI coding tools. Skills can be learned, practiced, and refined. This library documents the core skills taught in the workshop and extended skills for continued growth.

---

## Core Skills (Taught in Workshop)

### Skill 01 — Describe-First Development

**Level:** Beginner  
**Taught In:** Project 01  

Describe what you want to build *before* asking for code. Start with the experience, not the implementation.

**Bad approach:**
```
Write me an HTML page.
```

**Good approach:**
```
I want a personal portfolio page. It should have:
- My name and a one-sentence tagline at the top
- A section listing 3 projects I've worked on
- My email at the bottom
Dark background, minimal design. No JavaScript.
```

---

### Skill 02 — Iterative Refinement

**Level:** Beginner  
**Taught In:** Project 01  

Accept imperfect output and refine with natural language. Every iteration gets you closer.

**Pattern:**
```
First: "Build me [X]"
Then: "The [element] looks too [quality]. Make it more [desired quality]."
Then: "Change the [color/size/position] to [specific value]."
```

**Key insight:** You don't need to know the CSS property. Describe the visual result you want.

---

### Skill 03 — Error-First Debugging

**Level:** Beginner  
**Taught In:** Projects 01 & 02  

When something breaks, copy the error message and paste it to Claude with your code. Let AI explain what went wrong.

**Template:**
```
I got this error: [error message]

Here is my code:
[paste code]

What's wrong and how do I fix it?
```

---

### Skill 04 — State Thinking

**Level:** Intermediate  
**Taught In:** Project 02 (Mood Tracker)  

Before asking AI to add interactivity, describe what "states" your app can be in.

**Template:**
```
My app can be in these states:
- Empty (no entries yet)
- Has entries (showing list)
- Editing (user clicked an entry)

How should I store this data and switch between views?
```

---

### Skill 05 — API Integration Pattern

**Level:** Intermediate  
**Taught In:** Project 03 (Recipe Finder)  

A structured prompt pattern for adding external API calls.

**Template:**
```
I want to call this API: [API URL / documentation link]
When the user [trigger], I want to fetch [data].
Show a loading state while fetching.
Show an error message if the fetch fails.
Display the result as [description of UI].
```

---

### Skill 06 — Persona Prompting

**Level:** Intermediate  
**Taught In:** Project 04 (AI Chat)  

Give your AI chat assistant a personality and constraints before writing the code.

**Template:**
```
My AI assistant is named [name].
Personality: [3 adjectives]
It specializes in: [domain]
It should always: [behavior]
It should never: [constraint]
Tone: [description]

Now build a chat interface that uses this system prompt.
```

---

### Skill 07 — Component Decomposition

**Level:** Intermediate  
**Taught In:** Projects 02–04  

Break a complex UI into named components before coding.

**Template:**
```
I'm building [app name]. Break the UI into components:
- What are the major sections?
- What does each section do?
- Which sections share data?

Don't write code yet. Just describe the structure.
```

---

### Skill 08 — Deploy Readiness Check

**Level:** Beginner  
**Taught In:** End of Day (Ship It)  

Before deploying, run through this checklist with Claude.

**Template:**
```
I'm about to deploy my [app name] to Vercel.
Here is my code: [paste or describe]

Check for:
1. Any broken links or missing files
2. Any hardcoded local paths
3. Any console.log statements I should remove
4. Any API keys exposed in the code
5. Mobile responsiveness issues
```

---

## Extended Skills

### Skill 09 — Refactor for Readability

Ask Claude to improve code you've already written without changing its behavior.

```
Refactor this code to be more readable. Keep the behavior exactly the same.
Add comments explaining what each section does.
[paste code]
```

### Skill 10 — Test-Case Generation

Ask Claude to write test cases for your code.

```
Write 5 test cases for this function. Include edge cases.
[paste function]
```

### Skill 11 — Accessibility Audit

```
Review this HTML for accessibility issues. Check for:
- Missing alt text
- Missing aria-labels
- Color contrast issues
- Keyboard navigation
[paste HTML]
```

### Skill 12 — Performance Optimization

```
Review this code for performance issues. I'm targeting:
- Fast initial load
- No render-blocking resources
- Minimal memory usage
[paste code]
```

### Skill 13 — Security Review

```
Review this code for security vulnerabilities. Look for:
- Exposed API keys
- XSS vulnerabilities
- Unsafe eval or innerHTML usage
- CORS misconfigurations
[paste code]
```

### Skill 14 — Documentation Generation

```
Generate documentation for this code. Include:
- What it does (one sentence)
- Parameters (if any)
- Return value (if any)
- Usage example
[paste code]
```

### Skill 15 — Progressive Enhancement

```
I have this basic working feature: [describe]
Add progressive enhancement so it:
1. Works without JavaScript
2. Works better with JavaScript
3. Works best on modern browsers with CSS support
```

---

## Skill Progression Map

```
Beginner
│
├── Describe-First Development (01)
├── Iterative Refinement (02)
├── Error-First Debugging (03)
└── Deploy Readiness Check (08)
│
Intermediate
│
├── State Thinking (04)
├── API Integration Pattern (05)
├── Persona Prompting (06)
└── Component Decomposition (07)
│
Advanced
│
├── Refactor for Readability (09)
├── Test-Case Generation (10)
├── Accessibility Audit (11)
├── Performance Optimization (12)
├── Security Review (13)
├── Documentation Generation (14)
└── Progressive Enhancement (15)
```

---

*Have a skill to contribute? See [CONTRIBUTING.md](../../CONTRIBUTING.md).*
