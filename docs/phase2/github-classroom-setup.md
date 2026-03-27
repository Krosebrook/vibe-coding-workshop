# GitHub Classroom Setup Guide

> How to set up GitHub Classroom for the Vibe Coding Workshop — for instructors who may not be deeply technical.

---

## What Is GitHub Classroom?

GitHub Classroom is a free tool that lets you create coding assignments on GitHub. Each participant gets their own private copy of a starter repository when they accept an assignment link.

Think of it like Google Classroom, but for code.

**Why use it for this workshop:**
- Each participant has their own repository for all 4 projects
- You can see everyone's code in one place
- Vercel can deploy directly from GitHub (which is how deployment works in the workshop)
- Participants leave the day with a real GitHub portfolio

**You need:**
- A free GitHub account (github.com)
- A GitHub organization (free for educators — set up below)

---

## Step 1: Create a GitHub Organization

GitHub Classroom requires an organization — not just a personal account.

1. Go to [github.com/organizations/new](https://github.com/organizations/new)
2. Choose **Free plan**
3. Organization name: `vibe-coding-workshop` (or `vcw-[year]` for a cohort-specific org)
4. Contact email: your email
5. "This account belongs to: My personal account"
6. Click **Next** → skip adding members for now → **Complete setup**

---

## Step 2: Apply for the GitHub Education Discount (Optional but Recommended)

As an instructor at an educational institution, you can get free GitHub Team features.

1. Go to [education.github.com](https://education.github.com)
2. Click **Get benefits**
3. Select "Teacher"
4. Verify your school email (College of Lake County)
5. Approval takes 1–5 business days

This is optional — the free plan works fine for the workshop.

---

## Step 3: Create Your Classroom

1. Go to [classroom.github.com](https://classroom.github.com)
2. Click **New classroom**
3. Select your organization (`vibe-coding-workshop`)
4. Name your classroom: `Vibe Coding Workshop — Summer 2026`
5. Click **Create classroom**

---

## Step 4: Create the 4 Project Template Repositories

Before creating assignments, you need a starter repository for each project. Participants' repos will be created from these templates.

### How to Create a Template Repository

For each project:

1. Go to `github.com/[your-org]`
2. Click **New repository**
3. Name it: `template-project-01` (use this exact naming pattern)
4. Set it to **Public**
5. Check **Add a README file**
6. Create the repo, then add your starter files (see content below)
7. Go to **Settings** → scroll down to "Template repository" → check the box ✅

---

### Template Repository Contents

#### `template-project-01` — Personal Landing Page

**Files to include:**
```
README.md       ← Instructions for the project
index.html      ← Starter HTML (minimal boilerplate, dark theme variables)
```

**README.md content:**
```markdown
# Project 01 — Personal Landing Page

Build your personal landing page using AI tools.

## What to build
A single-page personal site with:
- Your name and a short bio
- Links to your social profiles
- Clean, professional design

## How to build it
1. Open this repo in Cursor
2. Use the prompting playbook to describe what you want
3. Iterate until you love it
4. Deploy to Vercel

## Checklist
- [ ] Hero section with your name
- [ ] Bio section
- [ ] Links section
- [ ] Mobile-responsive
- [ ] Deployed to Vercel (add your URL here)

**My live URL:** [add yours here]
```

**index.html starter:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Landing Page</title>
  <style>
    :root {
      --bg: #0a0a0a;
      --surface: #111111;
      --text: #e8e8e8;
      --muted: #888888;
      --accent: #7c3aed;
    }
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body {
      background: var(--bg);
      color: var(--text);
      font-family: Inter, system-ui, sans-serif;
      min-height: 100vh;
    }
  </style>
</head>
<body>
  <!-- Your content goes here -->
  <h1>Hello, world</h1>
</body>
</html>
```

---

#### `template-project-02` — Mood Tracker

**Files to include:**
```
README.md
index.html    ← Starter with localStorage helpers commented in
```

**README.md:** Same format as Project 01, adapted for mood tracker requirements.

---

#### `template-project-03` — Recipe Finder

**Files to include:**
```
README.md
index.html
```

**README.md should include:**
- The TheMealDB API endpoint: `https://www.themealdb.com/api/json/v1/1/filter.php?i={ingredient}`
- A link to the docs: `https://www.themealdb.com/api.php`

---

#### `template-project-04` — AI Chat Assistant

**Files to include:**
```
README.md
index.html       ← Frontend chat UI starter
api/
  chat.js        ← Vercel serverless function starter
vercel.json      ← Vercel configuration
package.json     ← Minimal package.json for Vercel functions
```

**vercel.json:**
```json
{
  "functions": {
    "api/*.js": {
      "runtime": "nodejs18.x"
    }
  }
}
```

**api/chat.js starter:**
```javascript
// This serverless function receives a message from the frontend
// and calls the Claude API. The API key is stored in Vercel's
// environment variables — never in the code.

export default async function handler(req, res) {
  if (req.method !== 'POST') {
    return res.status(405).json({ error: 'Method not allowed' });
  }

  const { message } = req.body;

  // TODO: Add Claude API call here using process.env.ANTHROPIC_API_KEY
  // See: https://docs.anthropic.com/en/api/getting-started

  res.status(200).json({ response: 'Hello from the API!' });
}
```

---

## Step 5: Create Assignments in GitHub Classroom

For each project, create one assignment.

1. In your classroom, click **New assignment**
2. Fill in:

| Field | Value |
|-------|-------|
| Assignment title | `Project 01 — Personal Landing Page` |
| Assignment type | Individual |
| Deadline | Leave blank (workshop day is self-paced) |
| Starter code | Select `template-project-01` |
| Repository visibility | **Private** (only you and the participant can see it) |
| Enable feedback pull requests | Yes (optional — lets you leave inline code comments) |

3. Click **Create assignment**
4. Copy the **invitation link** — you'll share this with participants

Repeat for all 4 projects.

---

## Step 6: Share Assignment Links with Participants

You'll share all 4 links during the workshop setup.

**Option A: Slide**
Put all 4 links on a single slide with QR codes. Participants scan each one.

**Option B: Google Doc / Notion page**
Create a page with all 4 links. Share the page URL in the workshop Discord channel.

**Option C: Directly in the Discord channel**
Post all 4 links in the `#workshop-day` channel at 9 AM.

**What happens when a participant clicks a link:**
1. They're asked to log in to GitHub (or create an account)
2. A new private repository is created in your org: `project-01-[their-github-username]`
3. It's pre-filled with the starter code from your template
4. They clone it in Cursor and start building

---

## Step 7: Reviewing Participant Work

During and after the workshop, you can review everyone's code.

**To see all submissions:**
1. Go to classroom.github.com → your classroom
2. Click on an assignment
3. You'll see a list of all accepted assignments with links to each repo
4. Click any participant's row to open their repository

**What to look for:**
- Did they commit code? (check the commit count)
- Did they add their live URL to the README?
- Any interesting approaches worth highlighting?

**Leaving feedback (optional):**
If you enabled feedback pull requests, GitHub Classroom automatically creates a PR in each repo. You can leave comments on specific lines of code there.

---

## Troubleshooting Common Issues

### "I clicked the link but it says 'Not found'"
The link may have expired or been copied incorrectly. Share the link again from GitHub Classroom.

### "I can't push to my repository"
They haven't configured Git credentials in Cursor. Solution:
1. Open Cursor's terminal (Ctrl+`)
2. Run: `git config --global user.email "you@example.com"`
3. Run: `git config --global user.name "Your Name"`
4. Try pushing again; if prompted, sign in via GitHub

### "My repo was created but it's empty"
The template may not have been set up correctly. Quick fix: have them manually create the files from the cheat sheet content, or fork the template repo directly.

### "I don't have a GitHub account"
Have them create one at github.com right now. It takes 2 minutes. Email + username + password.

### "My Vercel deployment failed"
Common causes:
1. **Project 04:** Missing `vercel.json` or incorrect serverless function format
2. **All projects:** Build command set to something that doesn't exist (set build command to empty for pure HTML projects)
3. **All projects:** Wrong root directory (should be `/`)

---

## After the Workshop

- Keep the classroom active for at least 3 months
- Consider making participant repos public after the workshop (ask participants first)
- Add the best projects to the workshop showcase (with consent)
- Archive the classroom when the cohort is done: Classroom settings → Archive

---

*See also: `setup-guides/vercel-setup.md` (connecting GitHub to Vercel), `docs/playbooks/README.md` PB01 (Workshop Day Playbook)*
