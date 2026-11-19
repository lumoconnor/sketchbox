# sketchbox

A home for small web experiments. The root `index.html` links to each one, and every experiment lives in its own folder as a self-contained page.

| Experiment | Folder | Status |
| --- | --- | --- |
| grid toy | `grid-toy/` | live |
| micro write | `micro-write/` | live |
| micro sheet | `micro-sheet/` | live |
| micro paint | `micro-draw/` | live |

## micro office

micro write, micro sheet and micro paint are a tiny suite of minimal office-style apps. Plain HTML, CSS and JS, no build step.

- `shared/micro.css`: the shared look, pasted inline into each app's `<style>` so every page stays self-contained (keep them in sync) (serif type, narrow column, light/dark, fading toolbar, quiet footer).
- `micro-write/`: **micro write**, a word processor. `micro-write/juicy.html` is a livelier variant.

## micro write shortcuts

| Action | Keys | Or type |
|---|---|---|
| Bold / italic | Ctrl/Cmd+B, Ctrl/Cmd+I | |
| Body text | Ctrl/Cmd+Alt+0 | |
| Heading 1 / 2 | Ctrl/Cmd+Alt+1, Ctrl/Cmd+Alt+2 | `# ` / `## ` |
| Bullet list | Ctrl/Cmd+L | `- ` |
| Save .md / .html | Ctrl/Cmd+S, Ctrl/Cmd+Shift+S | |
| Open .md or .html | Ctrl/Cmd+O | |
| Print / PDF | Ctrl/Cmd+P | |

The document autosaves to the browser's localStorage. Pasting brings in plain text only.
- `micro-sheet/`: **micro sheet**, a spreadsheet.
- `micro-draw/`: **micro paint**, a drawing app.

## micro sheet

Type in a cell and press Enter (down) or Tab (right). Arrows move, Enter or F2 edits the current cell, Escape cancels, Delete clears. On touch, tap a cell to select it and tap again to edit.

Formulas start with `=`: `+ - * /`, brackets, cell references like `B3`, and `SUM`, `AVG`, `MIN`, `MAX`, `COUNT` over ranges like `A1:A9` or lists like `SUM(A1, B2, 5)`. Errors show as `#ERR`, `#VALUE`, `#DIV/0` or `#CYCLE`.

| Action | Keys |
|---|---|
| Save .csv | Ctrl/Cmd+S |
| Open .csv | Ctrl/Cmd+O |
| Undo / redo | Ctrl/Cmd+Z, Ctrl/Cmd+Y |
| Copy / paste | Ctrl/Cmd+C, Ctrl/Cmd+V (pasting a block from another spreadsheet fills several cells) |

CSV saves formulas as typed, so they come back when reopened. The sheet autosaves to localStorage.

## micro paint

Draw with a mouse, finger or stylus such as the Apple Pencil.

On touch screens:
- Tap with two fingers to undo, three to redo.
- Once a stylus has drawn, a single finger no longer draws (reload to draw with a finger again). A contact as wide as a palm never draws, and if a palm or finger is mid-stroke when the stylus lands, that stroke is wiped.
- On an iPad Pro, a ring shows where the Pencil will land while it hovers.

Tools:
- **ink**: a fine liner with a near-even line. Direction, pressure and speed change the width only by a hair (the `vary` setting, 0.08), and a quick lift ends in a short point. Slow, careful lines are steadied so they stay straight; fast scribbling passes through untouched, for colouring in.
- **eraser**: rubs ink away, back to the paper.

Pick one of ten colours. The rainbow swatch (or R) deals a new palette and paper: a harmony of hues with two darks, a muted tone, five mids and two lights, on a near-neutral paper (now and then a dark one). Changing the paper doesn't touch the drawing, because ink sits on a clear layer above it. Clear asks for a second click. Open accepts any image, or drop one on the page; it saves as .png on the current paper.

| Action | Keys |
|---|---|
| Ink / eraser | I / E |
| New colours and paper | R |
| Undo / redo | Ctrl/Cmd+Z, Ctrl/Cmd+Y |
| Save .png | Ctrl/Cmd+S |
| Open image | Ctrl/Cmd+O |

Pictures are drawn at 2× screen resolution, so the canvas is 2400 × 1600 unless you open a larger or smaller image (up to 4096 px). The picture autosaves to localStorage. Tools live in the `TOOLS` object in `micro-draw/index.html`: each has `add` (take a point), `draw` (paint the stroke so far) and optional `idle` (pen resting).

## Adding an experiment

1. Make a folder with an `index.html` in it.
2. Add a line for it to the list in the root `index.html`.

## Hosting

No build step, so GitHub Pages can serve it as is: Settings → Pages → Source "Deploy from a branch", branch `main`, folder `/ (root)`. The site then appears at `https://lumoconnor.github.io/sketchbox/`.
