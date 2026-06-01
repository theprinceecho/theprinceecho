# Notes

## Project Philosophy

This landing page is built with intention — calm, precise, and sovereign. Every change should preserve clarity, elegance, and long-term maintainability.

## Landing Page Refinement (June 2026)

**Current Focus:** Visual system, spacing, depth, and component refinement on `refine/landing-page-v2`.

### Achievements in this iteration
- Introduced comprehensive **Spacing + Typography Design System** (CSS custom properties + fluid `clamp()` scales).
- Significantly improved **generous spacing and breathing room** across sections, with particular attention to mobile rhythm.
- Enhanced **glassmorphism and depth** on cards (layered shadows, better hover states).
- Increased presence of **Recent Transmissions cards** — larger images (120px) and taller cards.
- Removed legacy heavy glow/shadow on main hero logo.
- Explored multiple approaches for the **TPE background watermark** (opacity, sizing, mobile handling, subtle background lift). Currently paused — still not sufficiently visible on mobile.

### Current Status Quo
- Design system and spacing foundation is solid and elegant.
- Visual depth and component refinement progressing well.
- **Open item:** TPE watermark visibility on mobile remains challenging. Further exploration paused for now.
- Overall direction remains calm, sovereign, and high-signal.

### Next Steps (when resumed)
- Revisit watermark with new technical approaches if desired.
- Continue mobile optimization and polish pass.

## GitHub Automation

### Pull Request Workflow

Every pull request to `main` automatically runs:

- **HTML Linting** via HTMLHint (with custom rules in `.htmlhintrc`)
- **Lighthouse CI** (Performance, Accessibility, SEO, Best Practices)
- Basic file validation

### Key Files

| File                              | Purpose                              |
|-----------------------------------|--------------------------------------|
| `.github/workflows/pr-checks.yml` | Main CI workflow                     |
| `.htmlhintrc`                     | Custom HTMLHint rules                |
| `lighthouserc.json`               | Lighthouse CI configuration          |
| `config/project.json`             | Centralized project configuration    |
| `Notes.md`                        | Technical documentation              |

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
└── .github/workflows/pr-checks.yml
```

## Local Development

Open `index.html` in a browser. For a local server:

```bash
npx serve .
```

## How to Contribute

1. Create a feature branch from `main`
2. Make focused, high-quality changes
3. Open a Pull Request
4. Ensure CI checks pass
5. Request review if needed

Please keep changes aligned with the existing design language and tone.

## Future Improvements (Ideas)

- Add a Pull Request template
- Expand Lighthouse assertion thresholds
- Add broken link checking
- Improve documentation further
- Consider image optimization pipeline

## Contact

For questions about the project or automation, reach out via the contact form or X (@ThePrinceEcho).