# Bead: sase-1q5.1 — Batch the stranded-work session query per project

[Bead Pages](../README.md) / [sase-1q5](README.md) / sase-1q5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5k.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5k.linker.w0.md) · **Assignee:** `sase-1q5.1` · **Size:** small
**Created:** 2026-10-30 18:38:09 EDT · **Closed:** 2026-10-30 20:27:38 EDT
**Plan:** [202610/tui\_index\_lock\_speedup.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_index_lock_speedup.md)

## Description

stranded-batch: replace the per-assignee index query loop with one batched, chunked query per project, keeping the exact recheck and dedupe, with parity tests and a before/after timing.

## Notes

[2026-10-30T23:19:44Z · sase-1q5.1] stranded-batch timing gh_sase-org__sase: before wall=157.1s queries=238 (per-assignee loop, stashed new code); after wall=4.7s queries=3 (batched, chunk=100). Bead count identical (238). Machine was loaded (concurrent check lane) so treat absolutes as noisy; the query-count drop 238->3 is the structural win.

[2026-10-31T00:27:38Z · sase-1q5.1--1] Batched stranded session query per project (chunk=100) in stranded_facts.py; parity tests new/updated (test_stranded_collector_batch.py, test_stranded_collector_recovery.py); timing 157.1s/238q -> 4.7s/3q with identical bead count; sase tool run check a898fdb3ebec496f2b5ab26739fc30d7 green (all lint + test scoped exit 0, triage pass); epic-symbols clean.

## Dependencies

- **Blocks:** [sase-1q5.4](sase-1q5.4.md) ✓ · ⧖ 2026-10-30
- **Blocks:** [sase-1q5.8](sase-1q5.8.md) ✓ · ⧖ 2026-10-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1q5.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q5.1.md) | [sase-1q5.1](sase-1q5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`58ce6ee`](https://github.com/sase-org/sase/commit/58ce6ee62e468710a118a93b77d0084cad98b1a5) | feat(bead): batch stranded session query per project | [sase-1q5.1](sase-1q5.1.md) | 2026-10-30 20:29:00 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1q5.1--1][1] | Need phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q5.1.md

<!-- sase:referenced-by:end -->
