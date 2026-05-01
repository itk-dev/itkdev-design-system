# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Changed

- ITK Development is now part of **Borgmesterens Afdeling** (BA) rather than Kultur og Borgerservice. Updated department references in `index.html`, `README.md`, `examples/website.html`, and `tokens/logo.html`. Email address (`itk@mkb.aarhus.dk`) and the Hetzner sample news copy are unchanged for now.

### Fixed

- `examples/website.html`: department list now uses `border-bottom` per row so the first row no longer hugs the cell's top edge and the last row doesn't appear clipped — uniform vertical rhythm across all six items.

### Added

- `robots.txt` and `noindex` meta tag on `examples/website.html` to keep the applied example out of search engines.
- Initial repository setup for the ITK Development Design System.
- `tokens.css` — design tokens (colors, neutral scale, typography, type scale, spacing, radii, elevation, focus ring, layout) as CSS custom properties.
- `index.html` — landing page indexing foundations, brand, and applied examples.
- `tokens/` — reference pages for colors, typography, spacing, logo, and components.
- `examples/website.html` — applied example showing the system on a public website.
- `assets/logos/` — primary, white, black, and ITK Development logo variants.
- `README.md` documenting repo layout and usage.
- `CLAUDE.md` with rules for AI coding agents applying the design system.
- `LICENSE` (MIT).
- GitHub Actions workflow to deploy the static site to GitHub Pages on push to `main`.
