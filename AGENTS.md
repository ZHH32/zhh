# AGENTS.md

Static HTML/CSS coursework site — no build step, no package manager, no tooling. Open files directly in a browser; there is nothing to install or run.

- Each `*.html` file is a self-contained lesson page; styles are inline in `<style>` blocks, except `css.css` which is linked by early lesson pages (1–4).
- Page filenames are Chinese lesson titles (e.g. `6-1 flex.html`); the `img/` folder holds referenced images — keep relative paths intact when moving files.
- No tests, lint, or typecheck exist. Verify changes by viewing the affected HTML in a browser.
- New `*.html` pages must be added as link-cards in `index.html` (update the works count in `.stats` too).
