# Top 25 Guidebooks

> In-depth guides covering every aspect of vibe coding, AI-assisted development, and workshop operations.

---

## Guidebook Index

| # | Title | Audience | Pages (est.) |
|---|-------|----------|-------------|
| G01 | [The Vibe Coding Handbook](#g01---the-vibe-coding-handbook) | All learners | 40 |
| G02 | [Prompt Engineering for Builders](#g02---prompt-engineering-for-builders) | All learners | 30 |
| G03 | [Claude for Beginners](#g03---claude-for-beginners) | Beginners | 25 |
| G04 | [Cursor: Your AI Code Editor](#g04---cursor-your-ai-code-editor) | Beginners | 20 |
| G05 | [HTML & CSS Fundamentals for Vibecoder](#g05---html--css-fundamentals-for-vibecoder) | Beginners | 35 |
| G06 | [JavaScript Survival Guide](#g06---javascript-survival-guide) | Intermediate | 30 |
| G07 | [Working with APIs](#g07---working-with-apis) | Intermediate | 25 |
| G08 | [Deploying with Vercel](#g08---deploying-with-vercel) | All learners | 15 |
| G09 | [Supabase for Non-Technical Founders](#g09---supabase-for-non-technical-founders) | Intermediate | 20 |
| G10 | [v0 by Vercel: UI Generation Guide](#g10---v0-by-vercel-ui-generation-guide) | All learners | 15 |
| G11 | [Git & GitHub for Beginners](#g11---git--github-for-beginners) | Beginners | 20 |
| G12 | [Accessibility in AI-Generated Code](#g12---accessibility-in-ai-generated-code) | All learners | 20 |
| G13 | [Building Mobile-Friendly Apps](#g13---building-mobile-friendly-apps) | All learners | 20 |
| G14 | [Security Basics for Beginners](#g14---security-basics-for-beginners) | All learners | 20 |
| G15 | [Debugging with AI](#g15---debugging-with-ai) | All learners | 15 |
| G16 | [From Idea to Deployed App: Full Workflow](#g16---from-idea-to-deployed-app-full-workflow) | All learners | 25 |
| G17 | [Building a SaaS with No-Code + AI](#g17---building-a-saas-with-no-code--ai) | Intermediate | 30 |
| G18 | [The Non-Technical Founder's Tech Stack](#g18---the-non-technical-founders-tech-stack) | Founders | 25 |
| G19 | [Working with Databases as a Beginner](#g19---working-with-databases-as-a-beginner) | Intermediate | 25 |
| G20 | [AI Ethics for Builders](#g20---ai-ethics-for-builders) | All learners | 15 |
| G21 | [Content and UX Copywriting for Apps](#g21---content-and-ux-copywriting-for-apps) | Designers/Founders | 20 |
| G22 | [Workshop Instructor Guide](#g22---workshop-instructor-guide) | Instructors | 30 |
| G23 | [Participant Pre-Workshop Guide](#g23---participant-pre-workshop-guide) | Participants | 10 |
| G24 | [Post-Workshop: Keep Building](#g24---post-workshop-keep-building) | Alumni | 20 |
| G25 | [Business Case for AI-Assisted Development](#g25---business-case-for-ai-assisted-development) | Managers/Founders | 15 |
| G26 | [Getting Started with Vibe Starter](#g26---getting-started-with-vibe-starter) | All learners | 10 |
| G27 | [How to Use the Prompt Library](#g27---how-to-use-the-prompt-library) | All learners | 10 |
| G28 | [AI Tool Comparison: Choosing Your Stack](#g28---ai-tool-comparison-choosing-your-stack) | All learners | 15 |
| G29 | [Hosting a Regional Vibe Coding Workshop](#g29---hosting-a-regional-vibe-coding-workshop) | Instructors | 20 |
| G30 | [The Vibe Code Jam: Participant Guide](#g30---the-vibe-code-jam-participant-guide) | Community | 10 |

---

## G01 — The Vibe Coding Handbook

**Audience:** All learners  
**Summary:** The complete guide to AI-assisted "vibe coding." What it is, why it works, and how to master it.

### Table of Contents
1. What Is Vibe Coding?
2. The History: From Traditional Coding to AI Collaboration
3. The Vibe Coding Mindset
4. Core Principles: Intent Over Syntax
5. The Prompt → Output → Refine Loop
6. Common Beginner Mistakes (and How to Avoid Them)
7. Choosing the Right AI Tool for Each Task
8. Working with Claude, Cursor, and v0
9. When AI Gets It Wrong: Understanding Hallucination
10. Building Complex Apps Step by Step
11. The Vibe Coder's Toolkit
12. Next Steps After Your First App

### Key Concepts
- **Intent over syntax:** Describe what you want, not how to build it
- **Progressive refinement:** Start rough, iterate to polished
- **AI as collaborator:** Not autocomplete, not a vending machine
- **Breaking the blocks:** What to do when AI keeps getting it wrong

---

## G02 — Prompt Engineering for Builders

**Audience:** All learners  
**Summary:** A practical guide to writing prompts that consistently produce good code and content.

### Table of Contents
1. Why Prompting Matters
2. The Anatomy of a Great Prompt
3. Context: Setting the Scene
4. Instruction: Being Specific About What You Want
5. Format: Telling AI How to Respond
6. Constraints: What Not To Do
7. Examples: Show, Don't Just Tell
8. Chain-of-Thought Prompting
9. Few-Shot Examples in Code Prompts
10. System Prompts for Chat Apps
11. Prompting for Documentation
12. Common Prompt Patterns (Library)
13. Debugging Bad Prompts

### Prompt Pattern Library
```
DESCRIBE-FIRST:
"I'm building [X]. It should [behavior]. 
The user will [interaction]. 
Style: [description]. Constraints: [list]."

ERROR-DEBUG:
"I got this error: [error]. Here is my code: [code]. 
What's wrong and how do I fix it? Explain like I'm a beginner."

REFINE:
"The [element] looks [problem]. 
Change it to be more [desired quality] by [specific change]."

ARCHITECTURE:
"I want to build [app]. 
What are the components I need? 
Don't write code yet — just describe the structure."
```

---

## G03 — Claude for Beginners

**Audience:** Beginners  
**Summary:** A hands-on guide to using Claude effectively, from first conversation to complex app building.

### Table of Contents
1. What Is Claude?
2. Getting Started at claude.ai
3. Your First Coding Conversation
4. Continuing a Conversation (Context Window)
5. When to Start a New Chat vs. Continue
6. Uploading Files and Images
7. Claude's Personality and How It Thinks
8. Getting Claude to Explain Its Code
9. Using Claude for Non-Code Tasks (Documentation, Emails, Ideas)
10. Claude API: What It Is and When You Need It
11. Claude in Cursor: The Best of Both Worlds
12. Claude's Limitations (And How to Work Around Them)

### Quick Reference
| What you want | How to ask Claude |
|---------------|------------------|
| Build something new | Describe it in detail with context |
| Fix an error | Paste error + code + "what's wrong?" |
| Understand code | "Explain this like I'm not a programmer" |
| Change something | "Change X to Y" with visual description |
| Better code | "How would you improve this?" |

---

## G04 — Cursor: Your AI Code Editor

**Audience:** Beginners  
**Summary:** Install, configure, and master Cursor — the AI-native code editor used in the workshop.

### Table of Contents
1. Installing Cursor
2. The Interface Overview (What's Different from VS Code)
3. Your First AI Edit: Cmd+K
4. The Chat Panel: Cmd+L
5. Composer: Multi-File Editing
6. Understanding the .cursorrules File
7. Connecting Your Own API Keys
8. Cursor + GitHub: Opening a Repo
9. Working with HTML Files in Cursor
10. Debugging with Cursor AI
11. Tips and Tricks for Faster Workflows
12. Privacy: What Cursor Sends to AI

### Essential Shortcuts
```
Cmd+K (Mac) / Ctrl+K (Win) — Inline AI edit
Cmd+L (Mac) / Ctrl+L (Win) — Open chat panel
Cmd+I (Mac) / Ctrl+I (Win) — Open Composer
Cmd+Shift+L — Add code to chat context
```

---

## G05 — HTML & CSS Fundamentals for Vibecoder

**Audience:** Beginners  
**Summary:** The minimum viable HTML and CSS knowledge you need to understand and modify AI-generated code.

### Table of Contents
1. What Is HTML? What Is CSS?
2. The Basic HTML Document Structure
3. Common HTML Tags You'll See and Modify
4. The Box Model (Why Things Don't Look Right)
5. CSS Properties You'll Use Most Often
6. Colors: Hex, RGB, and HSL
7. Layouts: Flexbox in Plain English
8. Layouts: CSS Grid in Plain English
9. Responsive Design: Media Queries
10. CSS Custom Properties (Variables)
11. Reading and Editing AI-Generated HTML/CSS
12. "I didn't break it, I improved it" — Iterating on AI Output

### Most Common CSS Properties
```css
/* Box */
margin, padding, border, border-radius
width, height, max-width

/* Text */
font-size, font-weight, color, line-height, text-align

/* Layout */
display (flex, grid, block, inline)
flex-direction, justify-content, align-items
grid-template-columns, gap

/* Visual */
background, box-shadow, opacity, overflow
```

---

## G06 — JavaScript Survival Guide

**Audience:** Intermediate  
**Summary:** The JavaScript you'll encounter in workshop Projects 02–04, explained clearly.

### Table of Contents
1. Why JavaScript Exists (And Why You Need It)
2. Variables: let, const, and var
3. Functions: Regular and Arrow
4. DOM Manipulation: Changing the Page
5. Events: Responding to User Actions
6. Arrays and Objects (Data Storage)
7. Async JavaScript: Fetch and Promises
8. localStorage: Saving Data in the Browser
9. JSON: The Data Language of the Web
10. Error Handling: try/catch
11. The Module Pattern (for Larger Apps)
12. Debugging JavaScript in the Browser

---

## G07 — Working with APIs

**Audience:** Intermediate  
**Summary:** A beginner-friendly guide to understanding, finding, and using APIs in your apps.

### Table of Contents
1. What Is an API? (The Restaurant Analogy)
2. REST APIs: The Standard Format
3. HTTP Methods: GET, POST, PUT, DELETE
4. API Keys: What They Are and How to Protect Them
5. Making API Calls with fetch()
6. Reading API Documentation
7. Free APIs Perfect for Projects
8. Handling Responses: Success and Error Cases
9. Loading States: Showing Users What's Happening
10. Rate Limits and How to Handle Them
11. Using Postman or Bruno to Test APIs
12. API Projects: Workshop Examples

### Top Free APIs for Beginners
| API | What It Provides | Key Required? |
|-----|-----------------|--------------|
| TheMealDB | Recipe search | No |
| Open-Meteo | Weather data | No |
| PokeAPI | Pokémon data | No |
| TheDogAPI | Dog breeds + photos | Free tier |
| Free Dictionary API | Word definitions | No |
| CoinGecko | Crypto prices | No |
| GitHub API | Repository data | No (public) |
| JokeAPI | Random jokes | No |

---

## G08 — Deploying with Vercel

**Audience:** All learners  
**Summary:** Deploy your first project to a real URL using Vercel. Step-by-step for beginners.

### Table of Contents
1. What Is Vercel?
2. Creating Your Free Account
3. Connecting GitHub to Vercel
4. Your First Deployment (3 clicks)
5. Understanding Your Vercel Dashboard
6. Custom Domains (Optional)
7. Environment Variables: Hiding API Keys
8. Automatic Deployments (Every Git Push)
9. Preview Deployments (Every PR)
10. When Deployment Fails: Common Errors
11. Vercel Analytics (Free Tier)
12. Alternatives: Netlify, GitHub Pages, Cloudflare Pages

---

## G09 — Supabase for Non-Technical Founders

**Audience:** Intermediate  
**Summary:** Add a database, authentication, and real-time features to your app without a backend developer.

### Table of Contents
1. What Is Supabase?
2. Creating Your Free Project
3. The Supabase Dashboard Overview
4. Tables: Creating Your First Database Table
5. The Supabase JavaScript Client
6. Reading Data (Select)
7. Writing Data (Insert, Update, Delete)
8. Row Level Security: Protecting Your Data
9. Authentication: Email + Social Login
10. Real-Time Subscriptions
11. Storage: Uploading Files and Images
12. When Supabase Is (and Isn't) the Right Choice

---

## G10 — v0 by Vercel: UI Generation Guide

**Audience:** All learners  
**Summary:** Use v0 to generate beautiful UI components with text descriptions.

### Table of Contents
1. What Is v0?
2. Your First UI Generation
3. Iterating with Text Prompts
4. Copying Components into Your Project
5. v0 + React vs. v0 + HTML/CSS
6. Best Practices for v0 Prompts
7. Combining v0 Output with Your Existing Code
8. Limitations of v0 and When to Use Claude Instead
9. Free Tier Limits and Paid Plans
10. v0 Community Components

---

## G11 — Git & GitHub for Beginners

**Audience:** Beginners  
**Summary:** Version control and code collaboration, explained without jargon.

### Table of Contents
1. Why You Need Git (Even If You Work Alone)
2. Installing Git
3. Your First Git Repository
4. The Git Workflow: Stage → Commit → Push
5. GitHub: The Social Network for Code
6. Creating and Cloning Repositories
7. Branches: Working Without Fear
8. Pull Requests: Getting Code Review
9. Working with GitHub Copilot in the Browser
10. Connecting Your Project to GitHub (In Cursor)
11. .gitignore: What Not to Track
12. Common Git Commands Reference

### Quick Reference
```bash
git init                    # Start tracking a folder
git add .                   # Stage all changes
git commit -m "message"     # Save a checkpoint
git push                    # Send to GitHub
git status                  # See what's changed
git log --oneline           # See commit history
git checkout -b feature     # Create a new branch
```

---

## G12 — Accessibility in AI-Generated Code

**Audience:** All learners  
**Summary:** Make sure your AI-generated apps work for everyone — including people with disabilities.

### Table of Contents
1. Why Accessibility Matters
2. WCAG: The Standard You're Aiming For
3. Semantic HTML: The Foundation
4. Color Contrast: Checking and Fixing
5. Keyboard Navigation: Can You Use Your App Without a Mouse?
6. Screen Readers: How They Work
7. ARIA: When to Use It (and When Not To)
8. Images and Alt Text
9. Forms: Labels, Error Messages, Focus
10. Testing with axe, WAVE, and Lighthouse
11. Prompting Claude to Generate Accessible Code
12. The Accessibility Audit Checklist

---

## G13 — Building Mobile-Friendly Apps

**Audience:** All learners  
**Summary:** Design and build apps that work great on phones — where most users are.

### Table of Contents
1. Mobile-First vs. Desktop-First Design
2. The Viewport Meta Tag (Never Forget This)
3. Responsive Units: rem, em, %, vw/vh
4. Media Queries: One Breakpoint Strategy
5. Flexbox for Mobile Layouts
6. Touch Targets: Making Buttons Big Enough
7. Typography on Mobile
8. Testing on Real Devices (and DevTools)
9. Performance on Mobile Networks
10. Progressive Web App Basics

---

## G14 — Security Basics for Beginners

**Audience:** All learners  
**Summary:** The most important security concepts every vibe coder needs to know.

### Table of Contents
1. Why Security Matters Even for Small Projects
2. Secrets and API Keys: Never Hardcode Them
3. Environment Variables: The Right Way
4. HTTPS: Always
5. Content Security Policy: The Basics
6. Input Validation: Trust No User Input
7. Cross-Site Scripting (XSS): What It Is and How to Prevent It
8. Authentication: When You Need It and Options
9. Rate Limiting for APIs
10. Dependency Security: Checking npm packages
11. Security Headers: A Simple Checklist
12. When to Ask a Security Professional

---

## G15 — Debugging with AI

**Audience:** All learners  
**Summary:** Turn errors from frustrating roadblocks into learning opportunities — with AI's help.

### Table of Contents
1. The Debugging Mindset
2. Reading Error Messages (They're Not Scary)
3. Console.log: Your Best Friend
4. Browser DevTools for HTML/CSS Bugs
5. Network Tab: Debugging API Calls
6. Pasting Errors into Claude: The Template
7. When AI Gives You the Wrong Fix
8. Rubber Duck Debugging (with AI as the Duck)
9. Common JavaScript Errors and Fixes
10. Common CSS Problems and Fixes
11. API Debugging Checklist
12. Building a Personal Bug Journal

---

## G16 — From Idea to Deployed App: Full Workflow

**Audience:** All learners  
**Summary:** The complete end-to-end process of going from "I have an idea" to "here's the URL."

### Table of Contents
1. Defining Your App (The One-Sentence Pitch)
2. Identifying Your Core Feature (MVP Thinking)
3. Drawing It Out (Even Rough Sketches Help)
4. Choosing Your Tools
5. Setting Up Your Development Environment
6. The First Prompt (Getting the Structure)
7. Iterating Until It Feels Right
8. Adding Features Incrementally
9. Testing Your App as a User Would
10. Pre-Launch Checklist
11. Deploying to a Real URL
12. Sharing Your Work and Getting Feedback

---

## G17 — Building a SaaS with No-Code + AI

**Audience:** Intermediate  
**Summary:** Build a subscription-based software product without writing backend code from scratch.

### Table of Contents
1. What Is SaaS and Why Build One?
2. Vibe Coding SaaS vs. Traditional Development
3. The Tech Stack: Frontend + Supabase + Stripe
4. Authentication with Supabase Auth
5. Stripe for Subscriptions (with Claude's Help)
6. User Dashboard Template
7. Gated Content: What Free vs. Paid Users See
8. Email Onboarding with Resend
9. Analytics and Monitoring
10. Launching on ProductHunt
11. Customer Support Tools
12. Scaling When You Hit Limits

---

## G18 — The Non-Technical Founder's Tech Stack

**Audience:** Founders  
**Summary:** The exact tools to use at each stage of building a startup — no CS degree required.

### Table of Contents
1. Pre-Validation (Idea Stage): No Code Needed
2. MVP Stage: The Lean Vibestack
3. Launch Stage: What to Add
4. Growth Stage: When to Hire
5. Tools by Category: Frontend, Backend, Auth, Payments, Email, Analytics
6. Vibe Coding vs. Traditional Dev vs. No-Code: When Each Makes Sense
7. Estimating Development Time with AI
8. Working with Contractors on AI-Built Code
9. Open Source vs. Hosted Services
10. Cost Comparison: DIY vs. SaaS Tools

---

## G19 — Working with Databases as a Beginner

**Audience:** Intermediate  
**Summary:** Understand databases well enough to build data-driven apps, without a database degree.

### Table of Contents
1. What Is a Database? (The Spreadsheet Analogy)
2. SQL vs. NoSQL: Which One?
3. Tables, Rows, and Columns
4. Basic SQL: SELECT, INSERT, UPDATE, DELETE
5. Relationships: Connecting Tables
6. Supabase: A Database You Can Actually Use
7. Using AI to Write SQL
8. When localStorage Is Enough
9. Data Modeling for Common App Types
10. Backups and Data Safety

---

## G20 — AI Ethics for Builders

**Audience:** All learners  
**Summary:** How to build AI-powered products responsibly — for users, society, and yourself.

### Table of Contents
1. Why Ethics Matters in AI Development
2. Bias in AI Outputs
3. Privacy: Handling User Data Responsibly
4. Transparency: Telling Users When AI Is Involved
5. Accessibility and Inclusion in AI Products
6. AI for Mental Health: Special Responsibilities
7. Avoiding Dark Patterns
8. Content Moderation in AI Chat Apps
9. The Environmental Cost of AI
10. Principles for Responsible AI Product Development

---

## G21 — Content and UX Copywriting for Apps

**Audience:** Designers/Founders  
**Summary:** Write better button labels, error messages, onboarding copy, and UI text for your apps.

### Table of Contents
1. Why UX Copy Matters as Much as Design
2. Button Labels: Action-First Language
3. Error Messages: What They Should Say
4. Empty States: When There's Nothing to Show
5. Onboarding: First Impressions
6. Confirmation Messages and Success States
7. Loading States: Keep Users Engaged
8. Form Copy: Labels, Placeholders, Help Text
9. Using Claude to Write Better UI Copy
10. Testing Copy with Real Users

---

## G22 — Workshop Instructor Guide

**Audience:** Instructors  
**Summary:** Everything you need to deliver a Vibe Coding Workshop successfully.

### Table of Contents
1. Workshop Philosophy
2. Room Setup and Equipment Checklist
3. Participant Pre-Work (Pre-Attendance Requirements)
4. Day-Of Schedule (Minute-by-Minute)
5. The Opening: Setting the Room's Energy
6. Teaching Project 01 (Step by Step)
7. Teaching Project 02 (Step by Step)
8. Lunch Break: Facilitated Discussion Topics
9. Teaching Project 03 (Step by Step)
10. Teaching Project 04 (Step by Step)
11. The Ship It Ceremony
12. Common Problems and Solutions
13. Post-Workshop: Follow-Up and Feedback
14. Adapting the Workshop for Different Audiences

---

## G23 — Participant Pre-Workshop Guide

**Audience:** Participants  
**Summary:** What to do before the workshop to get the most out of your day.

### Table of Contents
1. Welcome and What to Expect
2. Accounts to Create Before You Arrive
3. Software to Install
4. Your Idea: What to Think About Beforehand
5. What NOT to Do (Don't Watch Hours of Tutorials)
6. Day-Of Logistics
7. FAQ: Pre-Workshop Questions

---

## G24 — Post-Workshop: Keep Building

**Audience:** Alumni  
**Summary:** What to do after the workshop to keep the momentum and go deeper.

### Table of Contents
1. The First Week: Don't Let the Vibe Fade
2. Your First Solo Project: How to Choose
3. Resources for Going Deeper
4. Community: Where to Find Other Vibe Coders
5. When to Start Learning "Real" Code
6. Sharing Your Work: GitHub, X, LinkedIn
7. Freelancing and Monetizing Your Skills
8. Building a Portfolio That Gets Noticed
9. Recommended Next Steps by Goal
10. Stay in Touch

---

## G25 — Business Case for AI-Assisted Development

**Audience:** Managers/Founders  
**Summary:** How to make the case for vibe coding and AI-assisted development in your organization.

### Table of Contents
1. The ROI of AI-Assisted Development
2. Speed Comparison: Traditional vs. AI-Assisted
3. Quality Considerations
4. Risk Management
5. What Skills Teams Still Need
6. Building vs. Buying vs. AI-Building
7. Case Studies: Organizations Using Vibe Coding
8. Getting Stakeholder Buy-In
9. Training Your Team
10. Governance and Security Policies for AI Dev Tools

---

## G26 — Getting Started with Vibe Starter

**Audience:** All learners  
**Summary:** How to use the Vibe Starter CLI to scaffold new projects in seconds and hit the ground building.

### Table of Contents
1. What Is Vibe Starter?
2. Installing and Running (npx, no install needed)
3. Choosing the Right Template
4. Understanding the Generated Files
5. Customizing Your `.cursorrules`
6. Customizing Your `CLAUDE.md`
7. Deploying Immediately After Scaffolding
8. Advanced: Creating Custom Templates

### Key Concepts
- **Scaffolding:** Setting up the project structure before writing any features
- **Opinionated defaults:** Why having sensible defaults helps beginners move faster
- **`.cursorrules`:** How to tune AI behavior for your specific project

---

## G27 — How to Use the Prompt Library

**Audience:** All learners  
**Summary:** How to search, copy, use, and contribute prompts in the Vibe Coding Prompt Library.

### Table of Contents
1. What Is the Prompt Library?
2. How to Search and Filter
3. Understanding the Prompt Format
4. Replacing Variables in Prompts
5. Adapting Prompts for Your Context
6. Saving Your Favorite Prompts
7. Contributing a New Prompt
8. The Prompt Contribution Review Process

### Key Concepts
- **Prompt variables:** `{{VARIABLE_NAME}}` placeholders you replace with your own content
- **Category taxonomy:** How prompts are organized for fast browsing
- **Contribution flow:** How community-submitted prompts are reviewed and merged

---

## G28 — AI Tool Comparison: Choosing Your Stack

**Audience:** All learners  
**Summary:** How to evaluate and choose the right AI tools for your project — with honest comparisons from real-world vibe coding use.

### Table of Contents
1. Why Tool Choice Matters (and Why It Doesn't)
2. The Four Tool Categories: Editor, Model, UI Generator, Deploy
3. Cursor vs. Windsurf vs. Copilot
4. Claude vs. ChatGPT vs. Gemini
5. v0 vs. Bolt.new vs. Building from Scratch
6. Vercel vs. GitHub Pages vs. Netlify
7. The Recommended Workshop Stack
8. The Free-Tier Stack
9. When to Switch Tools
10. How to Evaluate New AI Tools as They Launch

### Key Concepts
- **Tool categories:** Why each role in the stack is distinct
- **Lock-in vs. flexibility:** When to commit to a tool and when to keep options open
- **The evaluation framework:** Five questions to ask about any new AI dev tool

---

## G29 — Hosting a Regional Vibe Coding Workshop

**Audience:** Instructors  
**Summary:** A complete guide for certified regional instructors running the workshop in their city.

### Table of Contents
1. Getting Certified: The Regional Instructor Path
2. Finding and Booking a Venue
3. Setting Up Registration and Marketing Locally
4. Pre-Workshop Logistics
5. Adapting Examples for Your Local Context
6. Day-Of Facilitation Tips
7. Managing the Room: Energy, Pace, Breakdowns
8. Post-Workshop Follow-Up
9. Building a Local Alumni Community
10. Reporting and Quality Standards

### Key Concepts
- **Local context:** How to make the workshop feel relevant to your city
- **Facilitation energy:** The difference between lecture and accompaniment
- **Alumni activation:** Turning one-day participants into an ongoing community

---

## G30 — The Vibe Code Jam: Participant Guide

**Audience:** Community  
**Summary:** Everything you need to know to participate in — and win — the annual Vibe Code Jam.

### Table of Contents
1. What Is the Code Jam?
2. How to Register
3. Choosing a Track (Solo, Team, First Timer, Remix)
4. The Theme Reveal: How to Interpret It
5. Building in 24 Hours: Time Management Tips
6. Getting Help: Discord Channels and Support
7. Submitting Your Project
8. The Showcase and Judging Process
9. After the Jam: Keep the Momentum

### Key Concepts
- **The 80% rule:** Ship something that works 80% of the way vs. perfecting 20% of a feature
- **Scope discipline:** How to pick an idea you can actually ship in 24 hours
- **Rubber duck prompting:** When you're stuck at 2 AM and no one's in the Discord

---

*These guidebooks are available as Markdown in this repository and will be published as PDFs for workshop participants.*
