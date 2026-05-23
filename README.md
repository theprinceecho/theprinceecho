# ThePrinceEcho

A sovereign landing page for those who sense the urge.

## Overview

This repository contains the official landing page for [ThePrinceEcho](https://theprinceecho.com) — a quiet, high-signal space for reflections on macro cycles, sovereignty, and the convergence of human intelligence with advancing technology.

The site is intentionally minimal, elegant, and focused on clarity.

## Tech Stack

- Static HTML, CSS & JavaScript
- Hosted on GitHub Pages / custom domain
- GitHub Actions for CI

## Project Structure

```
.
├── index.html
├── contact.html
├── legal.html
├── Notes.md
├── .github/workflows/
├── .htmlhintrc
└── lighthouserc.json
```

## Local Development

Simply open `index.html` in a browser. No build step required.

For a local server:
```bash
npx serve .
```

## Pull Requests & Automation

All changes go through Pull Requests. The following checks run automatically:

- HTML linting (HTMLHint with custom rules)
- Lighthouse audits (Performance, Accessibility, SEO)

See [Notes.md](./Notes.md) for the current automation setup and contribution guidelines.

## Philosophy

This project follows a sovereign, high-signal approach:
- Clean and minimal code
- Thoughtful typography and spacing
- Performance and accessibility as first-class citizens
- Long-term maintainability over complexity

## License

All rights reserved.