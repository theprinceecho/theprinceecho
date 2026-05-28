# Notes

## Project Philosophy

This landing page is built with intention — calm, precise, and sovereign. Every change should preserve clarity, elegance, and long-term maintainability.

## Current Status

| Area                        | Status     | Notes                                           |
|----------------------------|------------|-------------------------------------------------|
| **Repository Foundation**  | 🟢 ✅      | Clean structure, well organized                 |
| **README.md**              | 🟢 ✅      | Clean profile description                       |
| **Notes.md**               | 🟢 ✅      | Technical documentation                         |
| **CI Workflow**            | 🟢 ✅      | `pr-checks.yml` running on PRs                  |
| **HTML Linting**           | 🟢 ✅      | HTMLHint + custom `.htmlhintrc`                 |
| **Lighthouse CI**          | 🟢 ✅      | Performance, Accessibility & SEO checks         |
| **Project Config**         | 🟢 ✅      | `config/project.json` centralized               |
| **Quality Gates**          | 🟢         | Solid PR validation in place                    |
| **Overall Maturity**       | 🟢         | Professional and maintainable foundation        |

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
