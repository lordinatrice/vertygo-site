# Vertygo Aerial: website

The landing page for Vertygo Aerial, small-group aerial retreats.
Static site built with Jekyll, hosted on GitHub Pages. No JavaScript.

## Run it locally

```sh
bundle install
bundle exec jekyll serve      # http://localhost:4000
```

## Where things live

| What | Where |
| --- | --- |
| Every piece of copy | `_data/locales/en.yml` |
| The page, one include per section | `_includes/sections/` |
| Header, footer, logo, photo helper | `_includes/` |
| Brand colours and styles | `assets/css/main.css` (tokens at the top) |
| Photos | `assets/images/photos/` |
| Survey and Instagram links | `_config.yml` |

## Photos

Each slot shows `assets/images/photos/<name>.jpg`. If a file is missing, a coloured
shape with the alt text is shown instead.

| File | Section |
| --- | --- |
| `hero.jpg` | Hero, big arch (portrait) |
| `detail.jpg` | Hero, small card |
| `studio.jpg` | Community, arch (portrait) |
| `group.jpg` | Community, circle (square) |
| `river.jpg` | Beyond the studio, arch (portrait) |
| `wildlife.jpg` | Beyond the studio, circle (square) |
| `india.jpg`, `georgia.jpg`, `thailand.jpg`, `france.jpg` | Where next (portrait 3:4) |
| `camilla.jpg` | Meet Camilla (portrait 4:5) |

Replace a file with the same name to change a photo, and update its alt text in
`_data/locales/en.yml`. Keep photos around 1400 px on the long side, JPEG at 80% quality, with location
metadata (EXIF) removed since the repository is public.

The portrait is an arch. For a circle, swap `shape-arch` for `shape-circle` in
`_includes/sections/meet-camilla.html`.

## Languages

English only for now, ready for more. For French:

1. Copy `_data/locales/en.yml` to `fr.yml` and translate the values.
2. Copy `index.html` to `fr/index.html` and set `lang: fr` and `permalink: /fr/` in its front matter.

## Accessibility

- Semantic landmarks, one `h1`, a heading per section, `lang` on `<html>`.
- A "Skip to content" link and visible keyboard focus.
- Alt text on every photo, decorative SVGs hidden from screen readers.
- Text contrast is AA or better on every background (8.6:1 for body text on pastels).
- Smooth scrolling only when the visitor allows motion.
