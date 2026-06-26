# PERSONAL LEARNING FRAMEWORK
---

## 1. CORE PHILOSOPHY: "See the Mechanism, Then Build It"

**Understanding = Visual Intuition + First-Principles Construction + Retrieval Practice**

Every concept must pass through three gates:
1. **Visual Gate**: Can I draw/animate the mechanism? (3B1B)
2. **Construction Gate**: Can I build it from scratch without APIs? (Karpathy)
3. **Teaching Gate**: Can I explain it to a beginner in plain language? (Feynman)


If any gate fails, understanding is fragile.

**Golden Rule**: If you cannot visualize the transformation, draw the block diagram, and code it from basic arrays or from `torch.Tensor` (or `numpy.ndarray`) and basic operations, you do not understand it.

---

## 2. SYSTEM 1 vs SYSTEM 2 AWARENESS

| Phase | Goal | Method |
|-------|------|--------|
| **System 2 (Deliberate)** | Build rigorous mental models | Slow, step-by-step derivations, explicit shape tracking, print every tensor |
| **System 1 (Intuitive)** | Make pattern recognition automatic | Spaced retrieval, interleaved practice, visual mnemonics |

**Never skip System 2 to reach System 1.** Intuition without rigor is superstition. Rigor without intuition is brittle. Example: The learner must *feel* the shape of every tensor, *see* the flow of every gradient, and *debug* every failure mode before reaching for the "easy" solution.

---

## 3. THE LEARNING WORKFLOW

### Stage 0: The Intuition (3B1B Style)
- **Animate before calculate.** Draw the domain. Show what changes and why.
- **Block diagrams over equations.** Equations are compressed code; diagrams are the source.
- **Motivate the failure.** Why do naive methods break? What does "good" look like?
- **Dimensional analysis first.** Identify the dimensionless knobs (e.g., $mL$, Biot number, Fourier number) before touching code.

### Stage 1: The Naive Build (Karpathy Style)
- **No boilerplate frameworks.** Imports are `torch`, `numpy`, `matplotlib`. Maybe `scipy` for validation only.
- **Seed everything.** `torch.manual_seed(42)`, `np.random.seed(42)`. Reproducibility is a feature, not an afterthought.
- **Print shapes immediately.** After every tensor operation, print `.shape` until the learner internalizes the dimensionality.
- **Do not optimize prematurely.** Let the naive version fail or underperform. This creates the "problem" that the next section solves.
- **Run it and diagnose.** Plot the loss curves, the predictions, the residuals. The learner must *see* the hockey-stick loss, the boundary drift, the oscillatory residuals.
- **Narrate the failure.** "Look at this - the boundary error is 3 degrees. That is unacceptable for engineering. Why is this happening? Let us investigate..."

### Stage 2: The Diagnosis (The "Health Check")
Before fixing, decompose:
- **Component analysis**: Break the problem into parts. Which part dominates the error?
- **Activation/State health**: Track distributions, saturation, dead regions.
- **Gradient/Update health**: Are updates vanishing? Exploding? Is the step size ~1e-3 of parameter std?
- **Spatial/Temporal bias**: Where does the error live? Boundaries? Corners? Early time?
- **Loss landscape**: Log-scale plots. Monotonic decrease? Plateaus? Hockey sticks?

### Stage 3: The Fix (One Change, One Lesson)
- Introduce exactly one technique per session.
- Re-run all diagnostics. Side-by-side before/after.
- Quantify the delta. Did boundary error drop? Did convergence speed up? What is the distribution of the errors now? Compare to previous run.
- Repeat until the problem is solved.

### Stage 4: The Abstraction (The Reward)
- Only after raw construction is owned, introduce the library abstraction.
- The abstraction is not the lesson; it is the reward for understanding the lesson.

### Stage 5: The Feynman Compression
- Write the explanation you wish you had read before starting.
- Use analogies, not jargon. Every symbol must map to a physical picture.
- If stuck, explain it to a rubber duck (or a child).

### Stage 6: The Retrieval (Make It Stick)
- **Desirable difficulty**: Exercises should feel slightly too hard, not comfortably easy.
- **Interleaving**: Mix this topic with prior topics in practice sessions.
- **Spacing**: Revisit this notebook in 1 day, 3 days, 7 days.
- **Self-testing**: Close the notebook. Rebuild from memory. Check against reference.

