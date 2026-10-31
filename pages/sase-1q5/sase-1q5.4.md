# Bead: sase-1q5.4 — Indexed session lookup in sase-core

[Bead Pages](../README.md) / [sase-1q5](README.md) / sase-1q5.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5k.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5k.linker.w0.md) · **Assignee:** `sase-1q5.4` · **Size:** medium
**Created:** 2026-10-30 18:38:10 EDT · **Closed:** 2026-10-30 22:37:27 EDT
**Plan:** [202610/tui\_index\_lock\_speedup.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_index_lock_speedup.md)

## Description

core-session-lookup: push agent_session/agent_name equality filters into SQL with NOCASE indexes, fix the workflow-scoped reconcile deletion bug, keep the Rust post-filter, and move the sase-core pin.

## Notes

[2026-10-31T01:13:58Z · sase-1q5.4] core-session-lookup progress: sase-core pushdown + NOCASE indexes + scoped-reconcile fix + watermark gating implemented; 9 new Rust tests green (146 index tests pass); stranded BEFORE timing gh_sase-org__sase wall=3.5s queries=3 beads=234 on old core; extension rebuild in progress for AFTER timing

[2026-10-31T01:50:12Z · sase-1q5.4--2] AFTER timing (rebuilt sase_core_rs with pushdown): project=gh_sase-org__sase wall=2.5s queries=3 beads=231 vs BEFORE wall=3.5s queries=3 beads=234 on old core. Queries counted at binding level (unchanged call count expected); wall-time gain from SQL pushdown + NOCASE indexes. Full log: /tmp/stranded_after.log, before: /tmp/stranded_before.log

[2026-10-31T02:37:27Z · sase-1q5.4--4] core-session-lookup done: SQL session/name pushdown + NOCASE indexes + scoped-reconcile watermark fix, Rust post-filter kept. Verified: sase-core check run 1093a63163f1d9e73a7057c6ed2c97af PASS (exit 0, verdict pass); workspace check run 5989554ef48a889395635f6c1a5eac97 verdict no_new_failures (27 KNOWN + 1 FLAKY, workspace tree clean, phase diff is 8 files in linked sase-core); stranded timing gh_sase-org__sase BEFORE wall=3.5s queries=3 beads=234 vs AFTER wall=2.5s queries=3 beads=231; epic-symbols empty. No new binding added, sase-core-revision.txt pin left for host.

## Dependencies

- **Depends on:** [sase-1q5.1](sase-1q5.1.md) ✓ · ⧖ 2026-10-30
- **Blocks:** [sase-1q5.8](sase-1q5.8.md) ✓ · ⧖ 2026-10-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1q5.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q5.4.md) | [sase-1q5.4](sase-1q5.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@2775bc0`](https://github.com/sase-org/sase-core/commit/2775bc00934ba77abbc6990880013a013fc80be5) | feat(index): push session/name filters into SQL with NOCASE indexes | [sase-1q5.4](sase-1q5.4.md) | 2026-10-30 22:38:17 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1q5.4--4][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q5.4.md

<!-- sase:referenced-by:end -->
