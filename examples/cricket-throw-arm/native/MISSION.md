# Mission: Cricket Throw Arm Design and Shape Optimisation

## Why

You want to physically build a manual cricket throw arm and need to know which arm shape actually maximises ball launch speed. Rather than guessing, you want a mathematical model grounded in rotational dynamics so you can compare straight, arc, and spline geometries on the same footing — and then use Python FEA to verify the arm will not yield under the centrifugal loads at release.

## Success looks like

- Given an arm material (Al 6061-T6), cross-section area, and total arc length, you can compute the launch speed for any arm shape (straight line, circular arc, Bezier spline) from first principles.
- You can explain, with numbers, why bending an arm away from straight changes *both* the tip radius and the moment of inertia, and you can predict which direction that trade-off goes.
- You can write a Python FEA solver for a curved beam under centrifugal loading, validate it against an analytical cantilever case, and read off the peak von Mises stress.
- You can run a constrained shape optimisation (scipy SLSQP) that finds the circular arc angle maximising launch speed subject to a stress safety factor of ≥ 1.5, and interpret the result for your build.

## Constraints

- **Held constant throughout:** total arc length L = 0.5 m; circular cross-section of radius r_cs = 8 mm; material Al 6061-T6. Fixing all three pins mass per unit length and keeps comparisons honest.
- **Driving invariant:** fixed input energy E = 50 J (representative of a hard manual swing via a spring-loaded mechanism). Constant-torque and constant-angular-impulse alternatives are noted but not developed here.
- **Cricket ball:** MCC Law 4 spec, mass 155.9–163 g; we use m_ball = 0.1595 kg (midpoint) throughout.
- No aerodynamics (drag, spin) — arm mechanics only.
- Python tools: numpy, scipy, matplotlib only (no external FEA package).

## Out of scope

- Release-angle optimisation (assume the arm releases the ball at its natural apex).
- Dynamic simulation of the driving mechanism (spring, rubber, human torque profile).
- Manufacturing or material-joining details.
- Aerodynamic flight path of the ball after release.
