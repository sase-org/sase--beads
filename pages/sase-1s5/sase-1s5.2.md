# Bead: sase-1s5.2 — Batched dismissal-lineage resolution makes fleet snapshot builds fast

[Bead Pages](../README.md) / [sase-1s5](README.md) / sase-1s5.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.cy--6` · **Assignee:** `sase-1s5.2` · **Size:** medium
**Created:** 2026-11-08 06:51:28 EST · **Closed:** 2026-11-08 07:40:31 EST
**Plan:** [202611/health\_watch\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/health_watch_fixes.md)

## Description

fleet-lineage-batch: in sase-core, replace the per-candidate SQL lineage walk in resolve_agent_session_dismissal_lineage with one lineage-column load per (project, workflow dir) pair and an in-memory walk with identical results, prove equivalence and O(pairs) query count in tests, move sase's sase-core pin, and verify on apollo (F10).

## Notes

[2026-11-08T12:39:56Z · sase-1s5.2] F10 BEFORE (apollo health watch, 2026-11-08): presentation fleet snapshot builds 6.1–10.9 s (mean ~7.3 s) for ~86 served rows / 304 candidates. resolve_agent_session_dismissal_lineage did 727 select_lineage_rows calls costing 6.4–6.7 s (each 6–10 ms, fetching record_json ~14 KiB). Almost every build left timed_out_waiters>0 (116 of 120 in check 6). Cold-cache 504 Gateway Timeout after gateway start (5–17/day historically; one 21 s after the 11:40 UTC restart). Private-copy measurement of this phase's batching: 0.07 s for the same 304-candidate walk. covering_index = no; query_related_agent_artifact_dirs unchanged. After numbers wait on the apollo reinstall+gateway-restart gate follow-up.

[2026-11-08T12:40:31Z · sase-1s5.2] Batched resolve_agent_session_dismissal_lineage: one lineage-column load per (project, workflow dir) pair and an in-memory walk with identical results to the per-candidate SQL oracle. covering_index = no. Equivalence fixtures cover parent/retry chains, agent_session fallback, dismissed root, dead-seed suffix, missing seed, multi pair, and both expansion bounds. Pair-load count equals distinct pairs. Existing lineage, fleet_catalog, and sase_gateway fleet_reads tests passed. sase-core just check (sase tool run 88acffeeef5f1fea8f910168ead3e21d) passed. epic-symbols clean. Apollo reinstall+gateway restart proposed as staged gate custom-196bbcc8-c58f-4df3-ae8a-8137e67e2897; follow-up records after numbers.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1s5.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1s5.2/README.md) | [sase-1s5.2](sase-1s5.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@bee250a`](https://github.com/sase-org/sase-core/commit/bee250a33514a48e6bc422618c1a8c6ab661c039) | perf(agent-scan): batch dismissal-lineage walks by project/workflow pair | [sase-1s5.2](sase-1s5.2.md) | 2026-11-08 07:42:12 EST |
