# Bead: sase-15b.5 — Split crates/sase\_core/src/bead/events.rs

[Bead Pages](../README.md) / [sase-15b](README.md) / sase-15b.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oh.r0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oh.r0.md) · **Assignee:** `sase-15b.5` · **Size:** medium
**Created:** 2026-09-21 11:31:43 EDT · **Closed:** 2026-09-21 15:53:11 EDT
**Plan:** [202609/sase\_core\_next\_ten\_big\_file\_split.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_core_next_ten_big_file_split.md)

## Description

bead_events: decompose the 3,314-line bead event-stream module into wire, import, reduction, and merge/relocation submodules under bead/events/.

## Notes

[2026-09-21T19:53:11Z · sase-15b.5] Split bead/events.rs (3,314 lines) into bead/events/ tree, just check green. Files: wire.rs 526, import.rs 273, reduction.rs 772, merge.rs 640, mod.rs 38, tests/ 5 files (import 317, merge 287, reduction 393, wire 149, support 41, mod 7). Test count 26 before/after (cargo test --lib bead::events --list). No file over 1500; target absent from over-1500 audit. No public API change: bead/mod.rs untouched, all pub items re-exported from events/mod.rs; former pub(super) items now pub(in crate::bead) with identical reachability. No epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-15b.4](sase-15b.4.md) ✓ · ⧖ 2026-09-21
- **Blocks:** [sase-15b.6](sase-15b.6.md) ✓ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-15b.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-15b.5/README.md) | [sase-15b.5](sase-15b.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@ad732d6`](https://github.com/sase-org/sase-core/commit/ad732d67480bea95cc5a64428988ffb522731e81) | refactor(sase-core): split bead events into wire, import, reduction, merge modules | [sase-15b.5](sase-15b.5.md) | 2026-09-21 15:55:32 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-15b.5][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-15b.5/README.md

<!-- sase:referenced-by:end -->
