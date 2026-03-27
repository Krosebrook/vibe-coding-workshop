# Cursor Setup Guide

> How to download, install, and use Cursor for the Vibe Coding Workshop. Written for complete beginners.

---

## What Is Cursor?

Cursor is a code editor — the app where you write and edit code — with AI built directly into it.

Think of it like Microsoft Word, but for code. Except it has an AI assistant that understands your code, writes new code when you describe what you want, and explains things in plain English when you're confused.

You'll spend most of workshop day inside Cursor.

---

## Download and Install

### Mac

1. Go to [cursor.com](https://cursor.com)
2. Click **Download for Mac**
3. Open the `.dmg` file that downloads
4. Drag the **Cursor** icon to your **Applications** folder
5. Open your Applications folder and double-click Cursor
6. If you see "Cursor can't be opened because it's from an unidentified developer," go to **System Settings → Privacy & Security → Open Anyway**

```
┌─────────────────────────────────────────────┐
│  cursor.com                                  │
│                                              │
│  ┌──────────────────────────────────────┐   │
│  │  [ Download for Mac ]                │   │
│  └──────────────────────────────────────┘   │
│                                              │
└─────────────────────────────────────────────┘
```

### Windows

1. Go to [cursor.com](https://cursor.com)
2. Click **Download for Windows**
3. Run the `.exe` installer that downloads
4. Follow the installation wizard (click Next → Next → Install)
5. Cursor will open automatically when installation finishes

---

## First-Time Setup

When Cursor opens for the first time, it will walk you through a setup wizard.

### Step 1: Sign In or Create Account

- Click **Sign Up**
- Use your email or sign in with Google or GitHub
- Verify your email address

### Step 2: Import Settings (skip this)

If it asks whether to import settings from VS Code or another editor — click **Skip** unless you're already a VS Code user.

### Step 3: Choose a Theme

Pick whatever looks good to you. **Dark** themes are easier on the eyes during a full day.

### Step 4: Connect to Claude (Cursor's AI)

Cursor has its own AI built in. On the free plan:
- You get access to Claude through Cursor's interface
- No separate Claude API key needed for workshop projects 01–03
- For Project 04 (AI Chat app), you'll set up a direct Anthropic API key separately

---

## Key Features You'll Use Today

### Cmd+K / Ctrl+K — Inline Edit

Press **Cmd+K** (Mac) or **Ctrl+K** (Windows) while your cursor is in a file to edit code inline.

Use it for: small changes, style tweaks, fixing one specific thing.

```
[You select a line of code]
Press Cmd+K
Type: "Make this button purple with white text"
Press Enter
[Code changes inline]
```

### Cmd+L / Ctrl+L — Chat

Press **Cmd+L** (Mac) or **Ctrl+L** (Windows) to open the chat panel on the right side.

Use it for: asking questions, understanding what code does, getting explanations.

```
┌─────────────────┬─────────────────────────────┐
│  Your Code      │  Chat Panel                 │
│                 │  ┌─────────────────────────┐│
│  index.html     │  │ You: What does this     ││
│                 │  │ addEventListener do?    ││
│                 │  │                         ││
│                 │  │ Cursor: It listens for  ││
│                 │  │ a "click" event on the  ││
│                 │  │ button...               ││
│                 │  └─────────────────────────┘│
└─────────────────┴─────────────────────────────┘
```

### Cmd+I / Ctrl+I — Composer (the main one for today)

Press **Cmd+I** (Mac) or **Ctrl+I** (Windows) to open the Composer panel.

This is your primary tool. The Composer lets you describe what you want in plain English and generates or edits entire files.

Use it for: creating new features, building from scratch, major changes.

```
┌─────────────────────────────────────────────────────┐
│  Composer                                            │
│  ┌───────────────────────────────────────────────┐  │
│  │ Create a nav bar with three links: Home,      │  │
│  │ About, and Contact. Dark background #111111.  │  │
│  │ Sticky to the top of the page.                │  │
│  └───────────────────────────────────────────────┘  │
│  [ Submit ]                                          │
└─────────────────────────────────────────────────────┘
```

---

## The `.cursorrules` File

A `.cursorrules` file is a text file in your project folder that tells Cursor how you want it to behave for this specific project.

Think of it as a standing instruction — "whenever you write code for this project, remember these rules."

**Create a `.cursorrules` file in your project:**

```bash
# In Cursor's terminal (Ctrl+` to open):
touch .cursorrules
```

**Workshop project `.cursorrules` template:**

```
# Vibe Coding Workshop Project Rules

## Tech stack
- Vanilla HTML, CSS, JavaScript only
- No frameworks (no React, Vue, Angular, Bootstrap, Tailwind)
- No build tools (no npm, webpack, vite)
- All styles in a single <style> block in the HTML <head>
- All scripts in a single <script> block before </body>

## Design system
- Background: #0a0a0a
- Surface: #111111
- Text: #e8e8e8
- Accent: #7c3aed (purple)
- Font: Inter, system-ui, sans-serif

## Output format
- Single HTML file unless told otherwise
- Mobile-responsive by default
- No external CDN links unless specifically requested

## When I ask for changes
- Keep everything else the same
- Don't add features I didn't ask for
- Don't change the color scheme unless asked
```

Once this file is in your project, Cursor will follow these rules automatically on every prompt.

---

## Common First-Day Issues

### "Cursor won't open" (Mac)

Go to **System Settings → Privacy & Security** and look for a message about Cursor being blocked. Click **Open Anyway**.

### "I can't see my file preview"

To preview an HTML file in the browser:
1. Right-click the `index.html` file in the file explorer (left sidebar)
2. Select **Copy Path**
3. Paste it into your browser's address bar

Or install the **Live Preview** extension:
1. Click the Extensions icon in the left sidebar (4 squares)
2. Search "Live Preview"
3. Install the one by Microsoft
4. Right-click your HTML file → "Open with Live Preview"

### "Cursor is asking me to subscribe / upgrade"

The free plan is fine for the workshop. If you hit a rate limit on Cursor's built-in AI, you can paste your code into Claude at claude.ai directly and copy the response back.

### "I accidentally deleted my code"

Press **Cmd+Z** (Mac) or **Ctrl+Z** (Windows) to undo. You can undo many steps.

If that doesn't work: check the Timeline panel (View → Timeline) to restore an earlier version.

### "The AI generated something I don't want"

At the bottom of the Composer output, click **Reject** (or press Escape) to discard the changes. Your code stays as it was.

---

## Opening Your Project on GitHub

When you accept a GitHub Classroom assignment, you get a repository URL. Here's how to open it in Cursor:

1. Copy the repository URL from GitHub
2. In Cursor: **File → New Window**
3. Click **Clone a Repository**
4. Paste the URL
5. Choose where to save it on your computer
6. Click **Open** when it finishes cloning

---

*See also: `claude-setup.md`, `docs/phase2/prompting-playbook.md` (Cmd+I prompt patterns)*
