# Life Landscape

An authoring tool for sculpting 3D "life landscapes" — surfaces of **ridges and
valleys** that you can draw paths on and label. It's meant as a visual metaphor
for moving through life: choices are passes, habits are valleys, and some pulls
(a cult, an addiction, a calling) are deep **basins of attraction** ringed by a
rim you have to climb to escape.

## Run it

Just open `index.html` in any modern browser — double-click it, no install or
build step. Three.js loads from a pinned CDN, so the first open needs an
internet connection; after that the browser caches it.

> If you'd rather serve it locally: `python3 -m http.server` in this folder,
> then visit the printed URL.

## The idea

The terrain is a height field `y = f(x, z)` built from simple analytic
primitives. This keeps the metaphor honest:

- **Valley** — a Gaussian dip. A basin you settle into.
- **Ridge** — a Gaussian bump. A barrier between places.
- **Basin** — a deep central pull *plus a ring-shaped rim*. The rim is the
  **activation energy** required to leave. This is the "strange attractor" shape:
  easy to fall in, costly to climb out.
- **Saddle** — a mountain pass. The point of choice between two valleys.

On top of the surface you can:

- **Draw paths** — a trajectory of a life across the terrain.
- **Drop a marble** — it rolls down the gradient (with friction) and settles in
  whatever basin captures it. A quick, visceral way to feel an attractor.
- **Label** every feature and path.

## Controls

| Action | How |
| --- | --- |
| Orbit / zoom / pan | drag · scroll · right-drag |
| Place a feature | pick a tool, click the surface |
| Move a feature | in Orbit mode, drag its colored handle |
| Tune a feature | select it, use the sliders |
| Draw a path | Draw Path tool, click points, double-click / Enter to finish (Esc cancels) |
| Delete | select, then Delete/Backspace, or the delete button |

## Saving your work

- The scene **autosaves** to your browser's local storage.
- **Save JSON** downloads the scene; **Load JSON** restores it. Keep these
  alongside the essay so the landscapes travel with it.
- **Export PNG** grabs the current view for embedding.

## Notes

This is a v1. Natural next steps if you want them: gradient-descent paths that
auto-trace downhill, anisotropic / rotatable features, contour shading, multiple
marbles, and an "annotation" mode for free-floating text in 3D.
