# Security Policy

## Supported Versions

| Version | Supported |
|---------|-----------|
| Current (`main` branch) | ✅ |
| All previous commits | ❌ |

This is a static HTML website. There are no versioned releases with separate security support windows.

---

## Reporting a Vulnerability

**Please do not report security vulnerabilities through public GitHub Issues.**

If you discover a security vulnerability in this project, please report it privately:

**Email:** [hello@vibecodingworkshop.com](mailto:hello@vibecodingworkshop.com)  
**Subject line:** `[SECURITY] Brief description`

### What to Include

- A description of the vulnerability
- Steps to reproduce
- Potential impact
- Suggested fix (if known)

### Response Timeline

| Action | Timeline |
|--------|----------|
| Acknowledgment | Within 48 hours |
| Initial assessment | Within 5 business days |
| Fix or mitigation | Within 30 days for critical issues |
| Public disclosure | After fix is deployed |

---

## Security Considerations for This Project

### Current Attack Surface

This project is a **static HTML site** with no backend, no database, no authentication, and no JavaScript. The attack surface is minimal:

- No server-side code
- No user data storage (waitlist form links to `mailto:`)
- No cookies or local storage
- No third-party scripts
- No API endpoints

### Potential Vectors

Despite the minimal surface area, consider:

1. **Supply chain attacks** — If CDN-hosted fonts or libraries are ever added, ensure SRI (Subresource Integrity) hashes are used
2. **GitHub Pages configuration** — Ensure the deployment branch is protected
3. **Email harvesting** — The `mailto:` link exposes the business email address (acceptable tradeoff for this use case)
4. **Phishing/typosquatting** — Impersonators could register similar domains

### Security Headers (Recommended)

If hosting on GitHub Pages or Netlify, add a `_headers` or equivalent file:

```
/*
  Content-Security-Policy: default-src 'self'; style-src 'self' 'unsafe-inline'; font-src 'self' https://fonts.gstatic.com; img-src 'self' data:
  X-Frame-Options: DENY
  X-Content-Type-Options: nosniff
  Referrer-Policy: strict-origin-when-cross-origin
  Permissions-Policy: camera=(), microphone=(), geolocation=()
```

---

## Dependency Security

Currently, this project has **zero runtime dependencies**. If dependencies are ever added:

1. Run `npm audit` before merging any dependency changes
2. Use `npm audit --audit-level=high` in CI
3. Keep dependencies updated via Dependabot (already configured on this repo)

---

## Responsible Disclosure

We follow a **coordinated disclosure** policy:

1. Reporter notifies us privately
2. We acknowledge and begin investigation
3. We develop and test a fix
4. We deploy the fix
5. We thank the reporter (with permission, publicly)
6. After fix is live, reporter may publish their findings

We will not pursue legal action against researchers who:
- Act in good faith
- Avoid accessing or modifying user data
- Do not perform denial-of-service attacks
- Report findings to us before public disclosure

---

## Hall of Fame

Security researchers who have responsibly disclosed issues will be recognized here (with permission).

*No reports yet.*

---

*Questions? Contact [hello@vibecodingworkshop.com](mailto:hello@vibecodingworkshop.com)*
