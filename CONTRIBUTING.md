# Contributing to Reference Storage

Thanks for taking the time to look at this project. Reference Storage is an academic prototype built for the **M7 HR Management & Leadership** module at HTW Berlin, so the bar for contributions is "does this improve the demo or its documentation" — not full-scale product development.

## What we welcome

- Typo, grammar, and clarity fixes in `README.md` or `index.html`
- Accessibility improvements (semantic HTML, ARIA labels, keyboard navigation, focus states, colour contrast)
- Performance fixes (deferring scripts, reducing layout shift, removing unused Tailwind classes)
- Browser-compatibility bug reports
- Hardening of the Firebase / `localStorage` data layer — better error handling, schema migrations, edge cases
- Roadmap items: BibTeX / RIS export, DOI / BibTeX import, Playwright smoke tests, localisation
- Documentation improvements — clearer setup steps, security notes, citations

## What we won't merge

- A real Firebase config or any other credential — see [security](#security) below
- Backend services or persistent stored data beyond Firestore / `localStorage` — this is a static demo by design
- Large refactors or framework migrations (e.g. moving to React, Next.js, or a build pipeline); discuss in an issue first
- Visual redesigns that change the academic-presentation aesthetic without a clear rationale

## Workflow

1. **Open an issue first** for anything larger than a typo, so we can confirm the change fits the project scope.
2. Fork the repository and create a topic branch:
   ```bash
   git checkout -b fix/short-description
   ```
3. Make the change. Keep diffs small and focused.
4. Manually verify the demo still renders correctly:
   - Open `index.html` in Chrome / Firefox / Safari, or
   - Run `python -m http.server 8080` and visit <http://localhost:8080>
   - Walk through: add a reference → check sort order → edit a header → delete a reference → reload to verify persistence
   - If Firebase is configured, repeat the round-trip with the Firestore tab open in the console
5. Commit with a clear message (imperative mood, e.g. `Fix focus ring on delete-confirmation modal`).
6. Open a pull request against `main` describing **what changed and why**, with a screenshot if the change is visual.

## Coding style

- **HTML / CSS / JS** live in one file by design. Don't split them out unless you're discussing a production refactor in an issue first.
- Two-space indentation, double quotes for HTML attributes, single quotes for JS strings.
- Prefer Tailwind utility classes over new custom CSS. If you must add CSS, put it inside the existing `<style>` block.
- No new third-party CDN dependencies without prior discussion — current CDNs are Tailwind, Firebase, and Google Fonts.
- ES modules only. Don't introduce CommonJS or globals beyond the two documented Firebase injection points (`__firebase_config`, `__app_id`).

## Security

This is a public repository. Treat anything you commit as published.

- **Never** paste a real Firebase API key, project ID, or service-account JSON into a commit, an issue, or a PR description. Local-only configs belong in files matched by `.gitignore` (e.g. `firebase-config.local.js`).
- If you accidentally commit a credential, **rotate it immediately** in the Firebase Console and force-push a history-rewritten branch — opening a public issue describing the leak only makes it worse.
- When extending the Firestore schema, update the Security Rules in the same PR — default-deny is the only safe baseline.

## Reporting issues

Please include:

- Browser and version
- Whether Firebase was configured
- Steps to reproduce
- Expected vs. actual behaviour
- Screenshot or short screen capture if the issue is visual
- Relevant console / network errors

## Code of conduct

Be kind, be specific, assume good faith. Disagreement on technical decisions is welcome; personal attacks are not.

## License

By contributing, you agree that your contributions are licensed under the [MIT License](LICENSE) covering this repository.
