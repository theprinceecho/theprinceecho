# Notes

## Project Philosophy

This landing page is built with intention — calm, precise, and sovereign. Every change should preserve clarity, elegance, and long-term maintainability.

## Current Automation

### Pull Request Workflow

Every pull request to `main` automatically runs:

- **HTML Linting** via HTMLHint (with custom rules in `.htmlhintrc`)
- **Lighthouse CI** (Performance, Accessibility, SEO, Best Practices)
- Basic file validation

### Files

| File                    | Purpose                              |
|-------------------------|--------------------------------------|
| `.github/workflows/pr-checks.yml` | Main CI workflow                    |
| `.htmlhintrc`           | Custom HTMLHint rules               |
| `lighthouserc.json`     | Lighthouse CI configuration         |
| `Notes.md`              | Project notes and guidelines        |
| `README.md`             | Project overview                    |

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