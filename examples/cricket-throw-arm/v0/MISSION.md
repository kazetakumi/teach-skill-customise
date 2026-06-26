# Mission: Cricket Throw Arm — Design, Analysis, and Optimisation

## The Goal

Design a manual cricket throw arm that maximises ball release speed while ensuring the arm does not fail structurally. Use a rigorous mathematical model and Python-based FEA to understand the design space.

## Specific Questions to Answer

1. **How does planform geometry affect ball speed?** For a fixed arm arc length L, fixed cross-section area A, and fixed material, how do straight-line, circular-arc, and spline shapes change the achievable ball speed? *Held fixed: total arc length L, cross-section area A, material (steel), energy input W.*

2. **What is the structural failure mode?** Under what loading does the arm fail, and how does the maximum achievable speed relate to the yield stress of the material?

3. **How does FEA predict stress for complex shapes?** Implement Euler-Bernoulli beam FEA from scratch in Python and use it to compute stress distributions for arbitrary arm geometries.

4. **What is the optimal arm design?** Optimise the arm's cross-section profile (taper from root to tip) to maximise ball speed subject to a yield-stress constraint at every cross-section.

## The Core Trade-off

The rigid-body kinematic result is definitive: **a straight arm maximises ball speed for a given arc length, input energy, and cross-section**. This is because the straight arm simultaneously maximises the effective radius r_ball and maximises the performance index r_ball² / I.

The interesting design problem arises from structural constraints: for the same torque (which sets the root bending stress σ = τ/Z), a tapered arm (large cross-section at root, smaller at tip) achieves *higher angular velocity* for the *same root stress* than a uniform arm. The optimisation in Lesson 5 finds this optimal taper.

## Engineering Context

| Parameter | Value | Source |
|-----------|-------|--------|
| Cricket ball mass | 163 g | ICC regulation |
| Target release speed | 30–35 m/s | Competitive batting-practice speed |
| Arm material | Mild steel (A36) | Common, off-the-shelf |
| Yield stress σ_y | 250 MPa | A36 steel |
| Young's modulus E | 200 GPa | Steel |
| Density ρ | 7 850 kg/m³ | Steel |

## Lesson Sequence

| Lesson | Title | Core Skill |
|--------|-------|-----------|
| 0001 | Rigid Body Dynamics — The Rotating Lever | Translate torque → ω → v_ball for a uniform straight arm |
| 0002 | Shape Effects on Moment of Inertia | Show analytically and numerically why straight maximises v |
| 0003 | Structural Loading and Bending Stress | Compute bending moment diagram and yield-check the arm |
| 0004 | Euler-Bernoulli FEA from Scratch | Assemble global stiffness, validate against cantilever benchmark |
| 0005 | Shape Optimisation for Maximum Speed | Optimise taper profile via scipy; Pareto front speed vs safety |

## Fixed Comparison Basis (to avoid ambiguity)

- **Fixed**: total arc length L = 0.80 m, cross-section area A = 5 × 10⁻⁴ m², steel material.
- **Drive model**: constant torque τ over swing angle θ = π/2 radians. Energy W = τ θ.
- **Metric**: ball release speed v_ball = ω × r_ball where r_ball = end-to-end chord from pivot.
- **Failure criterion**: bending stress at any cross-section ≤ σ_y / SF (safety factor SF = 1.5).
