# Teaching Method — The Four-Phase Loop

A topic-agnostic teaching method. It governs *how* every lesson is taught, regardless of subject. Plug it into the `teach` skill by linking it from `NOTES.md`.

## Project arc (the course is project-anchored)

Learning here is **build-to-learn**: we don't teach a topic in the abstract, we build a real thing and master each concept as a slice of it.

- **`MISSION.md` must name a concrete build target** — not "learn X" but "build *this real artifact* using X." (e.g. "validate a loaded bracket with FEA static analysis," "build a working task board in React.") If the user only gives a topic, interview them to pin a real target before any lesson.
- **Decompose the *project*, not just the topic**, into a sequence of vertical slices. Each slice is one lesson that adds a real, working piece and teaches exactly one concept.

### Lesson 1 is always the North Star
The first lesson shows the destination so every later lesson has a place on the map:

1. **Show the finished project actually working** — a demo, screenshot, or runnable artifact you can see and poke. Not a description.
2. **Dissect it into the slices** we'll build — the roadmap, mapping which lesson builds which part.
3. **Name the foundations** each slice rests on — so the bottom-up climb has a visible reason.

### Lessons 2…N climb the foundations toward the target
Each builds one slice, bottom-up, using the four-phase loop below. The **final lesson assembles the real project.**

> Tension to manage: **project order ≠ concept order.** When advancing the build needs two new concepts, split into two lessons — never break "one concept per lesson" to make the project move faster.

## Core philosophy: three gates

Understanding is real only when a concept passes all three:

1. **Visual gate** — Can the learner draw/picture the mechanism?
2. **Construction gate** — Can they build it from primitives, no black boxes?
3. **Teaching gate** — Can they explain it simply to a beginner?

If any gate fails, understanding is fragile. Lessons exist to walk a concept through all three.

## The loop (every lesson follows this)

### Phase 1 — Visualize (see the mechanism)
- Lead with a diagram, animation, or concrete picture **before** any formalism or code.
- Show what changes and why. Motivate the failure: what breaks without this idea?
- Name the few "knobs" that matter before touching detail.

### Phase 2 — Build from scratch (construct it)
- Build the simplest version from primitives. No frameworks, no shortcuts.
- Let the naive version fail or underperform — the failure *is* the lesson.
- **Diagnose before fixing**: decompose the problem, inspect intermediate state, find where the error lives.
- Fix exactly **one** thing, then re-check. Attribute every improvement to a single change.

### Phase 3 — Compress (Feynman)
- Write the one-paragraph explanation you wish you'd had — plain language, no jargon.
- Every symbol/term maps to a picture or a line of the build.
- Teach-back is the gate: if it can't be explained simply, return to Phase 2.

### Phase 4 — Retain (make it stick)
- End with effortful retrieval, not re-reading: rebuild from a blank page, or a quiz.
- Exercises should feel *slightly too hard* (desirable difficulty).
- Space and interleave: revisit and mix with prior topics across sessions.

## Rules that bind all four phases

- **System 2 before System 1.** Earn intuition through slow, explicit work — never skip rigor to feel fluent.
- **One concept per lesson.** Keep it inside working memory; one tangible win each time.
- **Show, don't assert.** Every claim gets a diagram, a built example, or a citation.
- **Diagnose > fix.** Spend more time understanding *why* something fails than patching it.

## Lesson skeleton

1. **Hook** — the picture and the problem it solves.
2. **Build** — from-scratch construction; narrate the failure; diagnose; fix one thing.
3. **Compress** — the plain-language paragraph + a decision rule for when to use this.
4. **Retain** — 3–5 retrieval exercises (tweak / swap / extend / rebuild / teach).
