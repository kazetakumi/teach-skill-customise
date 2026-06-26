# Lesson Format

Defines *what file(s)* a lesson produces. Pairs with [TEACHING-METHOD.md](TEACHING-METHOD.md), which defines *how* it's taught.

## The rule

**Every lesson ends with an HTML file.** HTML is the durable, portable, reviewable artifact — one consistent format for every topic.

- **Computational topic** (code, math, simulation — anything you build and run):
  `.ipynb` (build surface) → coupled `.html` (review).
- **Conceptual topic** (no code to run):
  `.html` only.

## Why two artifacts for computational topics

- **Notebook = workbench.** Where Phase 2 (build from scratch, fail, diagnose, fix) happens. Messy by design — for thinking, not keeping.
- **HTML = performance.** The clean, beautiful version you revisit later (Tufte). Derived *from* the executed notebook, so its plots and results are real.

## Coupling rule

The HTML is a **thoughtful synthesis** of the notebook, not an `nbconvert` dump:

- Extract the core learnings, the key plots, and the compressed explanation.
- Rewrite for review — no code dumps, no `In[ ]:`/`Out[ ]:` prompts, no cell chrome.
- Embed the notebook's real output figures.
- Build the HTML only after the notebook runs top-to-bottom without errors.

## Files

- Notebooks: `./lessons/0001-<dash-case-name>.ipynb`
- HTML: `./lessons/0001-<dash-case-name>.html` (same number + name as its notebook)
