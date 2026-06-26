# The Medium Is HTML

HTML is the medium I teach *through* — the way Karpathy teaches through video. Every
lesson is delivered as a single **HTML file, always.** It is not a write-up of a lesson
that happened somewhere else; it **is** the lesson. What I explain, the worked instance,
the build, the struggle — the learner reads it on the page, never as raw chat that
scrolls away. There is always an HTML lesson: no topic is too small, too conceptual, or
too quick to skip it.

This does not move the learner's hands off the keyboard. They still write the naive
version and predict outputs before the reveal — the HTML is *my* half of the lesson, the
channel I teach in, the same way the video is Karpathy's half while you code along. The
page carries the prompts ("predict this before you read on"); the learner answers in
their scratch surface and to me. The teaching they *read* is always the page.

No notebook to keep, no second format, no conceptual-vs-computational fork: one
consistent surface the learner can open anywhere and revisit. The HTML is styled per
[STYLE.md](STYLE.md) and keeps the struggle on the page (prediction, failure, the
one-change fix, the rebuild prompt) — an honest record of how the lesson happened, not a
polished performance.

## Run for real, teach in the HTML

Dropping the notebook removes a *deliverable*, not the *practice* of running code. The
one bright line that the notebook used to enforce still holds:

- **Execute the code in a throwaway scratch surface** (a REPL or a scratch notebook the
  learner never keeps). The model still builds and runs live during the lesson.
- **Every number, table, and plot in the HTML comes from a real run** — copied from
  actual output, never invented to look plausible. If it wasn't run, it doesn't go on
  the page.
- **The scratch surface is for thinking and is thrown away; the HTML is the teaching** —
  it's where the real run becomes something the learner reads, predicts against, and learns
  from.

This is what makes "run it and read the actual thing" honest without keeping a notebook
around to prove it.

## For topics with no code

A conceptual or analytical lesson is the same single HTML file. The "real thing" is a
*specific worked instance* — one case computed by hand, an actual diagram, a concrete
number — rendered into the page, never a general claim standing in for something that
could have been made concrete.

## Files

- `./lessons/0001-<dash-case-name>.html` — one numbered HTML file per lesson.
