# TextFlora

A type generator where stems and roses grow out of the letters as you type. built as a single self-contained HTML file: canvas and plain JavaScript, no build step, no dependencies.

## Run it

Open `textflora.html` in any modern browser. Fonts load from Google Fonts, so you need to be online the first time:

- **Playfair Display Bold** for the letters (stands in for the original GT Ultra Fine, which is commercial)
- **DM Mono** for the interface

## Controls

| Action | What it does |
| --- | --- |
| Type | Letters grow stems, leaves and roses |
| Space | Cuts the stems, so the next word grows a new garden |
| Backspace | Withers the last letter |
| Enter | Clears everything |
| Click / tap the garden | A butterfly flies in and lands on a bloomed rose |
| Double-click / double-tap | Plants a rose that fades after a minute (local to your screen) |
| Palette dots | Switch between the 10 palettes |
| PNG / SVG | Export the current garden (Ctrl/Cmd+S saves PNG) |

On phones, tap the garden to bring up the keyboard.

Roses and letters lean toward your pointer.

## Poster mode

Use the **Type / Poster** toggle at the top right. Enter your words, pick a motion and a palette, then export a 1080 × 1080 loop at 30 fps.

- **Motions:** Breathe, Grow & wither, Typed, Gust, Scatter
- **Export:** MP4 or WebM loop (depends on browser support), or PNG frames as a `.zip`
- **Regrow garden** reseeds the flowers for the same words

## Palettes

Rose noir, Paper, Midnight, Citrus, Orchid, Moss, Tomato, Butter, Blush, Mono. Each is one row in the `PAL` array: name, background, flower, stem and leaf, flower line, type colour.

## Making it yours

Everything lives in `type-garden.html`:

- **Palette:** edit or add rows in `PAL`.
- **Typeface:** change the `F` constant and the Google Fonts `<link>`.
- **Density, boil, recoil:** the `OPT` object near the top (`density` scales how many leaves and bridges grow, `boil` toggles the line jitter, `recoil` sets how far a cut stem snaps back).
- **Flowers:** `rose()` draws the bloom, `leaf()` the leaves, and `grow()` decides which tip each stem gets (rose, fan, leaf or curl).
- **Motion:** `spr()` is the spring used for blooming, and the preset behaviours are inside `posterDraw()`.

## Differences from the original

- Letters use Playfair Display Bold instead of GT Ultra Fine.
- SVG export saves letters as live text, not outlines, so it needs the font installed to look the same elsewhere.
- No multiplayer: no other gardeners' cursors, and planted roses stay on your screen.
- Poster mode has five of the original seven motions (Reach and Visitor are not included).


