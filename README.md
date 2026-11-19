# sketchbox

A home for small web experiments. The root `index.html` links to each one, and every experiment lives in its own folder as a self-contained page.

| Experiment | Folder | Status |
| --- | --- | --- |
| grid toy | `grid-toy/` | live |
| micro write | `micro-write/` | placeholder |
| micro sheet | `micro-sheet/` | placeholder |
| micro draw | `micro-draw/` | placeholder |

## Adding an experiment

1. Make a folder with an `index.html` in it.
2. Add a line for it to the list in the root `index.html`.

## Hosting

No build step, so GitHub Pages can serve it as is: Settings → Pages → Source "Deploy from a branch", branch `main`, folder `/ (root)`. The site then appears at `https://lumoconnor.github.io/sketchbox/`.
