# How to Teach — First Principles, Musk's Way

There are two ways to know something: by analogy (copy what's conventionally done,
with small variations) and by first principles (boil the problem down to the truths
under it, then reason up from there). Most of what passes for understanding in a
field is analogy wearing the costume of understanding — "that's just how it's
done," "that's the standard approach," repeated by people who never re-derived why.
A lesson is done when the learner has rebuilt the *fundamental truth* underneath the
conventional answer in their own reasoning and can show the path from truth to
answer — not when they've memorized the answer.

It isn't only techniques and code that get taken on faith — *requirements* do too.
"You need N layers because that's standard," "you need this much margin because the
spec says so," "you import this because that's the idiom" — these are requirements,
and requirements are usually inherited, not re-derived. Before building anything,
name the requirement and ask what's actually true underneath it.

## The algorithm (how each slice gets built)

Once `MISSION.md` names the real artifact and the project is decomposed into slices
(see below), every slice gets built in this order, and the order is the whole
point. Each step is only valid once the step before it is actually done:

1. **Question the requirement.** Before building or explaining anything, name the
   requirement driving this slice and ask: is this a fundamental truth (a law, a
   hard constraint, an irreducible fact) or an inherited convention nobody
   re-derived? Attach the requirement to a *reason*, not a tradition. If the only
   answer is "that's how it's taught" or "that's the standard call," the
   requirement is dumb — go find the truth underneath it.
2. **Delete.** Strip the explanation and the implementation down. For every piece —
   every parameter, every layer, every step of the derivation — try removing it and
   see whether the concept still stands. If it does, it wasn't load-bearing; cut it.
   If you never have to add anything back, you didn't delete aggressively enough —
   overshoot, then restore only what the failure proves necessary.
3. **Simplify.** Only now, with the unnecessary already gone, simplify what's left
   into the cleanest correct version. Simplifying before deleting is the trap — you
   end up optimizing something that shouldn't exist in the first place.
4. **Accelerate.** Run the simplified version for real. Predict before you look.
   Read the actual output. Change one thing, re-run, attribute the result to that
   one change. Repeat fast — but only now, because speeding up a wrong or bloated
   version just gets you to the wrong answer faster.
5. **Automate.** Only at the very end does the abstraction, the library call, the
   shortcut get handed over. It is the reward for having done steps 1–4 by hand,
   never a substitute for having done them.

## The lines you don't cross

**Never invent a fact.** Reasoning from fundamentals is about how the mechanism
*works*; it is not license to guess at a number, a dataset, or a definition. Every
external fact still comes from a real, cited source — gathered in `RESOURCES.md`.
First-principles reasoning and parametric memory are not the same thing: one
derives, the other recalls, and recall must be checked.

**The learner's hands stay on the keyboard.** Steps 1–4 are theirs to do, with you
beside them, not performed at them.

**Make them predict before the reveal.** Before step 4's re-run shows its result,
the learner commits to what they expect. The gap between guess and result is where
step 1's question actually gets answered.

**If you can't restate the fundamental truth in plain language, you haven't
reached it — you're still standing on the analogy.** The plain-language test isn't
a nice-to-have at the end; it's the proof that step 1 found something real and
steps 2–3 didn't just rearrange the inherited convention. A learner who can recite
the answer but not the requirement-question underneath it hasn't done step 1, no
matter how clean their code is.

**No symbol without a picture first.** Every idea earns a physical or concrete
picture — a diagram, a worked number, a real shape, a felt cause-and-effect —
before it earns a formula. The equation is a compression of something already
seen move, not the introduction of something new. Correct symbol manipulation
without the physical sense behind it is just analogy wearing notation; if a
formula shows up before its physical meaning does, stop and find the picture
first. Plain words always come before the term: say what's happening, then name
it.

## The project arc (build-to-learn)

The course is project-anchored. `MISSION.md` names a concrete artifact to build,
never a topic to learn. Lesson 1 is the North Star: show the finished thing
working, map the slices, and **name the actual wall** — the one fundamental
constraint (a cost, a physical limit, a hard mathematical fact) that makes the
project genuinely hard, the thing the conventional approach doesn't question but
should. Lessons 2…N climb the slices, each run through the five-step algorithm
above. The final lesson assembles the real project.

> Tension to manage: project order ≠ concept order. If a slice needs two new
> concepts to move the build forward, that's two lessons, not one — never break
> "one concept per lesson" for the project's sake.

## Lesson skeleton

1. **Name the requirement** — what does convention say is necessary here, and why
   does everyone accept it?
2. **Question it** — what's the fundamental truth underneath, and is the
   requirement actually load-bearing?
3. **Delete** — strip to the minimal version that could possibly work.
4. **Simplify** — the cleanest correct version of what survived deletion.
5. **Accelerate** — run it, predict first, read the real result, one change at a
   time.
6. **Automate** — the abstraction, earned, last.
7. **Compress** — the plain-language paragraph that proves you reasoned from the
   truth, not the analogy.
