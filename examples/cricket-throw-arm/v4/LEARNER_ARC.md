# Learner Arc — Fading Across Missions

`PROJECT_ARC.md` and `TEACHING_STYLE.md` govern one mission. This file governs what
carries over *between* missions — because the actual goal isn't finishing any single
project, it's becoming the kind of person who can open a blank notebook on a brand-new
topic and build it from scratch, the way Karpathy does.

**The keyboard never fades.** The learner builds the naive version themselves, every
mission, from the first one to the hundredth — `TEACHING_STYLE.md` step 4 doesn't relax
over time, and nothing here overrides it. What fades is how much scaffolding surrounds
that build — how much the agent pre-explains, how many checkpoints it inserts, how
much it narrates before the learner attempts. The fade is in the support, never in who
does the building.

## The floor ledger

A single file, **outside any one mission's workspace** — `~/teach-floor.md`, shared
across every project directory `/teach` is ever run in. Every other teaching workspace's
`NOTES.md` should point to this same file by absolute path, because the floor is the
learner's, not the project's.

Format: pattern, status, the mission it was proven in, the date.

```markdown
- Rotational F=ma (moment of inertia, torque) — status: proven — cricket-throw-arm, 2026-06-25
- Linear regression via gradient descent, by hand — status: proven — micrograd-rebuild, 2026-05-12
```

**When to write an entry — same evidentiary bar as `learning-records`, not "was
taught":** log a pattern only when it has been demonstrated through the rebuild card
(the learner actually rebuilt it on a blank page) or reused unprompted in a later
concept without re-explanation. Coverage is not proof; a pattern that was only
explained once does not go on the ledger.

**Every `proven` entry must cite a specific artifact, not just the agent's
impression that the session went well.** Record, in the linked `learning-records`
entry, the actual rebuild-card answer or the verbatim unprompted reuse that earned
the mark. The same agent that taught the lesson is also the one judging whether it
landed — without a cited artifact, that judgment is unfalsifiable and tends to drift
generous over time, which then under-scaffolds the next mission that trusts it. If
you can't point to the artifact, the entry isn't `proven` yet.

**Status is not permanent.** If a learner struggles on a concept whose recursion chain
(per `PROJECT_ARC.md`) the ledger says is already proven, don't quietly patch over it —
mark the relevant entry `status: shaky, revisit`. A shaky entry is treated as not on
the ledger: the next time that pattern is needed, scaffold it fully again, as if it had
never been proven, until it's re-demonstrated and restored to `proven`.

## How a new mission consults it

When `PROJECT_ARC.md`'s Pass 2 recurses a component down toward its base, check the
ledger before recursing further. If a branch's transferable pattern is already
`proven`, stop there — it's floor, not a new lesson. If it's `shaky`, treat it as
unproven and teach it again properly.

## How scaffolding fades

Scaffolding depth on any new concept is set mechanically by how much of its recursion
chain is already `proven` on the ledger — not by counting recent sessions, not by a
fixed threshold. If most of what a new concept rests on is already floor, the agent
skips pre-explaining those parts entirely and only narrates/predicts-with the learner
on the genuinely new piece at the top of the chain. If little or nothing is floor yet,
full scaffolding applies, the same as mission one. The fade is a direct readout of the
ledger, never a separate counter to track.

## The end state

Success isn't a mission being finished — it's the floor ledger eventually covering
enough that almost nothing needs pre-explaining on a new topic. The end state is
explicit: the learner picks an unrelated, never-discussed topic, opens a blank
notebook, builds the naive version themselves with no pre-explanation at all, and the
agent's job has shrunk to what Karpathy's audience gives him — someone to explain it
to, not someone who needs the path cleared first.
