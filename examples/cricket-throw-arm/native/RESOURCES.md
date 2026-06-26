# Cricket Throw Arm Design Resources

## Knowledge

- [MCC Law 4: The Ball — lords.org](https://www.lords.org/mcc/the-laws/the-ball)  
  The legislative source for cricket ball mass: 155.9–163 g (5.5–5.75 oz). Use whenever you need to anchor the ball mass parameter.

- [Euler–Bernoulli Beam Theory — Wikipedia](https://en.wikipedia.org/wiki/Euler%E2%80%93Bernoulli_beam_theory)  
  Comprehensive derivation of M/I = σ/y = E/R; covers bending equation, deflection formulae, and model assumptions. Use for straight-beam mechanics and FEA element derivation.

- [Bending of Curved Beams (Winkler-Bach) — NPTEL IIT lecture notes](https://archive.nptel.ac.in/content/storage2/courses/105106049/lecnotes/mainch10.html)  
  Derives the hyperbolic Winkler-Bach stress distribution for initially curved beams, including neutral-axis shift. Use whenever the arm's radius of curvature is comparable to the cross-section depth.

- [Moment of Inertia Derivations — R. Fitzpatrick, UT Austin Physics](https://farside.ph.utexas.edu/teaching/301/lectures/node103.html)  
  General integral derivation for moment of inertia; backbone for computing I for the circular-arc arm analytically. Use to verify numerical integrals.

- [Moment of Inertia — HyperPhysics (Georgia State University)](http://hyperphysics.phy-astr.gsu.edu/hbase/mi2.html)  
  Tabulated formulas: straight rod I = mL²/3, ring I = mR². The limiting-case checks for the arc formula live here.

- [6061 Aluminium Alloy — Wikipedia](https://en.wikipedia.org/wiki/6061_aluminium_alloy)  
  Full property table for Al 6061-T6: E = 68.9 GPa, σ_y = 276 MPa, ρ = 2700 kg/m³. Use as citable baseline; cross-reference ASM/ASTM for production design.

- [Al 6061-T6 Properties — The World Material](https://www.theworldmaterial.com/al-6061-t6-aluminum-alloy/)  
  Tabulated mechanical properties in engineering-design format. Use to cross-check Wikipedia values.

- [scipy.optimize.minimize (SLSQP) — SciPy v1.18 Docs](https://docs.scipy.org/doc/scipy/reference/optimize.minimize-slsqp.html)  
  Official reference for the SLSQP constrained minimiser: constraint dict format, bounds, callback. Use when writing the shape optimisation in Lesson 5.

- [Robowler: Design of a Cricket Bowling Machine — Raza, Diegel & Arif (2014)](https://link.springer.com/content/pdf/10.1007/s11771-014-2409-2.pdf)  
  Peer-reviewed paper (doi:10.1007/s11771-014-2409-2) on a robotic arm bowling machine; covers arm kinematics, actuator selection, and release mechanics. The closest published reference to this design problem.

## Wisdom (Communities)

- [r/AskEngineering — Reddit](https://www.reddit.com/r/AskEngineering/)  
  Moderated engineering Q&A; useful for sanity-checking the FEA approach and asking about practical arm construction trade-offs.

- [Finite Element Analysis — Engineering Stack Exchange](https://engineering.stackexchange.com/questions/tagged/finite-element-method)  
  Tagged FEA questions; a good place to ask about Python-based beam element implementation choices.

## Gaps

- No freely accessible peer-reviewed source found specifically covering *manual* throw arm optimisation for cricket. The Robowler paper covers motorised designs. This is a genuine modelling gap — be explicit in lessons that the kinematic model is derived from first principles, not lifted from a cricket-specific reference.
