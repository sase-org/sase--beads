# Bead: sase-9k.3 — Surface wait priority in ACE

[Bead Pages](../README.md) / [sase-9k](README.md) / sase-9k.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9k.3` · **Size:** small
**Created:** 2026-07-25 14:38:31 UTC
**Plan:** [sase/repos/plans/202607/wait\_priority.md](https://github.com/sase-org/sase--plans/blob/main/sase/repos/plans/202607/wait_priority.md)

## Description

'Surface wait priority in ACE' section: render the explicit wait priority (and deference state) on queued agent list rows and in the agent detail pane's Wait line, including the render-cache key fix.

## Notes

Implemented ACE wait-priority display for explicit priorities: Agent carries wait_priority_explicit from waiting.json/wire/meta fallback, queued list rows append pN, detail Wait lines append priority N, and row render-cache keys include priority plus explicit flag. Added focused unit coverage for enrichment, dedup, row/detail rendering, and cache invalidation. Deference state was skipped because eligible_since is not projected through the scan wire. Verification: targeted tests passed; just test-visual passed; just check lint/type/validation passed but full parallel pytest repeatedly hit unrelated flakes (direct reruns of reported failures passed).

## Dependencies

- **Depends on:** [sase-9k.2](sase-9k.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9k.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9k.3/README.md) | [sase-9k.3](sase-9k.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`68723be`](https://github.com/sase-org/sase/commit/68723bedb8e0b29b53533200999f6a25f36b081e) | feat(ace): show explicit wait priorities (sase-9k.3) | [sase-9k.3](sase-9k.3.md) | 2026-07-25 16:17:50 |
