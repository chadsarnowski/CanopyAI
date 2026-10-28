# Built to Fix Fragmentation — HTML slideshow

A self-contained web version of `AMD_Marketing_Command_and_Operations.pptx`
(16 slides, Canopy Fest AI 2026).

## Running it

Double-click **index.html** — it opens in any browser and needs no server or
internet connection. To present from another machine, copy this whole folder;
everything it needs is inside it.

To put it on the web, upload the folder as-is to any static host (Netlify drop,
S3, GitHub Pages). There is no build step.

## Controls

| Key | Action |
| --- | --- |
| `→` `↓` `Space` | Next slide |
| `←` `↑` | Previous slide |
| `Home` / `End` | First / last slide |
| `1`–`9` | Jump to that slide |
| `O` | Overview of all 16 slides, click to jump |
| `N` | Speaker notes for the current slide |
| `F` | Fullscreen |
| `P` | Play / pause the video on the slide |
| `?` | Shortcut list |

Swipe left and right on a tablet or phone. The arrows at the left and right
edges do the same thing with a mouse.

Each slide has its own address — `index.html#8` opens straight to slide 8, so
you can link to a single slide.

## What carried over

- All 16 slides, positioned from the original PowerPoint geometry, so spacing
  and alignment match the deck rather than approximating it.
- The eight screen recordings. They were ProRes `.mov` files, which browsers
  cannot play, so they are re-encoded as H.264 `.mp4` in `assets/video/`
  (41 MB of `.mov` became 20 MB of `.mp4`). They autoplay, muted, and loop
  while their slide is up, and reset when you leave it. GIF was the other
  option but would have been several times larger and much blurrier on the
  small UI text in these screens.
- Speaker notes from slides 8 and 15, behind the `N` key.
- The demo links on slides 8, 15 and 16 are live — they open
  amdmarketingcommand.netlify.app and amdoperations.netlify.app in a new tab.

## Fonts

The deck is set in Impact (titles) and Calibri (body).

Calibri ships with Microsoft Office but browsers cannot use it, even on a
machine that has Office installed. **Carlito** is bundled in `assets/fonts/`
instead — a free font with metrics identical to Calibri, character for
character — so every line breaks exactly where PowerPoint breaks it, on any
machine, with no network connection. Every text box renders at its authored
size; nothing is scaled to fit. Carlito is SIL Open Font License 1.1, and the
licence travels with it in `assets/fonts/Carlito-OFL-LICENSE.txt`.

Impact is not bundled — it ships with both macOS and Windows, so the titles are
safe. On a Linux machine without it the headlines fall back to a condensed
sans; install Impact or Anton there if that ever matters.

One deliberate exception: the `LIVE:` row on the last slide is set 6% smaller
than the original so the second URL clears the mascot's hook.

## Printing to PDF

`Cmd-P` → Save as PDF, landscape, margins **None**, and turn on "Print
backgrounds". Each slide prints on its own 13.333 × 7.5 in page. Videos print as
their poster frame.

## Folder layout

```
index.html          the whole slideshow — markup, styles and script in one file
assets/img/         42 images from the deck (logos, icons, mascot, posters)
assets/video/       8 screen recordings, H.264 mp4
assets/fonts/       Carlito (4 weights, woff2) + its licence
```
