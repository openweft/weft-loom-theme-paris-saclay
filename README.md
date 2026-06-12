# weft-loom-theme-paris-saclay

`paris-saclay` brand theme for weft-loom compile tooling.

**Signature** : Université Paris-Saclay — chartreuse #84BD00 (PMS 376C) + navy #003C69.

## Usage (Marp slides)

```yaml
---
marp: true
theme: paris-saclay
---

# Slide title
```

The theme is published as an OCI artifact at
`ghcr.io/openweft/weft-loom-theme-paris-saclay:<tag>` and consumed by
the tool images via a multi-stage `COPY --from=` :

```dockerfile
COPY --from=ghcr.io/openweft/weft-loom-theme-paris-saclayatest /marp/ /opt/marp/themes/
```

## Layout

| Path                  | Contents                                  |
| --------------------- | ----------------------------------------- |
| `marp/paris-saclay.css`   | Marp slide stylesheet                     |
| `pandoc/paris-saclay.tex` | pandoc XeLaTeX template (V0.2)            |
| `latex/paris-saclay.sty`  | raw LaTeX style package (V0.2)            |

## Brand integrity

The CSS commits to the institution's published visual identity
guide. Re-brand drift → open a PR with the citation. Logos +
wordmarks remain the property of their owners and are referenced
only by colour + typography, never bundled as image assets.

## License

BSD-3-Clause (openweft).
