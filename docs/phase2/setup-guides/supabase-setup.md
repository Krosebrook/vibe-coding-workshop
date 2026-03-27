# Supabase Setup Guide

> How to set up and use Supabase — a free database — for your workshop projects.

---

## What Is Supabase?

Supabase is a database you can use in your web apps without needing to understand databases.

Think of it like a Google Spreadsheet that your app can read from and write to automatically. You create a table (like a spreadsheet with columns), and your app can add rows, read rows, update rows — all through a simple URL.

Under the hood, it's a real PostgreSQL database. But the interface looks like a spreadsheet, the setup takes 10 minutes, and you don't need to know SQL to use it.

**When you'd use Supabase:**
- Your app needs to save data that persists (survives page refresh) and is accessible from anywhere
- You need multiple users to share the same data
- Local storage isn't enough (it only saves data in one browser on one device)

**When you DON'T need Supabase:**
- Your data only needs to live on one person's device (use `localStorage` instead)
- Projects 01, 02, and 03 can be completed without Supabase
- Project 04 (AI Chat) doesn't require a database either

Supabase is optional for the workshop. The instructor will tell you when it's relevant.

---

## Step 1: Create a Supabase Account

1. Go to [supabase.com](https://supabase.com)
2. Click **Start your project**
3. **Sign up with GitHub** (recommended — reuses your existing account)
4. Authorize Supabase to access your GitHub account
5. You're in

---

## Step 2: Create Your First Project

1. Click **New Project**
2. Fill in:
   - **Name:** `vibe-workshop` (or whatever you're building)
   - **Database Password:** Create a strong password — save it somewhere. You'll need it if you use the database CLI. For the workshop, you likely won't need it directly.
   - **Region:** Choose the closest to Chicago (US East or US Central)
3. Click **Create new project**
4. Wait 1–2 minutes while Supabase provisions your database

```
┌─────────────────────────────────────────────────────┐
│  Your project is being set up...                     │
│                                                      │
│  ████████████████░░░░░░░░░  60%                     │
│                                                      │
│  Setting up database...                              │
└─────────────────────────────────────────────────────┘
```

---

## Step 3: Create Your First Table

Once your project is ready:

1. Click **Table Editor** in the left sidebar (it looks like a spreadsheet icon)
2. Click **New Table**
3. Fill in the table details:

**Example: A table for mood tracker entries**

| Column Name | Type | Notes |
|-------------|------|-------|
| `id` | int8 | Auto-generated, leave as is |
| `created_at` | timestamptz | Auto-generated, leave as is |
| `mood_score` | int4 | 1–5 rating |
| `note` | text | Optional note |
| `user_id` | text | If you're tracking who submitted |

To add a column:
1. Click **Add Column**
2. Enter the name, pick the type from the dropdown
3. Check "Is Nullable" if the column is optional
4. Repeat for each column

4. Click **Save** when done

You now have a database table. It looks like an empty spreadsheet.

---

## Step 4: Get Your API Keys

Your app connects to Supabase using two pieces of information: the project URL and an API key.

1. In your Supabase project, click **Settings** (gear icon, left sidebar)
2. Click **API** under "Project Settings"
3. You'll see:

```
Project URL:
https://[your-project-id].supabase.co

Project API Keys:
anon (public):  eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
service_role:   eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
```

4. Copy both:
   - **Project URL** — you'll use this in your code
   - **anon key** — safe to include in your frontend code (it's designed to be public with proper Row Level Security)

**Never copy or use the `service_role` key in frontend code** — it bypasses all security rules.

---

## Step 5: Connect Supabase to Your Web App

Add the Supabase JavaScript library to your HTML file:

```html
<script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2"></script>
```

Then initialize it:

```javascript
const SUPABASE_URL = 'https://[your-project-id].supabase.co';
const SUPABASE_ANON_KEY = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...';

const { createClient } = supabase;
const db = createClient(SUPABASE_URL, SUPABASE_ANON_KEY);
```

### Reading data (example: get all mood entries)

```javascript
const { data, error } = await db
  .from('mood_entries')
  .select('*')
  .order('created_at', { ascending: false });

if (error) {
  console.error('Error fetching data:', error);
} else {
  console.log('Entries:', data);
}
```

### Writing data (example: save a new mood entry)

```javascript
const { data, error } = await db
  .from('mood_entries')
  .insert([
    { mood_score: 4, note: 'Good day overall' }
  ]);

if (error) {
  console.error('Error saving entry:', error);
} else {
  console.log('Saved!', data);
}
```

**Tip for the workshop:** Paste this prompt into Claude to get Supabase integration code for your specific project:

```
I have a Supabase project. The URL is [your URL] and the anon key is [your key].
I have a table called [table name] with columns: [list columns].

Write the JavaScript code to:
1. [What you want to read or write]
2. Display the results in [where on the page]

I'm using vanilla JavaScript in a single HTML file. No npm, no frameworks.
```

---

## Step 6: Row Level Security (RLS)

By default, Supabase tables have Row Level Security (RLS) enabled, which means **your app can't read or write data until you add policies**.

For a workshop project where any visitor can add data (no login required):

1. Go to **Authentication → Policies** in the left sidebar
2. Find your table
3. Click **New Policy**
4. Select **Create a policy from scratch**
5. For read access: Policy name "Allow public read", Policy command: SELECT, Using expression: `true`
6. For write access: Policy name "Allow public insert", Policy command: INSERT, Using expression: `true`
7. Save

This allows anyone to read and write. For a production app, you'd add user authentication and more specific rules. For the workshop, this is fine.

---

## When to Use Supabase vs. localStorage

| Scenario | Use |
|---------|-----|
| One user, one device, temporary data | `localStorage` |
| One user, want data on any device | Supabase |
| Multiple users sharing data | Supabase |
| Data needs to survive browser clearing | Supabase |
| Simple demo, no persistence needed | Nothing — just in-memory JavaScript |

For Projects 01–03 in the workshop, `localStorage` is usually sufficient. Supabase becomes valuable for projects you continue building after the workshop.

---

## Troubleshooting

### "I'm getting a 403 error"
Your RLS policies aren't set up. Follow Step 6 above.

### "The data isn't showing up in my table"
Check the browser console (right-click → Inspect → Console) for error messages. Paste them into Claude with your code to get a specific fix.

### "I forgot my API keys"
Go to Supabase → Settings → API — they're always visible there.

### "I accidentally deleted a row"
Supabase has no undo button for deletes. This is why you never use the `service_role` key in frontend code — it's too powerful. For demo projects, just re-add the test data.

---

*See also: `vercel-setup.md` (for storing Supabase keys as env vars in production), `docs/phase2/prompting-playbook.md`*
