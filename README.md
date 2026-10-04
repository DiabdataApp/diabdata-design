<a id="readme-top"></a>

<!-- PROJECT SHIELDS -->

![GitHub contributors](https://img.shields.io/github/contributors/DiabdataApp/diabdata-design?color=blue&label=CONTRIBUTORS)
![GitHub last commit](https://img.shields.io/github/last-commit/DiabdataApp/diabdata-design?label=LAST%20COMMIT)
![License](https://img.shields.io/badge/LICENSE-CC%20BY%204.0-lightgrey)

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/DiabdataApp/diabdata-design">
    <img src="logo/logo_diabdata.svg" alt="Logo" width="80" height="80">
  </a>

<h3 align="center">DiabData Design</h3>
  <p align="center">
  <a href="https://github.com/DiabdataApp/diab-data-android">Android app</a> • <a href="https://github.com/DiabdataApp/diabdata-api-server">API server</a> • <a href="https://app.diabdata.fr/">Website</a>
  </p>
  <p align="center">
    Shared visual identity for the DiabData ecosystem: icons, logos, colors and fonts.
  </p>
  <br/>
</div>

# DiabData Design

This repository is the single place where DiabData's graphical assets live. Every other DiabData project takes what it needs from here instead of keeping its own copy, so an icon or a color only ever has to be changed once.

## Contents

| Folder | What it holds |
|---|---|
| `icons/` | Icons as SVG, in outlined and filled variants |
| `logo/` | Logo variants (full, icon-only, monochrome...) |
| `tokens/` | Colors, typography and spacing written as JSON design tokens |
| `fonts/` | Font files used across the projects |

## Who uses this repo

| Project | What it takes from here |
|---|---|
| [diab-data-android](https://github.com/DiabdataApp/diab-data-android) | Icons (converted to Android VectorDrawables), colors, logo |
| [diabdata-api-server](https://github.com/DiabdataApp/diabdata-api-server) | Logo |
| Website (private repository) | Icons, colors, fonts, logo |

## Naming convention

File names use **lowercase letters, digits and underscores only**, and always **start with a letter**. These are Android's resource naming rules, so every file can be used in the Android app without being renamed.

| Kind | Pattern | Example |
|---|---|---|
| Icon, outlined | `ic_<name>.svg` | `ic_insulin_pen.svg` |
| Icon, filled | `ic_<name>_filled.svg` | `ic_insulin_pen_filled.svg` |
| Logo | `logo_<variant>.svg` | `logo_diabdata.svg`, `logo_diabdata_filled.svg` |

## Icons

Most icons come from Google's [Material Symbols & Icons](https://fonts.google.com/icons?icon.set=Material+Symbols&icon.style=Rounded). Always export them with these settings so every icon looks consistent:

| variant  | weight | grade | optical size | style                            |
|:--------:|:------:|:-----:|:------------:|:---------------------------------|
| Outlined |  400   |   0   |      24      | Material Symbols (new) - Rounded |
|  Filled  |  400   |   0   |      24      | Material Symbols (new) - Rounded |

Custom icons should blend in with them:

- 24 × 24 `viewBox`
- Flat shapes only: no filters, blurs, masks or embedded images
- Colors set through the `fill` attribute, not through `<style>` blocks
- A single color, so each app can tint the icon itself

## Adding an icon

1. Export it from Material Symbols with the settings above, or draw it following the custom icon rules.
2. If you modified a Material Symbols icon by hand, add a comment at the top of the file naming the original. The Apache License 2.0 requires modified files to say so:
   ```xml
   <!-- Modified from Material Symbols "medication" (Google, Apache 2.0) -->
   ```
3. Rename it following the naming convention and place it in `icons/`.
4. If the icon has a filled variant, add both files.
5. Open a pull request saying where the icon will be used.

## Roadmap

- [ ] Write the color palette as design tokens in `tokens/`
- [ ] Generate Kotlin and CSS from the tokens with [Style Dictionary](https://styledictionary.com/)
- [ ] Convert SVG icons to Android VectorDrawables automatically
- [ ] Publish versioned GitHub Releases with ready-to-use bundles for each platform

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## License

- **Custom icons drawn from scratch and design tokens** are released under the [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) license.
- **Icons from Material Symbols, and icons modified from them**, are © Google and distributed under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0). Modified icons say so in a comment at the top of the file.
- **Fonts** keep their original licenses, included next to each font in `fonts/`.
- **The DiabData logo** is not covered by these licenses. It identifies the project and may not be used to represent other apps or services.

## Contact

Florian Cossu - [Linkedin](https://www.linkedin.com/in/florian-cossu/) - [Github](https://github.com/Florian-cossu)

<p align="right">(<a href="#readme-top">back to top</a>)</p>