---

## 4. NOTEBOOK STRUCTURE TEMPLATE

```markdown
# Lesson N: [Descriptive Title] — [Core Concept]
## [Engaging Subtitle]

**Welcome back!** In Part N-1, we [recap previous achievement]. Today we [build on that by introducing new concept].

**The problem:** [Physical scenario with equations].
**Why this matters:** [Engineering motivation].
**What we will build:** [Specific network/approach].

## 1. The Problem - "Physics Setup"
- Visual/block diagram of the mechanism.
- Governing equation with LaTeX.
- Boundary conditions with diagrams 
- Analytical solution (if available) plotted for validation.
- Parameter definitions with units.
- Animate or plot the target behavior before any code.
- Motivation: why does this matter? What fails without it?


## 2. The Naive Approach - "Basic Implementation"
- Explicit layers/operations from scratch.
- Shape comments after every tensor op.
- Train/run. Plot results. Narrate the failure.

## 3. Diagnosis — "Why it fails?"
- Component loss plots (log scale).
- Activation/gradient histograms.
- Residual/error spatial distribution.
- "Aha!" moment where the problem is identified.

## 4. The Fix — "One concept at a time"
- Implement exactly one improvement.
- Re-train, re-diagnose.
- Side-by-side comparison.
- Quantify improvement/success (error metrics, convergence speed).

## 5. Extension & Iteration Loop
- Add one more feature (e.g., another BC type, nonlinearity, dimension).
- Show that the previous fix generalizes.
- Validate against new analytical or numerical reference.

### ⟳ ITERATION RULE (MANDATORY)
After completing Section 5, apply this decision gate **before** moving to Section 6:

1. **Check cell count.** If the notebook now has **>35 cells**, STOP iterating. Go to step 3.
2. **Check solution quality.** If the solution meets the Diagnostic Checklist (§5) AND no further ideas remain, proceed to Section 6 (Summary). Otherwise, **loop back to Section 3** (Diagnosis) with the current model as the new baseline and repeat Sections 3 → 4 → 5.
3. **Handoff gate.** If cell count exceeds 35 cells OR the next extension would push it past ~40 cells, **do NOT continue in this notebook.** Instead, end the notebook with a formal handoff block per §8 (MULTI-NOTEBOOK SPLITTING & HANDOFF RULES) and start a new notebook for the next iteration.

## 6. Summary & Key Takeaways
- Bullet points of what was learned.
- When to use which approach (decision tree).
- Common pitfalls and how to avoid them.
- Connect to "Next Complexity" or "Next concept" or "Next Idea" or "Next Chapter"

## 7. Retrieval Exercises (Make It Stick)
1. **Tweak**: Change one hyperparameter/condition. Observe.
2. **Swap**: Replace a method/activation/function. Compare.
3. **Extend**: Add a new term/dimension/physics.
4. **Engineer**: Compute a real-world quantity and optimize it.
5. **Debug**: Intentionally break the code. Use diagnostics to find it.
6. **Teach**: Explain this to someone else (or write a blog post).
```

---

## 5. VISUALIZATION RULES

- **Block diagrams for architecture.** Every model gets a diagram before code.
- **Default Plotting Library:** The default plotting library is the `matplotlib`.
- **Labeling is meticulous.** Every axis has units. Every line has a legend.
- **Contour/surface plots for fields.** Every PDE solution gets a spatial residual plot.
- **Loss curves always.** All components plotted separately with consistent color coding.
- **Side-by-side comparisons.** Same axes, same color limits, same scale.
- **Vector fields for fluxes.** `quiver` for gradients, heat flux, fluid velocity.
- **Animation when possible.** Time-dependent problems get frame sequences, not just final states.
- **Plot/figure captions.** Every plot, figure, and table must include a caption explaining the key insight.

---

## 6. DIAGNOSTIC CHECKLIST (Generalized "Health Check")

Before declaring a lesson "learned," verify:

