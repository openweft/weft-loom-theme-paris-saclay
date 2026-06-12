# weft-loom-theme-paris-saclay

`paris-saclay` brand theme for weft-loom compile tooling.

**Signature** : `#62003C` — deep aubergine / wine, sourced directly
from the institutional SVG logo. The earlier draft used chartreuse
`#84BD00` which has no grounding in the current visual identity.

## Source

Direct read of the official SVG logo
(`universite-paris-saclay.fr/sites/default/files/media/2019-12/logo-ups.svg`,
2026-06 audit) — the wordmark glyphs fill with **`#62003C`** and no
other colour. The site stylesheet uses utility greys + Bootstrap
defaults for layout, but the brand colour is only in the logo fill.

| Role          | Hex       |
| ------------- | --------- |
| Primary       | `#62003C` (aubergine — logo fill) |
| Deep variant  | `#3D0025` (used for `<pre>` background) |
| Tint variant  | `#8B3F70` (used for h3 + blockquote rule) |
| Body text     | `#333333` |
| Paper surface | `#F9F5F7` |

## Typography

The site stylesheet declares :

- **Avenir** (`avenir,sans-serif!important`) — body
- **Century Gothic** — used for institutional emphasis

Avenir is a Linotype font (paid licence, not redistributable) ; the
theme falls back to **Avenir Next** / **Open Sans** / **Source
Sans Pro** if Avenir is not available. Century Gothic is a Microsoft
system font with broad availability.

## Wordmark

The official wording is **"Université Paris-Saclay"** (capital U,
lowercase remainder, hyphenated, both `Paris` and `Saclay`
capitalised). The CSS prints it in the footer.

## Usage (Marp slides)

```yaml
---
marp: true
theme: paris-saclay
---

# Slide title
```

## Distribution

Published as an OCI artifact at
`ghcr.io/openweft/weft-loom-theme-paris-saclay:<tag>`. Tool images
consume it via multi-stage `COPY --from=` :

```dockerfile
COPY --from=ghcr.io/openweft/weft-loom-theme-paris-saclay:latest /marp/paris-saclay.css /opt/marp/themes/paris-saclay.css
```

## License

BSD-3-Clause (openweft). The Université Paris-Saclay name + logo
remain the property of the institution ; this repo references the
brand only by colour and typography.

## Cover slide / logo

The theme renders a brand-typography wordmark on `section.lead`
slides ; no institutional logo file is bundled (trademarks remain
the institution's property and aren't redistributable under
BSD-3-Clause).

If you have the right to use the official logotype in your deck,
supply your own image via the `--ups-logo` CSS variable :

```markdown
<!-- _class: lead -->
<!-- _style: "--ups-logo: url(/path/to/your/logo.svg)" -->

# Title here
## Subtitle here
```

Official logo source : https://www.universite-paris-saclay.fr (institutional press contact).
