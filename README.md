# Curve Range

A shooting-range trainer for the **Curves & Surfaces** chapter of CS 451 Computer Graphics (Taibah University).
The levels follow the lecture slides in order. Each formula and rule is a weapon: the coach teaches it step by step,
then you shoot the right formula pieces, values and answers as they cross the range.

## Levels (slide order)

| # | Level | Slides | What you shoot |
|---|---|---|---|
| 1 | Introduction | 3-10 | Why curves, geometry, implicit / explicit / parametric, polynomials |
| 2 | Smooth curves | 12-13 | The seven needs, polylines against higher-order curves |
| 3 | Representations | 14-17 | Pros and cons of implicit, explicit and parametric, and which task suits which |
| 4 | Parametric curves | 18-21 | The parameter t in [0, 1], why cubics, degrees 1, 2, 3 |
| 5 | Specifying curves | 22-24 | Control points, interpolation vs approximation, piecewise curves |
| 6 | Continuity | 25-28 | G0, G1, C0, C1, C2, classify a join |
| 7 | General cubic form | 29-32 | X(t) = a3 t^3 + ..., T.C = T.M.G, Hermite / Bezier / splines / NURBS |
| 8 | Hermite curves | 33-43 | Coefficients, M_H, blending functions, the mid-point example |
| 9 | Bezier curves | 44-54 | Weights, M_B, convex hull, joining curves, the table example |
| 10 | Meshes and implicit surfaces | 56-65 | Polygon meshes, quadrics, metaballs |
| 11 | Bicubic patches | 66-75 | Q(s, t) = t^T.M.q.M^T.s, continuity, normals, tessellation |
| 12 | Recap | 77-81 | The quick recap |
| * | Whole chapter | all | one problem from each level, in order |

## How to play

1. **Armory**: the wall of formulas for the chosen level.
2. **Trainer**: the coach walks through the slides of that level (88 steps in total) with worked examples, figures and tables.
   Explorers let you drag things: a point moving along a parametric curve, a cubic, the Hermite and Bezier control points,
   the de Casteljau construction and a metaball blob.
3. **Range**: shoot.
   - Method levels build the formula pieces in order, then calculate something (a cubic value, Hermite coefficients,
     blending weights, a Hermite or Bezier point, a join, a surface normal). All numbers are random.
   - Cover the wall for double points. Every wrong shot gets a reason from the coach.
4. A level gets a tick when a run reaches 70% accuracy. The end screen names your weakest level and offers the next one.

Progress is saved in the browser (localStorage).

## Notes on the slides

- Hermite example (slide 42): P0 (1,1), P1 (6,5), P'0 (0,4), P'1 (4,0) gives the mid-point (3, 3.5).
- Bezier example (slide 52): P0 (2,2), P1 (2,3), P2 (3,3), P3 (3,2) gives X = 2, 2.15625, 2.5, 2.84375, 3 and Y = 2, 2.5625, 2.75, 2.5625, 2
  at t = 0, 0.25, 0.5, 0.75, 1. The slide shows the values rounded.
- Bezier join (slide 49): the slide prints P2 - P3. The game teaches P3 - P2 = k (Q1 - Q0) with k > 0, which is the form that makes the
  tangent directions match.
- Bonus: the Bezier end tangents are p'0 = 3 (p1 - p0) and p'1 = 3 (p3 - p2). They are not on the slides but follow from M_B, and they
  explain why p1 and p2 control the tangents.
- Quadric sphere (slide 60): the slide prints x^2 + y^2 + z^2 = 0. The sphere of radius r is x^2 + y^2 + z^2 - r^2 = 0.
- Brute-force patch evaluation (slide 72): the slide quotes 20,000 evaluations for a step of 0.01.

## Run it

One static file. Open `index.html` in a browser, or host it with GitHub Pages
(Settings > Pages > Deploy from a branch > `main` / root).
