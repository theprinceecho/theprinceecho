## ThePrinceEcho Landing Page – Technical Notes

## Project Philosophy
The landing page is built with intention: calm, precise, and sovereign.  
Every change must preserve clarity, elegance, and long-term maintainability.

## Current Status

| Area                        | Status          | Notes |
|----------------------------|------------------|-------|
| Repository Foundation      | Complete        | Clean structure, well organized |
| README.md                  | Complete        | Clean profile description |
| Notes.md                   | **Updated**     | Reflects active work on refine/landing-page-v2 |
| CI Workflow                | Complete        | `pr-checks.yml` strengthened (blocking lint + wait-on) |
| HTML Linting               | Complete        | HTMLHint + custom `.htmlhintrc` |
| Lighthouse CI              | Complete        | Performance, Accessibility & SEO checks |
| Project Config             | Complete        | `config/project.json` updated |
| Quality Gates              | Improved        | Linting is now blocking |
| Visual Direction (v2)      | **In Progress** | New skeleton on refine/landing-page-v2. Cream-on-dark with subtle gradient Hero |
| Overall Maturity           | High            | Maintainable and intentional codebase |

## GitHub Automation
- **Pull Request Workflow** (`pr-checks.yml`):
  - Runs on PRs targeting `main`
  - HTML Linting is now **blocking**
  - Added `wait-on` for reliable Lighthouse runs
  - Lighthouse CI (Performance, Accessibility, SEO, Best Practices)

## Key Files

| File                              | Purpose |
|-----------------------------------|--------|
| `.github/workflows/pr-checks.yml` | Main CI workflow (strengthened) |
| `.htmlhintrc`                     | Custom HTMLHint rules |
| `lighthouserc.json`               | Lighthouse CI configuration |
| `config/project.json`             | Centralized project configuration & design tokens |
| `Notes.md`                        | Technical documentation (this file) |
| `index.html`, `contact.html`, `legal.html` | Core pages (being rebuilt on v2 branch) |

## Active Development – Landing Page v2 (`refine/landing-page-v2`)

**Current Focus**: Rebuilding the landing page on a clean skeleton with CSS Custom Properties.

### Recent Progress
- Established clean **CSS Custom Properties** foundation (cream accents on dark base)
- Started new **Hero / Home section** with subtle radial gradient background
- Navigation aligned with new Hero style
- Emblem kept as `<img>` (no SVG for now)
- Work is being done exclusively on the `refine/landing-page-v2` branch

### Design Direction
- **Color System**: Cream accents on dark base
- **Hero Approach**: Clean + subtle gradient for depth (not flat, not heavy)
- **Philosophy**: Calm, high-signal, elegant, and intentionally minimal

## Local Development
- Open `index.html` directly in a browser, or
- Run `npx serve .` for a local server

## How to Contribute
1. Work on the `refine/landing-page-v2` branch for visual/HTML changes
2. Make focused, high-quality changes
3. Open a Pull Request to `main` when ready
4. Ensure CI checks pass

> Keep changes aligned with the existing calm, precise, and sovereign design language.

## Future Improvements (Roadmap)

- [x] Strengthen CI Quality Gates (completed)
- [ ] Image Optimization (WebP conversion in progress)
- [ ] Complete Hero section on v2 branch
- [ ] Build About section
- [ ] Build Recent Transmissions section
- [ ] Full mobile optimization pass
- [ ] Consider modular CSS structure

## Cloudflare Configuration (Production)
- Redirect Rules: HTTP → HTTPS + www → non-www (correct order)
- SSL/TLS: Full (strict)
- Always Use HTTPS: Enabled
- Security Level: Medium
- Caching: Standard
- Always Online: Enabled

Configuration is considered stable and production-ready.

---

**Contact**  
Use the contact form or X (@ThePrinceEcho) for questions about the project or automation.