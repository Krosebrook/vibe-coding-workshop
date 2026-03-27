# Repository Agents

> Automated agents and bots configured for this GitHub repository.

---

## Active Agents

### 1. GitHub Copilot

**Type:** AI coding assistant  
**Scope:** Pull requests, code review, documentation  
**Status:** Active  

GitHub Copilot is enabled for this repository and provides:
- Code suggestions in the editor
- PR description generation
- Code review comments
- Documentation generation

**Configuration:** See `CLAUDE.md` for context file (also used by Copilot).

---

### 2. Dependabot

**Type:** Dependency security bot  
**Scope:** Dependency updates and vulnerability alerts  
**Status:** Configured (activate via GitHub repo settings)  

**Recommended `.github/dependabot.yml`:**

```yaml
version: 2
updates:
  - package-ecosystem: "github-actions"
    directory: "/"
    schedule:
      interval: "weekly"
    labels:
      - "dependencies"
      - "automated"
```

> **Note:** This repo has no npm/pip dependencies currently. Dependabot is configured for GitHub Actions only.

---

### 3. GitHub Actions CI

**Type:** Continuous integration  
**Scope:** HTML validation, link checking  
**Status:** Recommended (not yet configured)  

**Recommended workflow (`.github/workflows/ci.yml`):**

```yaml
name: CI

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  validate:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Validate HTML
        uses: Cyb3r-Jak3/html5validator-action@v7.2.0
        with:
          targets: index.html
          css: true

      - name: Check links
        uses: lycheeverse/lychee-action@v1
        with:
          args: --verbose --no-progress index.html README.md
```

---

### 4. Lighthouse CI

**Type:** Performance & accessibility monitoring  
**Scope:** Web performance, accessibility, SEO audits  
**Status:** Recommended  

**Recommended workflow (`.github/workflows/lighthouse.yml`):**

```yaml
name: Lighthouse CI

on:
  push:
    branches: [main]

jobs:
  lighthouse:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Run Lighthouse CI
        uses: treosh/lighthouse-ci-action@v10
        with:
          urls: |
            http://localhost/
          uploadArtifacts: true
          temporaryPublicStorage: true
```

---

### 5. CodeQL Analysis

**Type:** Security scanning  
**Scope:** Code vulnerability detection  
**Status:** Recommended for future JS additions  

When JavaScript is added to the project, enable CodeQL:

```yaml
name: CodeQL

on:
  push:
    branches: [main]
  schedule:
    - cron: '0 12 * * 1'

jobs:
  analyze:
    runs-on: ubuntu-latest
    permissions:
      security-events: write
    steps:
      - uses: actions/checkout@v4
      - uses: github/codeql-action/init@v3
        with:
          languages: javascript
      - uses: github/codeql-action/autobuild@v3
      - uses: github/codeql-action/analyze@v3
```

---

## Agent Interaction Guidelines

### For Pull Requests

When opening a PR:
1. GitHub Copilot will suggest a description — review and edit before merging
2. CI workflows validate HTML and check links automatically
3. Lighthouse CI scores are posted as PR comments

### For Dependency Updates

Dependabot will open PRs for:
- GitHub Actions version updates (weekly)
- npm packages (if added in the future)

Auto-merge Dependabot PRs for minor/patch GitHub Actions updates:

```yaml
# .github/workflows/dependabot-auto-merge.yml
name: Dependabot auto-merge
on: pull_request

permissions:
  contents: write
  pull-requests: write

jobs:
  dependabot:
    runs-on: ubuntu-latest
    if: github.actor == 'dependabot[bot]'
    steps:
      - name: Auto-merge
        run: gh pr merge --auto --squash "$PR_URL"
        env:
          PR_URL: ${{github.event.pull_request.html_url}}
          GH_TOKEN: ${{secrets.GITHUB_TOKEN}}
```

---

## Branch Protection Rules

Recommended settings for `main` branch:

| Setting | Value |
|---------|-------|
| Require PR before merging | ✅ |
| Required approvals | 1 |
| Require status checks | ✅ (CI: validate) |
| Require branches to be up to date | ✅ |
| Restrict force pushes | ✅ |
| Restrict deletions | ✅ |

---

*See also: [docs/agents.md](../agents.md) | [docs/copilot-skills/](../copilot-skills/)*
