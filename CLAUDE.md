# CLAUDE.md — ITK Development Design System

Instructions for Claude Code (and other AI coding agents) when applying this design system to a project.

## What this is

A static, no-build design system: one stylesheet (`tokens.css`) defining every brand color, type ramp, spacing step, radius, shadow, and focus ring as CSS custom properties; HTML reference pages under `tokens/`; and a canonical applied example in `examples/website.html`.

When asked to "use the ITK design system", "apply ITK styling", or similar:

1. Link `tokens.css` (or the published version on GitHub Pages).
2. Style with the custom properties — never hardcode values that exist as tokens.
3. Match the look of `examples/website.html` for layout, typography, and color usage.

## Token discipline

**Use the token, not the value.**

| Don't | Do |
| --- | --- |
| `color: #007BA6;` | `color: var(--itk-blue);` or `var(--itk-primary);` |
| `padding: 16px;` | `padding: var(--itk-space-4);` |
| `border-radius: 6px;` | `border-radius: var(--itk-radius-2);` |
| `font-family: "Inter Tight", sans-serif;` | `font-family: var(--itk-font-display);` |
| `box-shadow: 0 4px 10px ...;` | `box-shadow: var(--itk-shadow-2);` |

If a value isn't in `tokens.css`, prefer composing tokens (e.g. `calc(var(--itk-space-4) * 2)`) over introducing a magic number. If a missing token is genuinely needed, add it to `tokens.css` rather than inlining the value.

## Color roles

The seven brand hues come from the ITK logo. They're not interchangeable.

- **`--itk-blue` (primary)** — primary actions, links, focus ring, default brand surface. Most UI chrome should be blue.
- **`--itk-red` (accent)** — destructive actions, "Afsluttet" / closed state, sparing emphasis. **Never** use red as the primary brand color in a layout.
- **`--itk-green`** — success, "Aktiv" / active state.
- **`--itk-cyan`, `--itk-aqua`, `--itk-mint`, `--itk-lime`** — supporting hues for charts, illustration, the rainbow divider, and category tags. Don't use them as primary action colors.
- **Neutrals (`--itk-ink`, `--itk-slate-700` through `--itk-slate-50`, `--itk-paper`)** — body copy, surfaces, borders, muted text.

The full **rainbow gradient** (red → lime → green → mint → aqua → cyan → blue) is reserved for dividers and the brand expression. Don't reuse it on buttons, cards, or hover states.

## Typography

- **`--itk-font-display` / `--itk-font-sans`** — Inter Tight. Headings use tight letter-spacing (`-0.01em` to `-0.04em` for very large display).
- **`--itk-font-mono`** — JetBrains Mono. Reserved for code, numeric IDs, technical metadata, eyebrow labels (uppercase + tracked letter-spacing).
- Load fonts from Google Fonts as in `index.html`:
  ```html
  <link href="https://fonts.googleapis.com/css2?family=Inter+Tight:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
  ```
- Type scale runs `--itk-text-xs` (12px) → `--itk-text-5xl` (88px). Pick the named step, don't invent in-between sizes.
- Body copy is Danish-first (æøå). Don't substitute fonts that lack proper Danish glyph support.

## Spacing & layout

- 4px base scale: `--itk-space-1` (4px) → `--itk-space-9` (96px). Default container is `--itk-container` (1200px) with `--itk-gutter` (24px).
- Radii: `--itk-radius-0` through `--itk-radius-4`, plus `--itk-radius-pill` for chips/badges.
- Elevation: `--itk-shadow-1` (subtle), `--itk-shadow-2` (cards), `--itk-shadow-3` (modals/popovers). Three steps, no more.
- Focus state: always use `--itk-focus` on `:focus-visible`. Do not remove default focus styling without replacing it.

## Logo

- Primary mark: `assets/logos/itk-4f-1.png` (four-colour). Use this on light backgrounds.
- On dark backgrounds: `assets/logos/itk-hvid-*.png` (white).
- Single-colour print / monochrome: `assets/logos/itk-sort-*.png` (black).
- The `itk-dev-*` variants include the "Development" wordmark — use those when ITK Development specifically (rather than ITK as a whole) needs to be credited.
- Maintain clear space and do not recolor the mark. See `tokens/logo.html` for guidance.

## Principles to defer to

When a design decision isn't covered here, defer to these (from `index.html`):

1. **Clarity over cleverness.** 360 000 citizens read these services. Plain Danish copy and obvious affordances beat decorative flourishes.
2. **Open by default.** Code and design are shared across OS2, GovTech Midtjylland and partner kommuner. Document choices; reuse tokens.
3. **The palette is the expression.** No gradients, no decorative illustration, no emoji. The triangles and the colours are enough.

## Reference

- `tokens.css` — all tokens
- `tokens/colors.html`, `tokens/typography.html`, `tokens/spacing.html`, `tokens/logo.html`, `tokens/components.html` — visual reference per category
- `examples/website.html` — applied example, the canonical "this is what good looks like"
