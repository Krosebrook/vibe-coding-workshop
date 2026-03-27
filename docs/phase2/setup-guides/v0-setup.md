# v0 Setup Guide

> How to use v0 by Vercel to generate UI components from text — and bring them into your project.

---

## What Is v0?

v0 is a tool by Vercel that generates user interface components from text descriptions. You describe what you want — "a dark nav bar with three links and a logo on the left" — and v0 generates the HTML and CSS for it.

Think of it as a specialized AI for visual design. Where Claude excels at logic and functionality, v0 excels at producing polished, production-quality UI code quickly.

**When to use v0 in the workshop:**
- Project 01 (Landing Page): Generate your hero section, nav bar, or cards
- Any project: When you want a specific UI component and want it to look great fast
- Any time you feel like spending more time on design than the project build allows

---

## Step 1: Create a v0 Account

1. Go to [v0.dev](https://v0.dev)
2. Click **Sign Up**
3. **Recommended: Sign up with GitHub** — this links your accounts and makes future workflows smoother
4. Authorize v0 to access your GitHub account
5. You're in

---

## Step 2: Your First UI Generation

When you land on v0, you'll see a text prompt area. Here's how to use it:

1. Type a description of the UI you want
2. Press Enter or click the generate button
3. v0 shows you a visual preview + the code
4. Iterate with follow-up prompts if needed
5. Export the code

**Example prompt for Project 01:**

```
A personal landing page hero section with:
- A dark background (#0a0a0a)
- My name "Alex Chen" in large text (48px+)
- Subtitle: "Designer & Builder"
- Two buttons: "View My Work" (purple, #7c3aed) and "Get In Touch" (outlined)
- Clean, modern, minimal
- No images — text and color only
```

v0 will generate multiple variations. Pick the one you like, then click to see the code.

---

## Step 3: Understand the Output

v0 generates code in a few possible formats:
- **Plain HTML/CSS** — paste directly into your project
- **React components** — only useful if your project uses React (the workshop uses vanilla HTML, so you may need to ask it to use plain HTML)

**Important:** Always ask v0 for vanilla HTML when it gives you React:

```
Regenerate this as plain HTML and CSS. No React, no JSX, no frameworks.
Use a single <div> with inline styles or a <style> block.
```

---

## Step 4: Export Code to Cursor

Once you have output you like:

1. In v0, click the **Code** tab (or similar) to see the full code
2. Click **Copy** to copy it all
3. In Cursor, open or create your `index.html`
4. Position your cursor where you want to paste the code
5. Press **Cmd+V** / **Ctrl+V** to paste
6. Preview it in the browser

You may need to adjust colors or fonts to match your project's design system. Use Cursor's Composer to make those adjustments:

```
I pasted a component from v0. Adjust the colors to match my design system:
Background: #0a0a0a, Text: #e8e8e8, Accent: #7c3aed.
Keep the structure the same.
```

---

## v0 Tips

### Use it for the parts you find tedious
v0 shines at repetitive UI work: nav bars, card grids, footer sections, form layouts. Spend your prompting energy on functionality; use v0 for visuals.

### Ask for variations
After your first generation, you can ask: "Show me 3 variations of this layout." v0 will give you options side by side.

### Keep your design system consistent
Always tell v0 your colors: `background #0a0a0a, text #e8e8e8, accent #7c3aed`. Consistent language across all your prompts keeps your project looking unified.

### Don't over-rely on it
v0 is a starting point, not a final product. Always bring the code into Cursor and refine it with Claude. v0 → Cursor → Claude is the workflow.

---

## Limitations

| Limitation | Workaround |
|-----------|-----------|
| May generate React/JSX by default | Ask explicitly for "plain HTML and CSS" |
| Doesn't know your existing project's code | Always paste the context you need it to match |
| Free tier has generation limits | Use Claude as a backup for UI generation |
| No direct GitHub integration | Copy-paste the code into Cursor |

---

## v0 vs. Claude for UI

Both can generate UI. Here's when to use which:

| Use v0 when... | Use Claude when... |
|---------------|-------------------|
| You want a visual preview | You want to edit existing code |
| Starting a new layout from scratch | Fixing a bug in your UI |
| You want multiple variations quickly | You need the AI to understand your context |
| Design is the priority | Functionality is the priority |

---

*See also: `cursor-setup.md` (where to paste v0 output), `claude-setup.md`, `docs/phase2/prompting-playbook.md`*
