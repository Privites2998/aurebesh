# Aurebesh Sign Generator

A browser-based generator for Star Wars–style signage rendered in Aurebesh. Single self-contained HTML file, no build step, no dependencies, no font upload required — every letter is a hand-traced SVG path baked into the page.

**Live preview**: open `index.html` in any modern browser.

## What it does

Type your text, pick a sign style, export. Live preview updates as you type.

### Sign styles

- **News ticker (HoloNet)** — wide horizontal bar with brand block, scrolling text, live indicator
- **Restricted door panel** — industrial portrait sign with octagonal corners, red status band, screws
- **Hazard / warning panel** — yellow + black diagonal stripes, hazard triangle, hex bolts
- **Directional sign** — chevron arrow + destination text + distance pill
- **Shop signage (neon)** — pink + cyan glow, double frame, status pill
- **Ship registry plate** — brushed metallic gradient, stamped text, six hex bolts
- **Holo-display caption** — cyan glow, scanlines, glitch artifacts, corner brackets
- **Alphabet chart** — every glyph in a labeled grid (also serves as a font specimen)

### Exports

- **SVG** (vector, fully portable)
- **PNG** (2× rasterized for sharpness)
- **Clipboard PNG copy** (Chromium browsers)

## The font

All 42 glyphs (26 letters A–Z, 10 digits 0–9, six punctuation marks `- / . , : !`) are defined as inline SVG `<path>` data with `fill-rule="evenodd"`. Each glyph fits in a 100×100 unit box with cap height ~85. The dictionary lives in the `GLYPHS` object near the top of the script in `index.html` — swap any path string to redesign a single letter.

Shapes are hand-traced from a canonical Aurebesh chart. Letters K, S, V, W, X, Y are the least canon-accurate and are first candidates for refinement.

## Not yet included

- Digraphs (Ch, Ae, Eo, Kh, Ng, Oo, Sh, Th) and the credits symbol
- Question mark, semicolon, parentheses, quote marks
- Word/glyph-bbox-based auto-fit (current fit estimate is character-count-based)

## Why no font file?

A bundled `.ttf` would mean dragging in a licensed font (or building a full OpenType file). The path-dictionary approach keeps the project royalty-free, makes SVG/PNG exports fully self-contained, and lets the user (you) iterate on any single letter by editing one path string.

## Files

```
index.html       — the entire app (HTML + CSS + JS + glyph paths)
README.md        — this file
LICENSE          — MIT
.gitignore       — macOS / editor noise
```

## License

MIT — see `LICENSE`.
