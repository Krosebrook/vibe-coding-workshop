# Vercel Setup Guide

> How to deploy your projects to live URLs using Vercel.

---

## What Is Vercel?

Vercel is a platform that takes code you've written and puts it on the internet — automatically, for free, in about 60 seconds.

You push your code to GitHub. Vercel notices. Vercel deploys it. You get a live URL.

That's it. You don't need to understand servers, hosting, DNS, or any of that. Vercel handles all of it.

In the workshop, you'll use Vercel to deploy all 4 projects.

---

## Step 1: Create a Vercel Account

1. Go to [vercel.com](https://vercel.com)
2. Click **Sign Up**
3. **Choose "Continue with GitHub"** — this is the easiest path and connects your repositories automatically
4. Authorize Vercel to access your GitHub account
5. Complete the onboarding (skip the team setup — it's just you)

You're now set up. Vercel can see your GitHub repositories.

---

## Step 2: Deploy Your First Project from GitHub

When you're ready to deploy a project from the workshop:

1. In Vercel, click **Add New... → Project**
2. You'll see a list of your GitHub repositories
3. Find your project repository (e.g., `project-01-yourname`)
4. Click **Import**
5. On the configuration screen:
   - **Framework Preset:** Select "Other" (for plain HTML projects 01–03)
   - **Root Directory:** Leave as `/` unless told otherwise
   - **Build Command:** Leave empty for plain HTML projects
   - **Output Directory:** Leave empty
6. Click **Deploy**
7. Watch the build log (takes 15–60 seconds)
8. When complete, Vercel shows you a URL like `project-01-yourname.vercel.app`

That URL is live. Anyone in the world can visit it.

---

## Step 3: Re-deploying After Changes

When you update your code and push it to GitHub, Vercel automatically redeploys.

1. Make changes in Cursor
2. Commit and push to GitHub (Cursor has a built-in Git panel — the branch icon in the left sidebar)
3. Go to your Vercel project dashboard
4. Watch the automatic deployment trigger
5. New version is live in ~30 seconds

You don't need to do anything in Vercel — the push to GitHub triggers it automatically.

---

## Step 4: Environment Variables (for Project 04)

Project 04 (AI Chat Assistant) needs your Claude API key. You store it as an environment variable in Vercel — never in your code.

**What is an environment variable?**

It's a secret that your app can access at runtime, but that isn't stored in your code. Vercel keeps it encrypted. Your GitHub repository never contains it.

**How to add your Claude API key:**

1. Go to your Project 04 project in Vercel
2. Click **Settings** (in the top navigation)
3. Click **Environment Variables** in the left sidebar
4. Click **Add New**
5. Fill in:
   - **Key:** `ANTHROPIC_API_KEY`
   - **Value:** Your API key (starts with `sk-ant-...`)
   - **Environment:** Check all three boxes (Production, Preview, Development)
6. Click **Save**
7. Go back to **Deployments** and click **Redeploy** to apply the new variable

Your serverless function can now access the key with `process.env.ANTHROPIC_API_KEY`.

---

## Step 5: Custom Domain Setup (Optional)

If you want your project to live at your own domain (e.g., `yourname.dev` instead of `project-01-yourname.vercel.app`):

1. Buy a domain at Namecheap, Google Domains, or Cloudflare Domains (~$10–15/year)
2. In Vercel: Project → Settings → Domains → Add Domain
3. Enter your domain name
4. Vercel gives you DNS records to add at your registrar
5. Add the records at your registrar (usually takes a few minutes to propagate)

This is entirely optional. The `.vercel.app` URL works perfectly and is shareable.

---

## Troubleshooting Common Issues

### "Build failed"

1. Click on the failed deployment to see the build log
2. Look for the red error message
3. Common causes:
   - **Plain HTML project:** A build command was accidentally set. Go to Settings → General → Build & Output Settings → clear the build command field
   - **Project 04:** Missing `package.json` or `vercel.json` in your repository

### "My changes aren't showing up"

- Did you commit and push to GitHub? The Cursor Git panel (branch icon, left sidebar) needs to show 0 pending changes
- Did Vercel trigger a new deployment? Check the Deployments tab — there should be a new one in the last few minutes
- Try force-refreshing your browser: **Cmd+Shift+R** (Mac) or **Ctrl+Shift+R** (Windows)

### "My API key isn't working in production"

- Confirm the environment variable name is exactly `ANTHROPIC_API_KEY` (case-sensitive)
- After adding the variable, you must click **Redeploy** — existing deployments don't automatically pick up new env vars
- Check that the key is correct by copying it again from `console.anthropic.com`

### "I need to share the URL but it's the wrong project"

Each Vercel project has its own URL. Check that you're in the right project in the Vercel dashboard (dropdown at top left).

---

## Understanding the Vercel Dashboard

```
┌─────────────────────────────────────────────────────────┐
│  Vercel Dashboard                                        │
│                                                          │
│  Projects:                                               │
│  ┌────────────────────────┐  ┌────────────────────────┐ │
│  │ project-01-yourname    │  │ project-02-yourname    │ │
│  │ ✅ Deployed            │  │ ✅ Deployed            │ │
│  │ yourname.vercel.app    │  │ yourname-p2.vercel.app │ │
│  └────────────────────────┘  └────────────────────────┘ │
│  ┌────────────────────────┐  ┌────────────────────────┐ │
│  │ project-03-yourname    │  │ project-04-yourname    │ │
│  │ ✅ Deployed            │  │ 🔄 Building...         │ │
│  └────────────────────────┘  └────────────────────────┘ │
└─────────────────────────────────────────────────────────┘
```

Each project card shows:
- Project name
- Latest deployment status (✅ Ready, 🔄 Building, ❌ Error)
- The live URL

Click any project to see its deployment history, logs, settings, and environment variables.

---

*See also: `cursor-setup.md` (Git panel for pushing code), `claude-setup.md` (getting your API key), `github-classroom-setup.md`*
