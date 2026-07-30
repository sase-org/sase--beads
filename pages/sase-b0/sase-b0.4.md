# Bead: sase-b0.4 — Files filter bar, kind cycle, and in-memory filtering

[Bead Pages](../README.md) / [sase-b0](README.md) / sase-b0.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b0.4` · **Size:** medium
**Created:** 2026-07-29 23:14:02 UTC · **Closed:** 2026-07-30 00:57:36 UTC
**Plan:** [202607/artifacts\_files\_subtab.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifacts_files_subtab.md)

## Description

filters: add the Files filter bar with kind/project/agent/workflow/ origin/since/until tokens and free text, pure in-memory filtering over the loaded snapshot, completion sources, the s kind-cycle key, and the / edit-query arm.

## Notes

[2026-07-30T00:57:36Z · sase-b0.4] Implemented and verified the Files filter bar, kind/project/agent/workflow/origin/since/until and free-text snapshot-only filtering, display-name completion sources, present-kind cycling, filtered chips/counts and empty state, plus f and / routing. Verified 26 Files/navigation tests passed, 31 directly rerun SDD/bead tests passed, mypy passed across 2526 source files, and just check passed formatting, Ruff, script/changelog, Symvision, and toobig stages. SASE validation remains blocked by six unrelated shared-sidecar reciprocal plan/prompt link errors for artifacts_files_subtab, at_reference_completion_menu, and copy_as_palette.

[2026-07-30T00:58:30Z · sase-b0.4] Verified 26 Files/navigation tests and 31 related SDD/bead tests pass; mypy passed across 2,526 files; formatting, Ruff, Symvision, and size checks passed. Full SASE validation remains blocked only by six unrelated reciprocal plan/prompt link errors in the shared plans sidecar.

## Dependencies

- **Depends on:** [sase-b0.2](sase-b0.2.md) ✓
- **Blocks:** [sase-b0.7](sase-b0.7.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b0.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b0.4/README.md) | [sase-b0.4](sase-b0.4.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`842723f`](https://github.com/sase-org/sase/commit/842723f6f6db058f7d301d732e61bb24aaf052f5) | feat(ace): add artifact file filtering | [sase-b0.4](sase-b0.4.md) | 2026-07-30 01:01:36 |
