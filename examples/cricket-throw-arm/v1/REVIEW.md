# Review Ledger

Operationalizes Phase 4 (Retain) of [TEACHING-METHOD.md](TEACHING-METHOD.md). Spacing only works if something tracks *what to review and when*. This is that ledger.

## Protocol

- **At session start:** scan this ledger. Any row whose **Next due** is on/before today is **due** — surface those for retrieval *before* teaching anything new.
- **After a successful review:** advance the interval and recompute Next due.
- **After a failed/shaky review:** reset interval to the first step (1 day).
- **When a new lesson is taught:** add a row, interval `1d`, Next due = tomorrow.

## Interval schedule (expanding)

`1d → 3d → 7d → 16d → 35d → done`

Each clean recall moves one step right. A miss drops back to `1d`.

## Ledger

| # | Concept | Lesson | Last reviewed | Interval | Next due | Status |
|---|---------|--------|---------------|----------|----------|--------|
| _ | _(none yet — first lesson adds the first row)_ | | | | | |

## Interleaving note

When two or more concepts are due the same day, review them **mixed**, not in blocks — practice *choosing* the right tool, not just recalling one in isolation.
