# CLAUDE.md

Guidance for Claude and other AI assistants working in this repository.

## What this repository is

`diabdata-design` holds the graphical assets shared by the DiabData ecosystem: icons, logos, design tokens (colors, typography, spacing) and fonts. It is a source of truth, not an app. Other repositories consume its files, so a change here can affect several projects at once.

Consumers:

- `diab-data-android`: Kotlin / Jetpack Compose app with `app`, `wear` and `widget` modules. Assets land in its `shared` module. It cannot use SVG directly: icons must be converted to Android VectorDrawable XML.
- `diabdata-api-server`: Bun server, uses the logo only.
- A private Next.js website: uses icons, colors, fonts and the logo.

## Layout

```
icons/    SVG icons, outlined and filled variants
logo/     logo variants
tokens/   JSON design tokens
fonts/    font files, each with its license
```

Generated output, once tooling exists, goes in `dist/`, which is git-ignored.

## Rules

### Naming

- Lowercase letters, digits and underscores only; must start with a letter (Android resource rules).
- Icons: `ic_<name>.svg` for outlined, `ic_<name>_filled.svg` for filled.
- Logos: `logo_<variant>.svg`.
- Flag any file name that breaks these rules instead of silently accepting it.

### SVG requirements

- Material Symbols icons are exported as: Rounded style, weight 400, grade 0, optical size 24.
- Custom icons: 24 × 24 viewBox, flat shapes, single color set via the `fill` attribute.
- No filters, blurs, masks, `<style>` blocks or embedded raster images: these break or degrade when converted to Android VectorDrawables.
- Icons modified from Material Symbols must start with a comment naming the original, e.g. `<!-- Modified from Material Symbols "medication" (Google, Apache 2.0) -->`. Apache 2.0 section 4(b) requires it. They stay under Apache 2.0, not CC BY 4.0. Flag any modified icon missing this comment.

### Things to avoid

- Renaming or deleting an existing asset is a **breaking change**: consumers reference files by name. Never do it silently; point out which repositories may be affected.
- Do not edit, redraw or recolor the logo unless explicitly asked.
- Do not add PNG or JPG files to `icons/`.
- Do not commit generated files.
- Do not relicense fonts; they keep their original licenses.

### Transition period

Assets are being copied here from the other repositories. The originals still exist in those repositories on purpose, so nothing breaks before a sync mechanism exists. Do not suggest deleting them from consumer repositories until that mechanism is in place.

## Planned, not yet in place

The roadmap includes Style Dictionary for tokens, automated SVG to VectorDrawable conversion, and versioned GitHub Releases with per-platform bundles. None of this exists yet: do not assume these tools, scripts or workflows are present.

## Working with the maintainer

The maintainer is a beginner using this project to learn, especially about Android, Gradle and CI.

- Explain the concepts behind a suggestion, not only the suggestion itself.
- Prefer ideas, pseudo-code and links to official documentation over complete implementations, unless complete files are explicitly requested.
- Point out common pitfalls before they happen.
- Suggest the simplest approach first; mention more advanced options as next steps.
