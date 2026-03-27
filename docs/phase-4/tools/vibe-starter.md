# Vibe Starter — Project Scaffolding Tool

> An opinionated CLI that scaffolds a new vibe coding project in seconds — the right structure, the right defaults, ready to build.

---

## What Is Vibe Starter?

Vibe Starter is a command-line tool that generates a fully configured project starter for vibe coding sessions. Instead of spending 30 minutes setting up file structure, configs, and boilerplate, you run one command and start building.

It reflects everything learned from running 50+ workshop projects — the folder structure that works, the defaults that don't surprise beginners, and the configs that don't get in the way.

```bash
npx vibe-starter my-app
```

That's it. You're building.

---

## Core Goals

1. **Zero configuration for beginners** — sensible defaults for everything
2. **Cursor-ready** — includes `.cursorrules` tuned for vibe coding
3. **Claude-ready** — includes `CLAUDE.md` context file for the project
4. **Multiple templates** — match the right starter to the right project type
5. **Vercel-ready** — one `vercel.json` to deploy immediately
6. **Extensible** — advanced users can customize without fighting the tool

---

## CLI Interface

### Basic Usage

```bash
# Scaffold with interactive prompts
npx vibe-starter

# Scaffold with name and default template
npx vibe-starter my-project

# Scaffold with specific template
npx vibe-starter my-project --template landing-page

# List available templates
npx vibe-starter --list

# Show version
npx vibe-starter --version
```

### Interactive Mode

When run without arguments, Vibe Starter prompts:

```
┌─────────────────────────────────────┐
│   Vibe Starter — vibe coding setup  │
└─────────────────────────────────────┘

? Project name: › my-awesome-app
? Choose a template: › (Use arrow keys)
  ❯ landing-page     — Personal or business landing page
    mood-tracker     — App with state + localStorage
    api-explorer     — App that fetches from a public API
    ai-chat          — AI-powered chat assistant
    custom           — Minimal scaffolding, build from scratch

? Include Cursor rules? › (Y/n)
? Include Claude.md context file? › (Y/n)
? Initialize git? › (Y/n)

✓ Created my-awesome-app/
✓ Added .cursorrules
✓ Added CLAUDE.md
✓ Initialized git repo

→ cd my-awesome-app
→ open index.html
→ Start building. Good luck.
```

---

## Generated Project Structure

### Landing Page Template

```
my-app/
├── index.html          ← Starter HTML with semantic structure
├── style.css           ← CSS custom properties + base styles
├── CLAUDE.md           ← AI context file for the project
├── .cursorrules        ← Cursor IDE rules for this project type
├── vercel.json         ← One-click deploy config
├── .gitignore          ← Sensible defaults
└── README.md           ← "How to keep building" guide
```

### AI Chat Template

```
my-app/
├── index.html          ← Chat UI starter
├── style.css           ← Chat component styles
├── app.js              ← Claude API integration (starter)
├── .env.example        ← Shows required env vars
├── CLAUDE.md           ← AI context for the project
├── .cursorrules        ← Cursor rules tuned for AI projects
├── vercel.json         ← Deploy config with env var notes
├── .gitignore          ← Includes .env
└── README.md           ← Setup instructions
```

---

## Templates

| Template ID | Name | Stack | Workshop Project |
|-------------|------|-------|-----------------|
| `landing-page` | Personal/Business Landing Page | HTML + CSS | Project 01 |
| `mood-tracker` | Mood & Habit Tracker | HTML + CSS + JS | Project 02 |
| `api-explorer` | API Explorer | HTML + CSS + JS + Fetch | Project 03 |
| `ai-chat` | AI Chat Assistant | HTML + CSS + JS + Claude API | Project 04 |
| `custom` | Minimal Starter | HTML + CSS only | Any |

---

## Default `.cursorrules` Content

Every generated project includes a `.cursorrules` file tuned for vibe coding:

