# Participant Portal Spec

> Feature specification for the Vibe Coding Workshop participant portal — the login-gated hub where alumni access resources, submit projects, and track their progress.

---

## Overview

The participant portal is a protected web application that replaces the "email a PDF and hope they open it" distribution model. It gives alumni a persistent place to:

1. Access all workshop resources (guidebooks, playbooks, templates)
2. Submit and showcase their projects
3. Track their progress and completion
4. Connect with other participants

**Phase 3 goal:** Ship a v1 portal that handles authentication, resource access, and project submission. Keep it simple — no feature creep.

---

## User Types

| Role | Description | Access |
|------|-------------|--------|
| `participant` | Completed a paid workshop (live or self-paced) | Resources, project submission, showcase |
| `alumni` | Completed workshop + 30 days post | Full access, peer review, showcase visibility |
| `instructor` | Kyle or guest instructors | All of the above + analytics, roster management |
| `admin` | Kyle only | Full system access, user management, content management |

---

## v1 Feature Scope

### Must Have (v1)
- [ ] Email/password authentication (Supabase Auth)
- [ ] Magic link login option
- [ ] Dashboard landing page (welcome, cohort name, quick links)
- [ ] Resource library (downloadable guidebooks, playbooks, templates — all PDFs)
- [ ] Project submission form (URL + description + project number)
- [ ] My Projects page (submitted URLs, completion status)
- [ ] Basic profile page (name, cohort, bio)

