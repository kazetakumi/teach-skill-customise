# Findings — github.com/GarethManning/education-agent-skills

Exploration of a third-party repo of education-focused Claude skills, done while
looking for a method to decompose a topic/project into an ordered sequence of
lessons (the open problem for `v4/TEACHING_STYLE.md`'s missing Project Arc section).

## Useful findings

| Category | Source | Finding |
|---|---|---|
| Curriculum design — sequencing | [`scope-and-sequence-designer`](https://github.com/GarethManning/education-agent-skills/blob/main/skills/curriculum-assessment/scope-and-sequence-designer/SKILL.md) | Three sequencing logics by content type: hard prerequisite (non-negotiable order), soft scaffold (recommended, adjustable), experiential readiness (practice before explanation for skill-type content) |
| Curriculum design — classification | [`curriculum-knowledge-architecture-designer`](https://github.com/GarethManning/education-agent-skills/tree/main/skills/curriculum-assessment/curriculum-knowledge-architecture-designer) | Classify content as T1 hierarchical (prerequisite chains) / T2 horizontal (multiple valid lenses, no strict order) / T3 dispositional (practiced capability, graded in bands) *before* sequencing — most topics are a mix of all three |
| Curriculum design — sizing (gap) | *(none found in repo)* | No skill has a real lesson-granularity rule — only our own delete-test (Musk) and bundling-test (v2, in `TEACHING-METHOD.md`) cover "how big should one lesson be" |
| Teaching — lesson structure | [`explicit-instruction`](https://github.com/GarethManning/education-agent-skills/tree/main/skills/explicit-instruction) (`explicit-instruction-sequence-builder`) | I Do (20%) → We Do (30%) → You Do (40%) time ratio; 80%+ success-rate gate required before advancing guided → independent practice |
| Teaching — practice design | [`explicit-instruction`](https://github.com/GarethManning/education-agent-skills/tree/main/skills/explicit-instruction) (`practice-problem-sequence-designer`) | Practice problems sequenced near-transfer → far-transfer, not random order |
| Learning — readiness gating | [`student-learning`](https://github.com/GarethManning/education-agent-skills/tree/main/skills/student-learning) (`fading-manager`) | Numeric thresholds (e.g. 3 consecutive sessions at quality X) move a learner up/down a 5-level scaffold ladder |
| Learning — error handling | [`student-learning`](https://github.com/GarethManning/education-agent-skills/tree/main/skills/student-learning) (`stuck-and-error-diagnosis-coach`) | Classify an error as conceptual / procedural / strategic / representational, then target help by type, not generically |
| Learning — individual placement | [`professional-learning`](https://github.com/GarethManning/education-agent-skills/tree/main/skills/professional-learning) (`pedagogical-content-knowledge-developer`) | Diagnose a learner's floor from their *stated* background (not age/cohort), sequence only the actual gaps, define an explicit stop/sufficiency criterion |

## Dead ends (explored, not useful for this problem)

- [`curriculum-alignment`](https://github.com/GarethManning/education-agent-skills/tree/main/skills/curriculum-alignment) — standards/coverage auditing, assumes a decomposition already exists
- [`original-frameworks`](https://github.com/GarethManning/education-agent-skills/tree/main/skills/original-frameworks) — developmental band/depth grading across years, not lesson sequencing
- [`systems-thinking`](https://github.com/GarethManning/education-agent-skills/tree/main/skills/systems-thinking) — real-world social/ecological systems mapping for civic action projects, not curriculum architecture

## Not yet explored

`memory-learning-science`, `self-regulated-learning`, `questioning-discussion`, `ai-learning-science` — likely relevant by name, not checked yet.

## Repo root

https://github.com/GarethManning/education-agent-skills/tree/main/skills
