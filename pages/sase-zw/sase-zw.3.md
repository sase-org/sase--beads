# Bead: sase-zw.3 — Reap proc runtime directories with proc-row retention

[Bead Pages](../README.md) / [sase-zw](README.md) / sase-zw.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ka](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ka.md) · **Assignee:** `sase-zw.3` · **Size:** small
**Created:** 2026-09-12 13:26:43 EDT · **Closed:** 2026-09-12 17:02:45 EDT
**Plan:** [202609/bound\_sase\_disk\_footprint.md](https://github.com/sase-org/sase--plans/blob/main/202609/bound_sase_disk_footprint.md)

## Description

procreap: delete a pruned proc's runtime directory alongside its logs and sweep the runtime directories whose proc rows are already gone.

## Notes

[2026-09-12T21:02:45Z · sase-zw.3] Implemented proc runtime retention cleanup: pruned proc rows now remove runtime sidecar dirs and orphan runtime dirs are swept against the active proc-store snapshot; verified focused proc/GitHub/audit tests, just _lint-symvision, just check (full-suite escalation), and sase bead epic-symbols sase-zw.3 reported no entries.

## Dependencies

- **Blocks:** [sase-zw.7](sase-zw.7.md) ◐ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zw.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zw.3/README.md) | [sase-zw.3](sase-zw.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e498ce8`](https://github.com/sase-org/sase/commit/e498ce822c603d3f15301f2956e275db8445f829) | fix(procs): reap proc runtime directories | [sase-zw.3](sase-zw.3.md) | 2026-09-12 17:04:28 EDT |
