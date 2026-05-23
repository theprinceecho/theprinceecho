# ThePrinceEcho

A sovereign landing page for those who sense the urge.

![ThePrinceEcho GitHub Setup](assets/github-setup-flowchart.jpg)

## Overview

This repository contains the official landing page for [ThePrinceEcho](https://theprinceecho.com) — a quiet, high-signal space for reflections on macro cycles, sovereignty, and the convergence of human intelligence with advancing technology.

The site is intentionally minimal, elegant, and focused on clarity.

## Tech Stack

- Static HTML, CSS & JavaScript
- GitHub Actions for CI

## GitHub Automation

The project uses a robust CI setup focused on quality and maintainability:

- **HTML Linting** with custom rules
- **Lighthouse CI** for performance, accessibility, and SEO
- Automated checks on every Pull Request

See the flowchart above for the full architecture.

## Project Structure

```
.
├── index.html
├── contact.html
├── legal.html
├── README.md
├── Notes.md
├── config/project.json
├── .htmlhintrc
├── lighthouserc.json
└── .github/workflows/pr-checks.yml
```

## Local Development

Open `index.html` in a browser. For a local server:
```bash
npx serve .
```

## Pull Requests

All contributions go through Pull Requests. Automated checks (HTML linting + Lighthouse) run on every PR to maintain quality.

## Philosophy

This project follows a sovereign, high-signal approach with focus on clarity, performance, and long-term maintainability.

## License

All rights reserved.