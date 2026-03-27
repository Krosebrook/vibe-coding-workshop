# Plugins & Extensions

> Recommended plugins, extensions, and browser add-ons for vibe coding. Organized by tool and use case.

---

## VS Code / Cursor Extensions

### Must-Have for the Workshop

| Extension | ID | Purpose |
|-----------|-----|---------|
| **Live Server** | `ritwickdey.LiveServer` | Local dev server with live reload |
| **Prettier** | `esbenp.prettier-vscode` | Code formatting |
| **Path Intellisense** | `christian-kohler.path-intellisense` | File path autocomplete |
| **Color Highlight** | `naumovs.color-highlight` | Visualize hex/CSS colors inline |
| **Auto Rename Tag** | `formulahendry.auto-rename-tag` | Rename paired HTML tags together |

### Accessibility

| Extension | ID | Purpose |
|-----------|-----|---------|
| **axe Accessibility Linter** | `deque-systems.vscode-axe-linter` | Inline accessibility errors |
| **HTMLHint** | `mkaufman.HTMLHint` | HTML validation and best practices |

### Git & GitHub

| Extension | ID | Purpose |
|-----------|-----|---------|
| **GitLens** | `eamodio.gitlens` | Enhanced Git integration |
| **GitHub Pull Requests** | `GitHub.vscode-pull-request-github` | PR management in editor |

### Productivity

| Extension | ID | Purpose |
|-----------|-----|---------|
| **Bracket Pair Colorizer** | Built into VS Code 1.60+ | Color-matched brackets |
| **TODO Highlight** | `wayou.vscode-todo-highlight` | Highlight TODO/FIXME comments |
| **Error Lens** | `usernameherer.errorlens` | Inline error messages |

---

## Browser Extensions

### Accessibility Testing

| Extension | Browser | Purpose |
|-----------|---------|---------|
| **axe DevTools** | Chrome/Firefox | Automated accessibility testing |
| **WAVE** | Chrome/Firefox | Visual accessibility report |
| **Colour Contrast Analyser** | Chrome | Check WCAG color contrast |
| **HeadingsMap** | Chrome/Firefox | Visualize heading structure |

### Performance & SEO

| Extension | Browser | Purpose |
|-----------|---------|---------|
| **Lighthouse** | Chrome (built-in DevTools) | Performance/a11y/SEO audit |
| **WebPageTest** | Chrome | Performance profiling |
| **SEO Meta in 1 Click** | Chrome | View all meta tags at once |

### Development

| Extension | Browser | Purpose |
|-----------|---------|---------|
| **React DevTools** | Chrome/Firefox | Debug React component trees |
| **JSON Formatter** | Chrome | Pretty-print JSON API responses |
| **ModHeader** | Chrome | Inject custom HTTP headers for testing |
| **EditThisCookie** | Chrome | Inspect and edit cookies |

---

## Cursor-Specific Configuration

### Recommended Settings (`settings.json`)

```json
{
  "editor.fontSize": 14,
  "editor.tabSize": 2,
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.wordWrap": "on",
  "files.autoSave": "onFocusChange",
  "editor.minimap.enabled": false,
  "workbench.colorTheme": "GitHub Dark Default",
  "editor.fontFamily": "'JetBrains Mono', 'Fira Code', monospace",
  "editor.fontLigatures": true
}
```

### `.cursorrules` for Workshop Projects

Place this file in your project root during the workshop:

```
You are a patient, encouraging AI coding mentor.

Guidelines:
- Always explain what you're doing in plain English before writing code
- Prefer simple, readable code over clever or concise code
- Use comments to explain every function and major block
- When making changes, describe what changed and why
- If the user seems confused, offer a simpler explanation
- Never assume the user knows technical jargon — always define terms
- Always suggest testing after making changes
- Celebrate small wins

Project context:
- This is a workshop project built by someone new to coding
- Errors are expected and are learning opportunities
- The goal is a working, deployed app — not perfect code
```

---

## AI Tool Plugins

### Claude Integrations

| Integration | Purpose | Link |
|------------|---------|------|
| **Cursor** | Claude in your editor | cursor.sh |
| **Claude.ai** | Web interface | claude.ai |
| **Claude API** | Direct API access (Project 04) | console.anthropic.com |

### Vercel Integrations

| Integration | Purpose |
|------------|---------|
| **GitHub → Vercel** | Auto-deploy on push to main |
| **Vercel CLI** | Deploy from terminal |
| **Vercel Analytics** | Usage analytics (free tier) |

### Supabase Integrations

| Integration | Purpose |
|------------|---------|
| **Supabase JS Client** | `@supabase/supabase-js` |
| **Supabase Auth** | User authentication |
| **Supabase Realtime** | Live data updates |

---

## Recommended Chrome DevTools Panels

For the workshop, participants should be comfortable with:

- **Elements** — Inspect and edit HTML/CSS live
- **Console** — View JavaScript errors and log messages
- **Network** — Monitor API calls and responses
- **Lighthouse** — Run performance/accessibility audits

**Keyboard shortcuts:**
- `F12` or `Cmd+Option+I` — Open DevTools
- `Cmd+Shift+C` — Inspect element mode
- `Cmd+Shift+J` — Jump to Console

---

*Plugin suggestions? Open an issue or PR. See [CONTRIBUTING.md](../../CONTRIBUTING.md).*
