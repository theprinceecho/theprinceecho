# Notes

## Project Philosophy

This landing page is built with intention — calm, precise, and sovereign. Every change should preserve clarity, elegance, and long-term maintainability.

## Landing Page Refinement (June 2026)

**Current Focus:** Visual system, spacing, depth, component refinement, and final logo integration on `refine/landing-page-v2`.

### Key Achievements

- Introduced comprehensive **Spacing + Typography Design System**.
- Significantly improved **generous spacing and breathing room**, especially on mobile.
- Enhanced **glassmorphism and visual depth** on cards.
- **Mobile optimizations**:
  - Reduced main hero logo size.
  - Improved nav alignment and spacing.
- Restructured **Recent Transmissions cards**:
  - Increased image size (140px) and card height.
  - Added stacked Roman numeral labels ("Essay I", "Essay II", etc.) for better scannability.
- Fixed **footer brand alignment** (logo + text now properly aligned).
- Aligned section headers for better visual coherence (added subtitle + divider to "Where to Find What").
- Shifted overall **color palette** to deeper charcoal (`#121212`) to better match the final lion + wolf emblem.
- Explored TPE watermark visibility (currently paused).

### Current Status Quo
- Strong design system and spacing foundation in place.
- Transmission section now much more scannable and substantial.
- Visual harmony with the final logo has been significantly improved.
- Overall direction remains calm, sovereign, and high-signal.

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