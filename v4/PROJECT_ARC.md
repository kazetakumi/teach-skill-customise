# Project Arc — From One Prompt to a Lesson Sequence

How a single mission becomes an ordered, sized sequence of lessons. Three moves, not
eight: recurse to the base, check the ledger, size with one test. This runs once,
between `MISSION.md` being filled and Lesson 1 being written — and gets revised as
teaching reveals it was wrong.

## Pass 1 — artifact → components

From the mission's target artifact, list its working subsystems — what is this thing
actually made of? This is mechanical systems decomposition, not pedagogical judgment
yet, and it surfaces dependencies *between* components for free: one component's output
is often another's input.

## Pass 2 — component → concept, recursed to the base

For each component, ask what understanding is needed to build *that piece* — then don't
stop at the first answer. Ask the same question of that concept: what does *this* rest
on? Keep recursing until you hit either a true primitive (a fundamental truth that
doesn't decompose further) or the learner's actual demonstrated floor (found by
probing, not assumed). A component-to-concept map that's only one level deep just
relocates the abstraction instead of grounding it; the recursion is what makes it
first-principles rather than a lookup table.

**The recursion question is the delete-test — don't run a second pass for it.** "Does
the component actually need this?" is the same question as "is this load-bearing?" If
the answer is no, it was never part of the chain; there is nothing further to cut.

**Naming what a concept *is*, as it survives the recursion, gives you its type and its
order for free — these are not separate steps:**

- A strict dependency (the next thing genuinely can't be accessed without it) **is**
  hierarchical — hard prerequisite, non-negotiable order, violating it is an error.
- A different valid way of looking at the same thing, with no strict dependency on it,
  **is** horizontal — soft scaffold, recommended order, adjustable.
- A practiced, enacted capability, felt before it's named, **is** dispositional —
  experiential readiness, practice generally before explanation.

There's no classification pass and no separate sequencing pass. Naming what a concept
*is* during the recursion already tells you where it goes.

**Name the transferable pattern, not just the concept.** For every concept that
survives the recursion, state what it's an instance *of* — the form that will recur on
a totally unrelated future topic (e.g. "moment of inertia for a tapering arm" is an
instance of "rotational F=ma," which will resurface in any spinning or swinging system,
not just this one). The artifact is the vehicle; the transferable pattern is what
actually gets kept. This is the unit that gets logged to
[`LEARNER_ARC.md`](LEARNER_ARC.md)'s floor ledger — not "built a throw arm," but "can
derive rotational F=ma from scratch."

**Check the floor ledger before recursing further.** If the transferable pattern a
branch of the recursion is heading toward is already on the learner's floor ledger
(per [`LEARNER_ARC.md`](LEARNER_ARC.md)), stop that branch immediately — it's proven,
not a new lesson. Name it as a callback when it resurfaces, never a fresh derivation.

*Open question, not yet resolved:* Pass 1 assumes the target artifact has clean
subsystems — true for a physical/computational build, less obviously true for a
mission like "get better at technical writing." Revisit this if Pass 1 turns out to be
trivial or skippable for non-engineering missions.

## Size each lesson

One test, reused from [`TEACHING_STYLE.md`](TEACHING_STYLE.md) step 5, not invented
here: **the bundling test.** Can you get from the dumb first version to a blank-page
rebuild without opening a second idea to make the first make sense? If not, it was two
lessons; split it.

## Validate against the North Star

Lesson 1 shows the assembled target artifact actually working. The final lesson
re-derives it. If walking the ordered, sized sequence can't actually reconstruct what
Lesson 1 showed, the decomposition was wrong — revise it the same way a failed code run
revises the next step, not as a one-shot plan committed to blind.
