# teach-skill-customise

A topic-agnostic, **project-anchored** customization overlay for
[Matt Pocock's `teach` skill](https://github.com/mattpocock/skills).

It does **not** fork or alter the core skill. The core skill reads one file —
`NOTES.md` — for user preferences. This overlay uses that single hook to graft a
complete teaching method onto the skill: `NOTES.md` links out to a small set of
spec files that change *how* lessons are taught, *what* they output, *when* they're
reviewed, and *how* they look.

```
teach skill (SKILL.md)  ──reads──▶  NOTES.md  ──links──▶  TEACHING-METHOD.md
                                                          LESSON-FORMAT.md
                                                          REVIEW.md
                                                          STYLE.md
```

## The teaching method

Every course is **build-to-learn**: you name a real artifact to build, and master
each concept as a slice of it.

- **Project-anchored.** `MISSION.md` names a concrete build target ("build a working
  task board in React"), not a vague topic ("learn React").
- **North Star first.** Lesson 1 shows the finished thing working plus a roadmap of
  the slices to come. Lessons 2…N climb the foundations; the final lesson assembles it.

Each lesson runs through a **four-phase loop**, each phase clearing one gate of
real understanding:

| Phase | Borrowed from | Gate it clears |
|-------|---------------|----------------|
| **Visualize** | 3Blue1Brown | see the mechanism |
| **Build from scratch** | Karpathy | construct it from primitives |
| **Compress** | Feynman | explain it simply |
| **Retain** | *Make It Stick* | keep it (spaced + interleaved) |

## Files (in `v1/`)

| File | Role |
|------|------|
| `NOTES.md` | The plug. Links the specs below + records learner preferences. |
| `TEACHING-METHOD.md` | The four-phase loop, three gates, and the project arc. |
| `LESSON-FORMAT.md` | Output rule: every lesson ends in HTML; computational topics build in a coupled `.ipynb` first. |
| `REVIEW.md` | Spaced-review ledger (`1d → 3d → 7d → 16d → 35d`), checked at session start. |
| `STYLE.md` | Çengel-textbook HTML look (teal banner, objectives box, margin notes, color-boxed equations). Reference: `_style-preview/cengel.html`. |

## How to use it

1. Make a workspace folder for your project, e.g. `~/teach/fea-bracket/`.
2. Copy the `v1/` spec files into it.
3. Open Claude Code there and run `/teach build <your real target>`.

The skill reads `NOTES.md`, follows the links, and teaches in the four-phase,
project-anchored, Çengel style.
