## ThePrinceEcho Landing Page – Technical Notes

## Project Philosophy
The landing page is built with intention: calm, precise, and sovereign.  
Every change must preserve clarity, elegance, and long-term maintainability.

## Current Status

| Area                        | Status          | Notes |
|----------------------------|------------------|-------|
| Repository Foundation      | Complete        | Clean structure, well organized |
| README.md                  | Complete        | Clean profile description |
| Notes.md                   | **Updated**     | Reflects active visual refinement (v2) |
| CI Workflow                | Complete        | `pr-checks.yml` runs on PRs |
| HTML Linting               | Complete        | HTMLHint + custom `.htmlhintrc` |
| Lighthouse CI              | Complete        | Performance, Accessibility & SEO checks |
| Project Config             | Complete        | `config/project.json` centralized |
| Quality Gates              | Solid           | Professional foundation |
| Visual Direction (v2)      | **In Progress** | Cream accents on dark base + CSS Custom Properties |
| Overall Maturity           | High            | Maintainable and intentional codebase |

## GitHub Automation
- **Pull Request Workflow** (`pr-checks.yml`):
  - Runs on PRs targeting `main`
  - HTML Linting via HTMLHint (custom rules in `.htmlhintrc`)
  - Lighthouse CI (Performance, Accessibility, SEO, Best Practices)
  - Basic file validation

> **Note**: HTML linting currently uses `|| true`. Consider making it blocking once visual work on v2 stabilizes.

## Key Files

| File                              | Purpose |
|-----------------------------------|--------|
| `.github/workflows/pr-checks.yml` | Main CI workflow |
| `.htmlhintrc`                     | Custom HTMLHint rules |
| `lighthouserc.json`               | Lighthouse CI configuration |
| `config/project.json`             | Centralized project configuration & design tokens |
| `Notes.md`                        | Technical documentation (this file) |
| `index.html`, `contact.html`, `legal.html` | Core pages |

## Project Structure
```
.
├── index.html
├── contact.html
├── legal.html
├── README.md
├── Notes.md
├── config/
│   └── project.json
├── .htmlhintrc
├── lighthouserc.json
├── .github/workflows/pr-checks.yml
└── archive/                  # Backup of previous versions during active work
```

## Active Development – Landing Page v2 (`refine/landing-page-v2`)

**Current Focus**: Visual and structural refinement while preserving sovereign, minimalist character.

### Recent Changes
- Established clean **CSS Custom Properties** foundation (cream accents on dark base)
- Refined header: removed language switcher, improved spacing, active states, and hover behavior
- Logo remains linked to `#home`
- Previous version backed up in `archive/` folder on the branch

### Key Decisions
- Language switcher removed (no current functionality, reduces visual clutter)
- Browser Cache TTL kept at **4 hours** temporarily during active visual iteration
- No broad “Cache Everything” Cloudflare Page Rule added at this stage

### Design Direction
- **Color System**: Cream accents on dark base (via CSS Custom Properties)
- **Typography**: Inter with refined scale and spacing
- **Philosophy**: Calm, high-signal, elegant, and intentionally minimal

## Local Development
- Open `index.html` directly in a browser, or
- Run `npx serve .` for a local server

## How to Contribute
1. Create a feature branch from `main` (e.g. `refine/landing-page-v2`)
2. Make focused, high-quality changes
3. Open a Pull Request
4. Ensure CI checks pass
5. Request review if needed

> Keep changes aligned with the existing calm, precise, and sovereign design language.

## Future Improvements (Roadmap)

- [ ] Make HTML linting **blocking** in CI (remove `|| true`)
- [ ] Add Pull Request template
- [ ] Expand Lighthouse assertion thresholds
- [ ] Add broken link checking to CI
- [ ] Implement image optimization pipeline
- [ ] Full mobile optimization pass (fluid typography, touch targets, responsive images)
- [ ] Refine Hero/Home, About, and Recent Transmissions sections
- [ ] Improve documentation further as visual system matures
- [ ] Consider extracting CSS into dedicated files for long-term maintainability

## Cloudflare Configuration (Production)
- Redirect Rules: HTTP → HTTPS + www → non-www (correct order)
- SSL/TLS: Full (strict)
- Always Use HTTPS: Enabled
- Security Level: Medium
- Caching: Standard + 4h Browser Cache TTL (temporary during refinement)
- Always Online: Enabled

Configuration is considered stable and production-ready.

---

**Contact**  
Use the contact form or X (@ThePrinceEcho) for questions about the project or automation.