### Nice to Have (v1)
- [ ] Project showcase view (all participants' submitted projects, opt-in)
- [ ] Completion badge/certificate download
- [ ] Instructor announcement banner
- [ ] Search across resource library

### Out of Scope (v1)
- Payment integration (handled separately)
- Video hosting
- Community/messaging features (use Discord for now)
- Mobile app

---

## Tech Stack Recommendation

| Layer | Technology | Rationale |
|-------|------------|-----------|
| Frontend | Next.js (App Router) or Remix | Server-side rendering, good auth support |
| Authentication | Supabase Auth | Already used in workshop, consistent for learners |
| Database | Supabase (PostgreSQL) | Same as auth, Row Level Security for data isolation |
| File storage | Supabase Storage | PDF/asset storage for resources |
| Hosting | Vercel | Consistent with workshop stack |
| Styling | Tailwind CSS | Fast iteration, consistent with design system |

**Why not vanilla HTML?** The portal requires dynamic auth state and per-user data. That warrants a JavaScript framework. Supabase + Next.js mirrors exactly what participants build in Vibe Coding 2.0 — it's a teaching asset too.

---

## Data Models

### User Profile

```sql
CREATE TABLE profiles (
  id UUID PRIMARY KEY REFERENCES auth.users(id),
  full_name TEXT NOT NULL,
  github_username TEXT,
  cohort_id TEXT NOT NULL,
  cohort_type TEXT CHECK (cohort_type IN ('in-person', 'virtual', 'self-paced', 'corporate')),
  bio TEXT,
  avatar_url TEXT,
  created_at TIMESTAMPTZ DEFAULT NOW(),
  updated_at TIMESTAMPTZ DEFAULT NOW()
);
```

### Project Submission

```sql
CREATE TABLE project_submissions (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  user_id UUID NOT NULL REFERENCES profiles(id),
  project_number INTEGER NOT NULL CHECK (project_number BETWEEN 1 AND 4),
  project_name TEXT NOT NULL,
  live_url TEXT NOT NULL,
  description TEXT,
  is_showcase_public BOOLEAN DEFAULT FALSE,
  submitted_at TIMESTAMPTZ DEFAULT NOW()
);
```

### Resource Library

```sql
CREATE TABLE resources (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  title TEXT NOT NULL,
  description TEXT,
  category TEXT CHECK (category IN ('guidebook', 'playbook', 'template', 'presentation', 'other')),
  file_url TEXT NOT NULL,
  is_public BOOLEAN DEFAULT FALSE,
  cohort_access TEXT[] DEFAULT '{}', -- empty array = all cohorts
  created_at TIMESTAMPTZ DEFAULT NOW()
);
```

### Cohorts

```sql
CREATE TABLE cohorts (
  id TEXT PRIMARY KEY, -- e.g., 'summer-2026-01'
  name TEXT NOT NULL, -- e.g., 'Summer 2026 — Cohort 1'
  format TEXT CHECK (format IN ('in-person', 'virtual', 'corporate', 'self-paced')),
  date DATE,
  capacity INTEGER,
  status TEXT CHECK (status IN ('upcoming', 'active', 'completed'))
);
```

---

## Row Level Security Policies

All tables use RLS to enforce data isolation:

```sql
-- Participants can only read their own profile
ALTER TABLE profiles ENABLE ROW LEVEL SECURITY;
CREATE POLICY "Users can view own profile"
  ON profiles FOR SELECT
  USING (auth.uid() = id);

-- Participants can view all public project submissions
CREATE POLICY "Public showcase is readable by authenticated users"
  ON project_submissions FOR SELECT
  USING (auth.role() = 'authenticated' AND is_showcase_public = TRUE);

-- Participants can only edit their own submissions
CREATE POLICY "Users can manage own submissions"
  ON project_submissions FOR ALL
  USING (auth.uid() = user_id);

-- Resources accessible to authenticated users
CREATE POLICY "Authenticated users can read resources"
  ON resources FOR SELECT
  USING (auth.role() = 'authenticated');
```

---

## Page Map

```
/                     → Public marketing site (index.html)
/login                → Login page (email + magic link)
/dashboard            → Authenticated home (post-login)
/dashboard/resources  → Resource library (guidebooks, playbooks, templates)
/dashboard/projects   → My submitted projects + completion status
/dashboard/submit     → Submit a new project URL
/dashboard/showcase   → Public showcase (opt-in projects from all alumni)
/dashboard/profile    → Edit profile (name, bio, GitHub username)
/admin                → Instructor/admin only: roster, analytics, content management
```

---

## Authentication Flow

```
1. Participant clicks "Log in" on marketing site
2. Redirected to /login
3. Enters email address
4. Option A: Magic link sent to email
   - Clicks link → authenticated, redirected to /dashboard
5. Option B: Password (if set)
   - Enters password → authenticated, redirected to /dashboard
6. New participants:
   - First login → prompted to complete profile (name, GitHub username)
   - System checks cohort access based on email → grants role
```

---

## Invitation / Access Control Flow

New participants gain portal access via invite:

1. Instructor registers participant in Supabase (email + cohort ID)
2. System sends magic link invite email automatically
3. Participant clicks link → completes profile setup
4. Cohort ID grants appropriate resource access

This avoids open public registration — only paid/attended participants get in.

---

## Design System

The portal extends the main site's design system:

```css
/* Same base tokens as index.html */
--bg: #0a0a0a;
--surface: #111111;
--border: #222222;
--text: #e8e8e8;
--accent: #7c3aed;
--accent-light: #a78bfa;
--green: #10b981;
```

Tailwind configuration maps these to custom utilities:
```js
// tailwind.config.js
extend: {
  colors: {
    bg: '#0a0a0a',
    surface: '#111111',
    border: '#222222',
    accent: '#7c3aed',
    'accent-light': '#a78bfa',
    green: '#10b981',
  }
}
```

---

## v1 Launch Checklist

- [ ] Supabase project created with all tables and RLS policies
- [ ] Next.js app scaffolded and deployed to Vercel
- [ ] Authentication working (magic link + email/password)
- [ ] Dashboard page renders cohort info from profile
- [ ] Resource library shows all PDFs for the user's cohort
- [ ] Project submission form saves to database
- [ ] My Projects page shows submitted URLs
- [ ] Basic profile edit works
- [ ] Invitation flow tested with 5 real participants (Summer 2026 cohort)
- [ ] Mobile-responsive

---

## Success Metrics (v1)

| Metric | Target |
|--------|--------|
| % of alumni who log in within 7 days of workshop | > 80% |
| % of alumni who submit all 4 project URLs | > 60% |
| % of alumni who download at least 1 resource | > 70% |
| Support emails related to portal access | < 5% of users |

---

*Owner: Kyle Rosebrook · Part of [Phase 3 documentation](./README.md)*
