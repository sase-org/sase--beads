# Bead: sase-1t3.11.1.2 — Query memory-read history for the selected context

[Bead Pages](../README.md) / [sase-1t3.11.1](sase-1t3.11.1.md) / sase-1t3.11.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t3.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.11.md) · **Assignee:** `sase-1t3.11.1.2` · **Size:** medium
**Created:** 2026-11-17 12:30:56 EST · **Closed:** 2026-11-17 17:15:08 EST
**Plan:** [202611/bounded\_log\_queries.md](https://github.com/sase-org/sase--plans/blob/main/202611/bounded_log_queries.md)

## Description

memory_reads: add the Rust streamed audit-query contract and memory decoder, switch the memory lane to bounded results, and preserve schema and attribution semantics.

## Notes

[2026-11-17T21:46:34Z · sase-1t3.11.1.2--1] Status: symvision NEW failure fixed this turn (MemoryAuditRow made private per hierarchy step 2); full check rerun ebc5d4620c399378b365927831b8ad68 in flight covering the fix. Follow-up: wait for ebc5d4620c399378b365927831b8ad68 green, confirm epic-symbols empty, then close this bead.

[2026-11-17T22:14:51Z · sase-1t3.11.1.2--1] Implemented memory_reads: sase-core audit_query (query_memory_audit: streamed JSONL, exact dir/name precedence, first-member attribution, context dedup, timestamp-desc sort, cap-after-match, source identity; binding memory_audit_query; pin ratcheted) + Python facade src/sase/memory/_read_log_query_facade.py feeding the existing per-agent/context caches from targeted queries (snapshot cache removed); census probes bounded caches; tests reworked plus tests/memory/test_memory_audit_query.py (schema, precedence, dedup, cap, malformed, 25k/100k bounds). Symvision fix: MemoryAuditRow made private (_MemoryAuditRow) per unused-public hierarchy. Verified: sase tool run check ebc5d4620c399378b365927831b8ad68 — all lint gates green incl. symvision; 61682 passed, 18 skipped; triage verdict no_new_failures.

[2026-11-17T22:14:58Z · sase-1t3.11.1.2--1] PROPOSED FOLLOW-UP: TUI import budget over cap (11,846,987 vs 11,828,610) reproduces on the clean base tree (base efc66a420b already at 11,840,137; this phase nets +6,850: facade +7,897, memory_reads -1,047); even fully deferring the new edge leaves the tree over cap. Tracked by task bead sase-1qn.2; also noted on parent epic sase-1t3.11.1.

[2026-11-17T22:15:08Z · sase-1t3.11.1.2--1] Verified: sase tool run check ebc5d4620c399378b365927831b8ad68 — all lint gates green including symvision; 61682 passed, 18 skipped; triage no_new_failures (single KNOWN import-budget overage reproduces on clean base, tracked by sase-1qn.2, recorded as PROPOSED FOLLOW-UP). Epic-symbols empty.

## Dependencies

- **Depends on:** [sase-1t3.11.1.1](sase-1t3.11.1.1.md) ✓ · ⧖ 2026-11-17
- **Blocks:** [sase-1t3.11.1.3](sase-1t3.11.1.3.md) ✓ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.11.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.11.1.2.md) | [sase-1t3.11.1.2](sase-1t3.11.1.2.md) | 3 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@c5e60d7`](https://github.com/sase-org/sase-core/commit/c5e60d78575b50b8eefd1b2881e6fac2b8768f55) | feat(audit-query): add targeted memory audit query over JSONL | [sase-1t3.11.1.2](sase-1t3.11.1.2.md) | 2026-11-17 15:37:19 EST |
| sase | [`1c626f3`](https://github.com/sase-org/sase/commit/1c626f39e5a40ede6de4c7d60082f1e46d193ecd) | feat(memory-reads): query memory audit log with targeted Rust backend | [sase-1t3.11.1.2](sase-1t3.11.1.2.md) | 2026-11-17 15:39:07 EST |
| sase | [`cd0b9c5`](https://github.com/sase-org/sase/commit/cd0b9c52733af177af29cadf61c6cde474b6340c) | fix(memory-reads): privatize audit row per symvision unused-public hierarchy | [sase-1t3.11.1.2](sase-1t3.11.1.2.md) | 2026-11-17 17:23:59 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1t3.11.1.2--2][1] | check phase bead status for monitor handoff close-out | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.11.1.2.md

<!-- sase:referenced-by:end -->
