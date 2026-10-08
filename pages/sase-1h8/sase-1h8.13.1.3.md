# Bead: sase-1h8.13.1.3 — One mutation view with shared algorithms, and the full notes family on it

[Bead Pages](../README.md) / [sase-1h8.13.1](sase-1h8.13.1.md) / sase-1h8.13.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0yi](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0yi.md) · **Assignee:** `sase-1h8.13.1.3` · **Size:** medium
**Created:** 2026-10-08 14:46:05 EDT · **Closed:** 2026-10-08 18:16:18 EDT
**Plan:** [202610/finish\_read\_model\_mutations\_child\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_read_model_mutations_child_epic.md)

## Description

view-core: fold indexed.rs into MutationView with cached and replay backings, staged events and a single commit; share event minting, lazy stream loading and manifest totals; rewrite create and the whole notes family (update batches with external-ref changes, reopen, append/edit/retract notes, attachments) as single algorithms; fix allocation range queries and oracle parity; close the io-stats counting gaps.

## Notes

[2026-10-08T22:16:10Z · sase-1h8.13.1.3] PROPOSED FOLLOW-UP: sase_gateway sudo_runner timeout_terminates_process_group_and_records_failed_entry fails under full sase tool run check but passes alone on both base and view-core trees — likely parallel-lane flake in untouched crate

[2026-10-08T22:16:18Z · sase-1h8.13.1.3] view-core done in sase-core: indexed.rs folded into MutationView (deleted), shared mint/load/manifest/commit helpers in mutation/shared.rs, create + update/append/edit/remove as single view algorithms with no external-ref or reopen fallbacks, LIKE replaced by index range scans with oracle dot parity, counters fixed, 8 new view_core tests; verified just fast, clippy, fmt, 193 mutation tests, 8 view_core, 16 bead_read_parity, 35 bead_event_parity, 296 sase_core_py, 6 read_model_parity green; full gate red only on unrelated gateway sudo_runner flake passing alone, recorded as follow-up; epic-symbols clean

## Dependencies

- **Depends on:** [sase-1h8.13.1.2](sase-1h8.13.1.2.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1h8.13.1.4](sase-1h8.13.1.4.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1h8.13.1.5](sase-1h8.13.1.5.md) ◐ · ⧖ 2026-10-08
- **Blocks:** [sase-1h8.13.1.6](sase-1h8.13.1.6.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.13.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.3/README.md) | [sase-1h8.13.1.3](sase-1h8.13.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@159f48e`](https://github.com/sase-org/sase-core/commit/159f48ef3c9c8b454eacf715f50eb6cbd5e0a279) | feat(beads): one mutation view with shared algorithms and full notes family | [sase-1h8.13.1.3](sase-1h8.13.1.3.md) | 2026-10-08 18:17:49 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h8.13.1.3][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.3/README.md

<!-- sase:referenced-by:end -->