```
You are a patient coding mentor helping someone who may be new to coding.

When generating code for this project:
- Always explain what you are doing in plain English before the code block
- Prefer simple, readable code over clever or concise code
- Add a comment above every logical block explaining what it does
- Use semantic HTML5 elements
- Use CSS custom properties for colors and spacing
- When you make a change, describe what changed and why at the end

When the user asks a question:
- Answer in plain English first
- Use an analogy if the concept is abstract
- Then show the code

Don't ask clarifying questions unless something is truly ambiguous.
Default to the simplest version that works.
```

---

## Default `CLAUDE.md` Content (Generated)

```markdown
# [Project Name] — Claude Context

## What This Is
[Generated description based on template choice]

## Tech Stack
- HTML5 + CSS3 (no frameworks)
- [JS if included]
- [API if applicable]

## Design Rules
- Dark theme preferred
- CSS custom properties for all colors
- Mobile-first, responsive

## Do Not
- Add external libraries without asking
- Use JavaScript frameworks
- Change the color scheme without asking
```

---

## Technical Architecture

### Technology Choices

| Decision | Choice | Rationale |
|----------|--------|-----------|
| Distribution | npm (npx) | No install required for users |
| Language | Node.js (ESM) | Widely available, no compilation |
| Prompts | `@inquirer/prompts` | Actively maintained, accessible |
| File generation | `fs/promises` + template literals | No heavy templating engine needed |
| Testing | Vitest | Fast, ESM-native |

### File Structure (The Tool Itself)

```
vibe-starter/
├── src/
│   ├── index.js           ← CLI entry point
│   ├── scaffold.js        ← Project generation logic
│   ├── templates/
│   │   ├── landing-page/
│   │   ├── mood-tracker/
│   │   ├── api-explorer/
│   │   ├── ai-chat/
│   │   └── custom/
│   └── utils/
│       ├── prompts.js     ← Interactive prompt flows
│       └── logger.js      ← Formatted terminal output
├── tests/
│   ├── scaffold.test.js
│   └── templates.test.js
├── package.json
└── README.md
```

---

## Development Roadmap

### v0.1.0 — Alpha
- [ ] `landing-page` template
- [ ] `ai-chat` template
- [ ] `.cursorrules` generation
- [ ] `CLAUDE.md` generation
- [ ] Basic interactive prompts
- [ ] `--list` flag

### v0.2.0 — Beta
- [ ] All 5 templates
- [ ] `vercel.json` generation
- [ ] `--template` flag
- [ ] `--no-git` flag
- [ ] Error handling + helpful messages

### v1.0.0 — Stable
- [ ] Custom template support (`--template ./my-template`)
- [ ] Update checker
- [ ] Telemetry opt-in (anonymous usage stats only)
- [ ] GitHub Actions CI template
- [ ] Docs site

---

## Contribution Guide

### Adding a Template

1. Create a folder in `src/templates/[template-name]/`
2. Add all scaffold files (use `{{PROJECT_NAME}}` as a placeholder)
3. Add a `template.json` manifest:
   ```json
   {
     "id": "template-name",
     "name": "Human Readable Name",
     "description": "One sentence description",
     "workshopProject": "01",
     "files": ["index.html", "style.css", "README.md"]
   }
   ```
4. Add tests in `tests/templates.test.js`
5. Update this README with the new template

### Improving `.cursorrules`

The default `.cursorrules` is living documentation. Open a PR with your improvement and a short rationale. The rule: every change should make vibe coding more accessible for beginners.

---

## FAQ

**Q: Is this only for workshop participants?**  
A: No. Anyone who wants a solid starting point for an AI-assisted project can use Vibe Starter.

**Q: Can I use it with Windsurf, Copilot, or other AI editors?**  
A: The `.cursorrules` file is Cursor-specific, but the generated code and `CLAUDE.md` work with any AI tool. We plan to add `.github/copilot-instructions.md` support in v0.2.0.

**Q: Does this require Node.js?**  
A: Yes. Node.js 18+ required. We chose npm/npx because it's the most widely available option for beginners.

**Q: Can I customize the default `.cursorrules`?**  
A: Yes. Edit the generated file after scaffolding. You can also pass `--cursor-rules ./my-rules.txt` in v1.0.0.

---

*See also: [Prompt Library](prompt-library.md) | [AI Tool Comparison](ai-tool-comparison.md) | [Phase 4 Overview](../README.md)*
