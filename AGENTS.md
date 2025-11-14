# Repository Guidelines

## Project Structure & Module Organization
The app ships as a single-page bundle in `index.html`, which contains the semantic markup, the glassmorphic CSS theme, and the vanilla JavaScript calculator logic. Inputs, result blocks, and helper text are grouped with `.card`, `.input-group`, and `.results` wrappers—preserve those hooks when extending the UI. There are no external assets; new icons or fonts should live alongside the document and reference relative paths to remain offline-first.

## Build, Test, and Development Commands
- `open index.html` (macOS) or `xdg-open index.html` (Linux) previews the static file directly in the browser.
- `python3 -m http.server 4173` serves the repo root for local testing with DevTools and avoids CORS issues when importing future assets.
- `npx prettier --write index.html` keeps the single source file formatted; install Prettier globally if you prefer a faster alias.

## Coding Style & Naming Conventions
Indent HTML, CSS, and JS blocks with four spaces as in the existing file. Use lowercase, hyphenated class names (e.g., `.result-details`), CSS custom properties for design tokens (`--accent`), and descriptive `data-*` attributes when adding controls. JavaScript should stay self-invoking, rely on `const`/`let`, camelCase variables (`resultValue`), template literals for dynamic strings, and guard against invalid numeric input before mutating the DOM.

## Testing Guidelines
There is no automated suite; rely on manual flows. Verify initial render with empty inputs, realistic dog weights (5 kg, 35 kg), and extreme values to confirm the exponent formula stays stable. Check that the spin buttons dispatch `input` events, that two-meal guidance updates instantly, and that `localStorage` retains edits after refresh. Document edge-case observations in the pull request when changes touch calculation logic or persistence.

## Commit & Pull Request Guidelines
Adopt Conventional Commits (`feat: add meal presets`, `fix: clamp negative weight`) to keep the linear history searchable. Each PR should describe the motivation, outline manual test steps, and attach before/after screenshots or screen recordings for UI tweaks. Reference related issues, call out any new browser requirements, and note follow-up work so reviewers can reason about scope quickly.

## Security & Configuration Tips
The calculator runs entirely client-side, but it still touches user-specific data. Never log raw inputs in production builds, and avoid introducing external scripts without pinning their versions. Keep secrets out of the repo, and remind contributors that localStorage persists per browser profile—clear it between demos when sharing devices.
