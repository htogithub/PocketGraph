# PocketGraph

A graphing calculator and math visualizer that runs entirely in the browser. It is built for both phones and computers, and opens as a standalone app when added to the iPhone home screen.

## Features

### Functions and curves
- Function graphs `y = f(x)` and `x = g(y)`, named functions `f(x) = ...` with derivatives `f'(x)` and `f''(x)`
- Implicit curves such as `x^2 + y^2 = 9` and shaded inequalities such as `y < 2x + 1`
- Polar curves `r = f(θ)`, parametric curves `(x(t), y(t))` and points
- Sliders created in one tap for any undefined variable, with play/pause animation
- Points whose coordinates are sliders can be dragged on the graph
- Tapping a curve traces it and shows its roots, extrema, y-intercept and intersections

### Sequences and series
- Explicit `u(n) = ...` or recursive `u(n+1) = ...` sequences, including second-order recursions such as Fibonacci
- Partial sums, cobweb plot, table of values and limit estimate

### Linear algebra
- Matrix card up to 6 × 6: rank, determinant, trace, characteristic polynomial, eigenvalues and eigenvectors, inverse and reduced row echelon form, shown as exact fractions when possible
- 2 × 2 matrices are shown as an animated transformation of the plane, and the images of the basis vectors can be dragged to edit the matrix
- 3 × 3 matrices are shown as a transformed cube in the 3D view
- Matrix expressions: `A v`, `A^-1`, `A^T`, `det`, `inv`, `rank`, `rref`, `eig`, `solve(A, b)`, `dot`, `cross`, `norm`

### Differential equations
- First-order `y' = f(x, y)` with slope field, and second-order `y'' = f(x, y, y')`
- Draggable initial conditions, RK4 or Euler method with adjustable step
- Dynamical systems `x' = f(x, y, t)`, `y' = g(x, y, t)` with vector field and phase portrait, and three-dimensional systems with `z'`

### 3D view
- Surfaces `z = f(x, y)` and implicit surfaces such as `x^2 + y^2 + z^2 = 9`
- Space curves `(x(t), y(t), z(t))`, 3D points and vectors
- 3D trajectories and vector fields, for example the Lorenz attractor
- Drag to rotate, pinch or scroll to zoom

### Calculations
- Sums `sum(1/k^2, k, 1, n)`, products `prod(...)`, integrals `int(f(t), t, 0, inf)` and numerical derivatives `deriv(x^3, x)`
- Implicit multiplication (`2x`, `sin x`, `xy`), `√`, `|x|`, `n!`, `binom`, `mod`, French notations `sh`, `ch`, `th`, `arcsin`

### Interface
- Side panel on computers, sliding bottom sheet on phones
- Built-in math keypad on touch screens (numbers, functions, QWERTZ letters), with a switch to the system keyboard
- Undo and redo, fourteen built-in examples and a syntax guide
- Export the graph as PNG or JSON, import a JSON graph
- Five themes (Tracing, Graph paper, Slate, Chalk, Night) plus automatic light/dark, eight accent colours or a custom one, three fonts, adjustable curve thickness, line, dot or no grid, π ticks
- Interface in French, English and German
- Everything is saved automatically in the browser

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole app: markup, styles and code in a single file |
| `manifest.webmanifest` | Lets the app open in standalone mode from the home screen |
| `apple-touch-icon.png` | Home screen icon on iPhone |
| `icon-192.png`, `icon-512.png` | App icons for other platforms |

## Hosting on GitHub Pages

1. Upload the five files to the root of the repository.
2. In the repository settings, open Pages and choose to deploy from the main branch, root folder.
3. Open the published address in Safari on the iPhone, tap Share, then Add to Home Screen.

No build step and no dependencies are needed. Fonts are loaded from Google Fonts when online, with system fonts as a fallback.

## Technical notes

- The expression engine (tokenizer, parser, dependency resolution between definitions, compilation to JavaScript functions) is written from scratch.
- Linear algebra uses LU and Gauss–Jordan elimination, the Faddeev–LeVerrier method for the characteristic polynomial and Durand–Kerner for its roots.
- Integrals use tanh-sinh quadrature, which handles singular endpoints and infinite bounds.
- Implicit curves use marching squares, implicit surfaces use marching tetrahedra, and the 3D view uses perspective projection with depth sorting.
