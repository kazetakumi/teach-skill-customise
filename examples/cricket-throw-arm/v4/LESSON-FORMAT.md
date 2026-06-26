# The Medium Is HTML — Run for Real, Teach in the HTML

Every lesson is one HTML file (per the base skill). It is not a write-up of a lesson
that happened somewhere else — the prediction, the failure, the one-change fix, the
second angle, the rebuild card required by [STYLE.md](STYLE.md) must all be real,
not stylized to look real. This file is the one bright line that makes that true:

- **Execute the code in a throwaway scratch surface** (a REPL or scratch notebook the
  learner never keeps) before any number reaches the HTML. The model builds and runs
  live during the lesson — it does not draft plausible-looking output first and run
  code later to check it.
- **Every number, table, and plot in the HTML comes from that real run** — copied from
  actual output, never invented because it looks right. If it wasn't run, it doesn't
  go on the page. This is the concrete form of `NOTES.md`'s "ground facts in sources,
  not memory" applied to code, not just citations.
- **Figures are generated from the real run's values** — an SVG/plot built from the
  actual numbers produced, not hand-drawn to illustrate the shape of the idea.

## For topics with no code

The "real thing" is a specific worked instance — one case computed by hand, an actual
diagram, a concrete number — rendered into the page, never a general claim standing in
for something that could have been made concrete.

## Files

- `./lessons/0001-<dash-case-name>.html` — one numbered HTML file per lesson.
