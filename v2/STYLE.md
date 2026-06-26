# What a Lesson Looks Like

A v2 lesson uses one editorial, warm, code-forward look — clean and Karpathy-minimal.
Calm to read, confident to look at, nothing gratuitous. If an element isn't carrying
meaning or making the page easier to read, cut it.

**Canonical reference:** [`_style-examples/Bprime-reference.html`](_style-examples/Bprime-reference.html).
Build every lesson by matching it — same palette, type, and components — not by
reinventing the look each time.

## Palette

| Role | Hex |
|------|-----|
| Paper background | `#fbfaf7` |
| Ink (body) | `#16191d` |
| Muted (labels, captions) | `#5b6470` |
| Orange accent | `#b4531f` |
| Failure marker | `#a8443a` |
| Working marker | `#5e7d4f` |
| Code block bg / ink | `#1d2127` / `#e6e1d6` |
| Hairlines | `#e7e3da` |

## Typography

- **Body:** serif (Iowan Old Style / Palatino / Georgia), ~18px, line-height 1.7.
- **Headline, eyebrow, section labels, captions:** sans-serif (Inter / system UI).
- **Code & numeric output:** monospace (SF Mono / Menlo / Consolas).

## Components

- **Eyebrow** — small uppercase orange kicker (lesson number · topic).
- **Headline + lede** — large Inter title, one calm serif lede line under it.
- **Section labels** — short uppercase muted Inter headings.
- **Code blocks** — dark, rounded, soft-shadowed; the *one line that changed* gets a
  faint orange highlight.
- **Result block** — the real output under the code, plainly: a small "Result" tag, the
  actual numbers in monospace, and a one-line italic verdict. A quiet left-border marks
  failure (`#a8443a`) vs working (`#5e7d4f`).
- **Figure** — a real plot, centered, thin border, sans caption.
- **Pull-line** — one orange-bordered sentence carrying the lesson's single insight.
- **Rebuild card** — a soft white card at the end with the blank-page question.

## What must stay on the page (the struggle)

The look exists to show how the lesson *actually happened*, so these are required:

- **The prediction** — the learner's guess before the reveal, struck through if wrong.
  The wrong guess is the most valuable thing on the page.
- **The failure** — the dumb first version and the exact way it broke, kept visible.
- **The one-change fix** — the single thing that changed and the result it produced.
- **The rebuild card** — the blank-page question that sends the learner to try it.

A lesson that shows only the polished final answer has hidden the teaching. That is the
one thing this style must never do.

## No noise

No emoji or icon ornaments · no decorative imagery that isn't a real figure · no second
accent colour beyond the palette above · no boxes added just to look "finished." The
finished look is the calm one. Keep the page quiet enough that the code and the result
are what catch the eye.
