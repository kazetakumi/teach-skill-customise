# Mission

## The Build Target

Design and numerically optimise the centerline geometry of a **manual cricket throw arm** — a pivoting lever arm that a person swings to project a cricket ball — and produce a Python FEA pipeline that:

1. Takes any arm centerline shape (straight line, circular arc, cubic Bézier spline).
2. Computes the **ball release speed** from first-principles rigid-body energy analysis.
3. Computes the **maximum von Mises stress** in the arm at release using a 2D frame FEA model.
4. Finds the shape that **maximises ball speed subject to a no-failure constraint** (σ_max ≤ σ_yield).

This is a build-to-learn project. Each lesson adds one working piece of that pipeline.

---

## Physical Setup

| Parameter | Value | Source |
|-----------|-------|--------|
| Arm arc length S | 0.80 m (fixed for all shapes) | design choice |
| Cross-section | Solid circle, r = 20 mm → A = 1.257×10⁻³ m² | design choice |
| Second moment (bending) | I_sec = πr⁴/4 = 1.257×10⁻⁷ m⁴ | geometry |
| Material | 6061-T6 aluminium alloy | standard |
| Young's modulus E | 69 GPa | ASM handbook |
| Density ρ | 2700 kg/m³ | ASM handbook |
| Yield strength σ_y | 276 MPa | ASM handbook |
| Cricket ball mass m_b | 0.163 kg | MCC Law 4.1 |
| Human input energy E_in | 80 J | biomechanics estimate |

**Invariants across all shapes:** arc length S, cross-section geometry, material.
Changing the shape changes: the moment of inertia I_arm, the effective radius R_eff, and the stress distribution — everything else is the same.

---

## Governing Physics (Overview)

### Speed model (rigid-body, energy-based)

The arm + ball system starts from rest and receives energy E_in from the thrower.
At the moment of release the arm has angular velocity ω; the ball speed is:

> v = R_eff · ω,   where  ½(I_arm + m_b · R_eff²)·ω² = E_in

This gives:

> **v = R_eff · √( 2·E_in / (I_arm + m_b·R_eff²) )**

R_eff is the straight-line distance from the pivot to the ball (tip of the arm).
For a straight arm R_eff = S; for any curve R_eff < S (chord < arc length).
The optimum shape balances losing R_eff (curve reduces it) against potentially losing less inertia I_arm.

### Failure model (FEA, 2D frame)

At release the arm spins at ω. Every element experiences centrifugal body force ρAω²r(s) directed radially outward (away from pivot). The arm is clamped at the pivot (fixed–free). We discretise the centerline into 2D Euler-Bernoulli frame elements (DOF per node: u_x, u_y, θ), assemble the global stiffness matrix K and centrifugal load vector F, solve K·u = F for displacements, recover element stresses, and report max von Mises stress.

**Assumed simplifications named explicitly:**
- Rigid-body energy model decoupled from elastic FEA model (arm treated as rigid when computing ω, elastic when computing stress).
- Arm stays in its plane of rotation (in-plane deformation only).
- Static equilibrium at the peak ω; angular acceleration neglected at the moment of release.
- No dynamic buckling, no material non-linearity.

---

## The Five Lessons

| Lesson | Concept | Build piece |
|--------|---------|-------------|
| 1 | North Star: full pipeline overview | Run all three shapes → speed + stress comparison |
| 2 | Rigid-body energy model | Derive I_arm(shape), v(shape); plot speed vs bend angle |
| 3 | Stress in a spinning curved arm | Centrifugal load distribution; analytical straight-arm check |
| 4 | FEA from scratch: 2D frame element | Build K-matrix, assemble, solve, verify on cantilever |
| 5 | Shape optimisation | Maximise v s.t. σ_max ≤ σ_y using scipy + FEA |
