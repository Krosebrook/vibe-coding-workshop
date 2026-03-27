# Setup Guide

> Get the Vibe Coding Workshop site running locally in under 5 minutes.

---

## Prerequisites

| Requirement | Version | Notes |
|-------------|---------|-------|
| Web browser | Any modern browser | Chrome or Firefox recommended |
| Git | Any recent version | For cloning |
| (Optional) Node.js | 18+ | Only needed if you want a local dev server |

No build tools, no package manager, no compilation. This is a static HTML file.

---

## Quick Start (30 seconds)

```bash
# 1. Clone the repository
git clone https://github.com/Krosebrook/vibe-coding-workshop.git

# 2. Navigate to the directory
cd vibe-coding-workshop

# 3. Open the site
open index.html        # macOS
start index.html       # Windows
xdg-open index.html    # Linux
```

That's it. The site opens in your browser.

---

## Local Dev Server (Optional)

If you want a proper dev server with live reload:

### Option A: Node.js `serve`

```bash
# Install serve globally (one-time)
npm install -g serve

# Start the server
serve .

# Site available at: http://localhost:3000
```

### Option B: Python (usually pre-installed)

```bash
# Python 3
python3 -m http.server 8080

# Site available at: http://localhost:8080
```

### Option C: VS Code Live Server Extension

1. Install the [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) extension
2. Right-click `index.html` in the VS Code explorer
3. Select "Open with Live Server"
4. Site opens at `http://127.0.0.1:5500`

---

## Project Structure

```
vibe-coding-workshop/
├── index.html          ← The entire website (HTML + CSS)
├── README.md           ← Project overview
├── CLAUDE.md           ← Claude AI context file
├── CONTRIBUTING.md     ← How to contribute
├── CODE_OF_CONDUCT.md  ← Community standards
├── SECURITY.md         ← Security policy
├── PRIVACY.md          ← Privacy policy
├── ROADMAP.md          ← Feature roadmap
├── SETUP.md            ← This file
└── docs/               ← Documentation suite
    ├── memory.md
    ├── gemini.md
    ├── agents.md
    ├── skills/
    ├── plugins/
    ├── repo-agents/
    ├── copilot-skills/
    ├── schemas/
    ├── personas/
    ├── templates/
    ├── guidebooks/
    ├── playbooks/
    └── presentations/
```

---

## Making Changes

### Editing the Site

The entire site is in `index.html`. CSS is inlined in the `<style>` block in `<head>`. No compilation needed.

```bash
# 1. Edit index.html with your preferred editor
code index.html        # VS Code
nano index.html        # Terminal

# 2. Refresh your browser to see changes
# (Live Server does this automatically)
```

### Design System

All colors and design tokens are CSS custom properties at the top of the `<style>` block:

```css
:root {
  --bg: #0a0a0a;
  --surface: #111111;
  --border: #222222;
  --text: #e8e8e8;
  --muted: #888888;
  --accent: #7c3aed;
  --accent-light: #a78bfa;
  --green: #10b981;
}
```

Change these to update the entire site's color palette.

---

## Deployment

### GitHub Pages (Current Setup)

The site deploys automatically from the `main` branch.

To deploy manually:
1. Commit and push changes to `main`
2. GitHub Actions (if configured) handles deployment
3. Or: Repository Settings → Pages → Source: main branch → root folder

### Netlify

```bash
# Install Netlify CLI
npm install -g netlify-cli

# Deploy (one-time setup)
netlify init

# Deploy
netlify deploy --prod
```

### Vercel

```bash
# Install Vercel CLI
npm install -g vercel

# Deploy
vercel --prod
```

### Any Static Host

Upload `index.html` (and any other static assets) to any static hosting service:
- AWS S3 + CloudFront
- Cloudflare Pages
- Azure Static Web Apps
- Firebase Hosting
- Surge.sh (`surge . yourdomain.com`)

---

## Workshop Participant Setup

If you're attending the workshop, here's what to prepare **before the day**:

### Accounts to Create (Free)

- [ ] [GitHub](https://github.com/signup) — code hosting
- [ ] [Cursor](https://cursor.sh) — AI code editor (free tier)
- [ ] [Claude](https://claude.ai) — AI assistant (free tier)
- [ ] [Vercel](https://vercel.com/signup) — deployment (free tier)
- [ ] [Supabase](https://supabase.com) — database (free tier, used in Project 04)

### Software to Install

- [ ] [Cursor](https://cursor.sh/download) — AI code editor (replaces VS Code for the day)
- [ ] Chrome or Firefox (latest version)
- [ ] Git — usually pre-installed; check with `git --version`

### Verify Your Setup

Run this to confirm Git is installed:
```bash
git --version
# Should output something like: git version 2.42.0
```

---

## Troubleshooting

### "The page looks broken"
- Make sure you're opening `index.html` directly, not a different file
- Try a hard refresh: `Ctrl+Shift+R` (Win/Linux) or `Cmd+Shift+R` (Mac)
- Clear browser cache

### "The font looks different"
- The site uses system fonts. The exact rendering depends on your OS and installed fonts. This is expected behavior.

### "I can't edit the file"
- Check file permissions: `ls -la index.html`
- Make sure you cloned (not downloaded) the repo

### Need Help?

- Open a [GitHub Issue](https://github.com/Krosebrook/vibe-coding-workshop/issues)
- Email [hello@vibecodingworkshop.com](mailto:hello@vibecodingworkshop.com)

---

*Setup taking longer than 5 minutes? Let us know — we'll fix the docs.*
