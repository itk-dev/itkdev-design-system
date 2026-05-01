# ITK Development — Design System

A small, opinionated visual design system for **ITK Development**, the team in Aarhus Kommune (Kultur og Borgerservice) that designs, builds and maintains digital services for every magistrate in the city.

One palette, one type stack, one set of primitives — used from `itk.aarhus.dk` down to internal admin tools.

> **Live preview:** <https://itk-dev.github.io/itkdev-design-system/>

## What's in here

| Path | Contents |
| --- | --- |
| [`index.html`](index.html) | Landing page / entry point to the system |
| [`tokens.css`](tokens.css) | All design tokens as CSS custom properties — the single source of truth |
| [`tokens/`](tokens/) | Documentation pages: colors, typography, spacing & elevation, logo, components |
| [`examples/website.html`](examples/website.html) | Canonical applied example — the system on a public website |
| [`assets/logos/`](assets/logos/) | Logo files (4-colour, black, white, alternates) |
| [`uploads/`](uploads/) | Source material — colour-code document, original logo files |

No build step. No JavaScript framework. Just static HTML + one CSS file you can drop into any project.

## Using the tokens

Link the stylesheet and use CSS custom properties. Don't hardcode hex values or pixel sizes that exist as tokens.

```html
<link rel="stylesheet" href="https://itk-dev.github.io/itkdev-design-system/tokens.css">
```

```css
.cta {
  background: var(--itk-primary);     /* --itk-blue */
  color: var(--itk-paper);
  padding: var(--itk-space-3) var(--itk-space-5);
  border-radius: var(--itk-radius-2);
  font-family: var(--itk-font-display);
  box-shadow: var(--itk-shadow-1);
}
.cta:focus-visible { box-shadow: var(--itk-focus); }
```

The full token reference lives in [`tokens.css`](tokens.css) — colors, neutral scale, type stack, type scale, spacing, radii, elevation, focus ring, and layout.

## For Claude Code users

Drop this prompt into Claude Code (or the Claude API) to bootstrap a project against the system:

```
Fetch this design system, read its README and CLAUDE.md, and implement the relevant aspects of the design.
https://github.com/itk-dev/itkdev-design-system
Implement: the designs in this project
```

Claude will read [`CLAUDE.md`](CLAUDE.md) for usage rules (token discipline, color roles, typography, logo handling, principles).

## Local preview

Any static server works. From the repo root:

```sh
python3 -m http.server 8000
# open http://localhost:8000
```

## Principles

1. **Clarity over cleverness.** Long-form Danish copy wins over decorative flourishes. Every component earns its place.
2. **Open by default.** The system is shared across OS2, GovTech Midtjylland and partner kommuner. Decisions are documented; tokens are tokens.
3. **The palette is the expression.** Seven faceted hues do the heavy lifting. No gradients, no decorative illustration, no emoji.

## License

[MIT](LICENSE) — © ITK Development, Aarhus Kommune.

## Contact

ITK Development · Aarhus Kommune · Kultur og Borgerservice
[itk@mkb.aarhus.dk](mailto:itk@mkb.aarhus.dk) · [itk.aarhus.dk](https://itk.aarhus.dk)