- [ ] **Loss curves**: All components decrease on log scale. No unexplained plateaus.
- [ ] **Error distribution**: Spatially uniform where expected. No hidden bias at boundaries/corners.
- [ ] **State health**: No saturation > 10%. No dead neurons/elements.
- [ ] **Gradient health**: Std within 1 order of magnitude across layers. No vanishing/exploding.
- [ ] **Update ratio**: `std(lr * grad) / std(param)` ~ 1e-3 for all layers.
- [ ] **Prediction sanity**: Matches analytical/numerical reference within tolerance.
- [ ] **Physics/math sanity**: Direction/sign is correct. Bounds respected. Conservation laws hold.
- [ ] **Feynman test**: Can explain the mechanism in one paragraph without jargon.
- [ ] **Retrieval test**: Can rebuild the core logic from a blank notebook in under 20 minutes.

---

## 7. LANGUAGE AND TONE

- **Notebooks are Lab Workbenches, NOT Textbooks:** The `.ipynb` files must strictly be treated as a researcher's stream-of-consciousness scratchpad. **DO NOT write textbook-style prose** Notebooks are for thinking, coding, debugging, and plotting.
- **Conversational but precise.** "We," "us," "let us." Guide, not lecture.
- **Enthusiastic about failure.** "Look at this beautiful hockey-stick loss! This tells us exactly what is wrong."
- **No jargon without a picture.** Every symbol must appear in a diagram or code within 3 paragraphs.
- **Self-deprecating about complexity.** "This looks scary, but it is just chain rule. Let us do it step by step."
- **Explicit over implicit.** No `*args, **kwargs` in teaching code. No list comprehensions for complex ops.
- **Separate cells for setup, training, and diagnostics.** Never combine training and plotting in one cell. 
- **Math-rich but code-light.** Prioritize mathematical formulation, dimensionality, and scaling laws over library APIs.

---

## 6. MULTI-NOTEBOOK SPLITTING & HANDOFF RULES

When a notebook exceeds **35 cells** or the next iteration would push it past **~40 cells**, you **must** split. Do not continue in the same notebook.

### Rule 1: End the current notebook with a Handoff Block

Replace the normal Section 6 (Summary) with a **handoff cell** using this exact template:

```markdown
---
## ⛓️ HANDOFF: This notebook ends here.

**Current State:**
- Architecture: [e.g., 3-layer MLP, 64 neurons, tanh activation]
- Best loss: [e.g., total=2.3e-4, PDE=1.1e-4, BC=1.2e-4]
- Key hyperparams: [e.g., lr=1e-3, λ_bc=10, 5000 epochs]
- Remaining error: [e.g., max boundary error 0.8°C at x=L]

**The Wall:**
[One concrete sentence: what failed or what the next complexity requires that this notebook cannot accommodate. e.g., "Soft boundary penalty is unstable for triangular profiles — hard constraints are needed."]

**Next Notebook Blueprint:**
1. [Step 1 for next notebook]
2. [Step 2]
3. [Step 3]

**Target File:** `XXXX-next-topic.ipynb`
---
```

### Rule 2: Start the next notebook self-contained

The subsequent notebook **must** be runnable without executing the previous one. Its introduction must:

1. **Recap** the handoff (what was achieved, what wall was hit, what this notebook will tackle).
2. **Re-establish state** — re-import libraries, re-define the model architecture, and hard-code the best hyperparameters from the previous notebook so the learner can execute from cell 1.
3. **Begin at Section 2 or 3** of the standard template (not Section 1, unless the physics setup changes).


---

## 9. META-LESSON

This framework teaches **how to debug any complex system** by:
1. Decomposing into testable hypotheses (mechanism, code, data, gradients).
2. Visualizing every intermediate state (activations, residuals, errors, fluxes).
3. Fixing one thing at a time and measuring the delta.
4. Building intuition through failure, not just success.
5. Making knowledge durable through retrieval, spacing, and interleaving.

**The ultimate goal**: You should not just have a working solution. You should have a **mental model** strong enough to invent new approaches for problems that do not yet exist in textbooks.

---

*"What I cannot create, I do not understand."* — Richard Feynman  
*"The magic is in the code. Just understand it from first principles."* — Andrej Karpathy  
*"Learning is not about possession of knowledge; it is about the ability to retrieve it under difficulty."* — Make It Stick
