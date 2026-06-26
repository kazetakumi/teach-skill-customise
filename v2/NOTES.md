# Teaching Notes

## Teaching Method
- **Follow [TEACHING-METHOD.md](TEACHING-METHOD.md) for every lesson.** It defines the single posture (teach the way Karpathy teaches — build the concept from scratch, live, looking at the real thing, until I could rebuild it alone) and the bright lines that hold every lesson to it. There is no phase loop; there is one goal and a few lines you don't cross. This governs *how* I'm taught, regardless of topic.
- **Ground facts in sources, not memory.** Derive mechanisms from scratch, but gather every external fact, dataset, number, and definition into `RESOURCES.md` from trusted sources first — and cite them in the lesson. Never invent facts from parametric memory.

## Lesson Output
- **Follow [LESSON-FORMAT.md](LESSON-FORMAT.md): HTML is the medium I teach through.** Every lesson is delivered as one HTML file, always — computational or conceptual, no exceptions. It is not a record of a lesson held in chat; it *is* the lesson, the way Karpathy's video is the lesson. Code is run live in a throwaway scratch surface; the scratch is thrown away, and every number and plot on the page comes from a real run, never invented.

## Style
- **Style every HTML lesson per [STYLE.md](STYLE.md).** One editorial, warm, code-forward look — clean and Karpathy-minimal, no noise, no emoji. The struggle (prediction, failure, one-change fix, rebuild prompt) stays on the page. Canonical reference: `_style-examples/Bprime-reference.html`.

Retention/spaced-review is **deliberately unwired** for now — v1's manual ledger is dropped, and a v2 retention design will replace it. Until then, no review step runs.

## User Preferences
- **First-principles learner.** Always derive from the ground up — no accepting results on authority. Start from primitives and build. If a lesson rests on something I haven't built, stop and build that first.
- **Mental-model first.** The goal of every lesson is a clear mental model I could rebuild from a blank page, not just a working answer.
- **Hands on the keyboard.** I write the naive version and predict outputs before they're revealed — I don't just watch.
- **Teachability is the success test.** I should be able to explain the concept to anyone, in simple language, from first principles. If I can't teach it simply, the lesson isn't done.
