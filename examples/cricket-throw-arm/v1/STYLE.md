# HTML Style — Çengel Textbook

Defines how every HTML lesson *looks*. The goal: lessons read like a chapter of Çengel's
*Heat and Mass Transfer* — warm, visual, accessible, with key ideas pulled into the margin.

**Canonical reference:** [`_style-preview/cengel.html`](_style-preview/cengel.html). Build new lessons by
copying its structure and CSS — don't reinvent the look each time.

## Palette

| Role | Hex |
|------|-----|
| Primary teal | `#0b6e8f` |
| Dark teal (headings) | `#085469` |
| Teal tint (boxes) | `#e3f1f6` |
| Orange accent (margin, problems) | `#e08a1e` |
| Red (emphasis in margin) | `#c0392b` |
| Ink (body text) | `#1c2a30` |
| Paper (background) | `#fffdf8` |

## Typography

- **Body:** serif (Iowan Old Style / Georgia), ~17px, line-height 1.6.
- **Headings, labels, margin notes:** sans-serif (Source Sans Pro / system UI).
- **Equations:** Cambria Math / Georgia serif.

## Required components (the Çengel signatures)

1. **Chapter banner** — teal gradient header with chapter number, title, italic subtitle.
2. **Objectives box** — tinted teal, bulleted, right after the banner.
3. **Margin notes** — right-hand column; orange-bordered callouts that pull each section's key idea
   into the margin. This is the defining Çengel feature — use it generously.
4. **Key-equation box** — teal-tinted, bordered, equation centered with a right-aligned number `(1–1)`.
5. **Worked example** — teal header bar; body sectioned **Problem / Analysis / Comment**.
6. **Summary block** — teal-topped tinted box of takeaway bullets.
7. **Problems** — orange-numbered list at the end.
8. **Footer** — primary-source link + a reminder to ask the teacher follow-ups.

## Layout

- Max width ~960px; two-column grid (main + 220px margin column) that collapses to one column on
  narrow screens.
- Light theme only. Prints cleanly.
- Figures: centered, bordered, rounded; captions in `FIGURE 1–1` form with a teal label.

## Mapping to the teaching loop

The four phases of [TEACHING-METHOD.md](TEACHING-METHOD.md) map onto Çengel components:

- **Visualize** → banner + opening figure + margin notes.
- **Build** → key-equation box + worked example.
- **Compress** → Summary block.
- **Retain** → Problems list.
