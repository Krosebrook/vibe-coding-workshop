# Claude Setup Guide

> How to create a Claude account, choose a plan, and use it effectively in the workshop.

---

## What Is Claude?

Claude is an AI assistant made by Anthropic. You talk to it in plain English, and it responds with text, code, explanations — whatever you need.

In the workshop, you'll use Claude to:
- Write code for your projects based on your descriptions
- Explain what code does when you're confused
- Debug errors by describing what went wrong
- Iterate on your designs by refining prompts

Claude is the core AI tool in the workshop. Getting familiar with it before the day makes a huge difference.

---

## Step 1: Create a Claude Account

1. Go to [claude.ai](https://claude.ai)
2. Click **Sign Up**
3. Enter your email address and create a password
   — or sign in with Google
4. Verify your email address
5. You're in

---

## Step 2: Choose a Plan

| Plan | Cost | What You Get | Good For |
|------|------|-------------|---------|
| **Free** | $0 | Access to Claude Sonnet, limited messages per day | The workshop — free tier is sufficient |
| **Pro** | $20/month | More messages, Claude Opus access, priority | Heavy daily use, no rate limits |

**For the workshop: the free plan works fine.**

If you hit a rate limit during the workshop (Claude stops responding and shows a message about limits), you have two options:
1. Wait a few minutes and try again
2. Use Cursor's built-in AI for a few prompts while Claude resets

You do not need to pay for Claude Pro to complete the workshop.

---

## Step 3: Your First Conversation

Open Claude and try this prompt before the workshop:

```
I'm learning to build web apps using HTML and JavaScript.
I've never coded before. I'm going to a workshop where I'll build 4 projects in one day.

Introduce yourself and tell me one thing about building web apps that would surprise a beginner.
```

You should get a friendly, detailed response. That's Claude. That's your coding partner for the day.

---

## Step 4: Tips for Getting Good Responses

### Be specific
The more context you give, the better the output. Instead of "make a button," say: "Create a purple button (#7c3aed) with white text that says 'Get Started'. Rounded corners, 16px padding on the sides, 10px on top and bottom."

### Use the prompting patterns
See `docs/phase2/prompting-playbook.md` for the four patterns you'll use all day:
- DESCRIBE-FIRST (starting something new)
- ERROR-DEBUG (fixing a broken thing)
- REFINE (improving what you have)
- ARCHITECTURE (planning before building)

### Don't restart — refine
If Claude gives you something close but not quite right, follow up: "That's close. Change X to Y. Keep everything else the same."

### Paste your code
When asking Claude to fix a bug, always paste the relevant code. Claude can't see your screen — it only knows what you tell it.

---

## Step 5: Claude API Key Setup (for Project 04)

Project 04 (AI Chat Assistant) requires a Claude API key so your app can call Claude directly. This is different from your claude.ai account.

**What the API key is:** A secret password that lets your app make requests to Claude programmatically. You'll store it securely in Vercel — never in your code.

**How to get one:**

1. Go to [console.anthropic.com](https://console.anthropic.com)
2. Sign in with your Claude account (same email)
3. Click **API Keys** in the left sidebar
4. Click **Create Key**
5. Name it: `vibe-coding-workshop`
6. Copy the key — it starts with `sk-ant-...`
7. **Save it somewhere safe.** You can only see it once. If you lose it, you'll need to create a new one.

**Important:** Never put your API key in your code. Not in your HTML file, not in a JavaScript file, not anywhere. Paste it directly into Vercel's environment variables section. The instructor will walk through this during Project 04.

**Free API credits:** New Anthropic accounts get $5 in free credits. Project 04 uses a tiny fraction of that — you will not run out during the workshop.

---

## Frequently Asked Questions

### "Is Claude the same as ChatGPT?"

They're different products from different companies (Anthropic vs. OpenAI), but they do similar things. Claude is considered particularly strong at code and longer conversations. Either works for vibe coding — the workshop uses Claude because it integrates well with Cursor and the workflow we teach.

### "Can I use ChatGPT instead?"

Yes, if you already have a ChatGPT account and are comfortable with it. The prompting patterns are the same. The workshop references Claude, but the skills transfer.

### "What if Claude gives me wrong code?"

That happens. It's a feature, not a bug — learning to identify and fix incorrect output is part of the skill you're building. Use the ERROR-DEBUG pattern: paste the error back to Claude and ask it to fix it.

### "Do I need to understand the code Claude writes?"

No — not to ship it. Understanding comes over time, through iteration. Today, focus on getting things to work and deployed. Understanding deepens with every project you build after.

---

*See also: `cursor-setup.md`, `vercel-setup.md` (for adding your API key to Vercel), `docs/phase2/prompting-playbook.md`*
