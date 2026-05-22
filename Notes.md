# Notes

## GitHub Automation

### Pull Request Validation

A basic GitHub Actions workflow has been added to automatically run checks on pull requests.

**Location:** `.github/workflows/pr-checks.yml`

**Trigger:** Every pull request targeting the `main` branch.

**Current Behavior:**
- Checks out the repository
- Performs a basic validation of core landing page files (`index.html`, `contact.html`, `legal.html`)
- Confirms the PR structure is ready for review

This serves as a clean, minimal foundation for future automation.

### Future Expansion Ideas
- Add HTML linting / validation
- Broken link checking
- Preview deployments for visual review
- Performance or accessibility checks

## Pull Request Workflow

1. Create a feature branch from `main`
2. Make focused, clean changes
3. Open a Pull Request targeting `main`
4. Automated checks will run automatically
5. Once checks pass and the PR is reviewed, it can be merged

Please keep changes minimal and follow the existing elegant, sovereign style of the landing page.