# Bead: sase-ej.4 — Rewire commit and other writers to mark instead of publish

[Bead Pages](../README.md) / [sase-ej](README.md) / sase-ej.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sh/README.md) · **Assignee:** `sase-ej.4` · **Size:** medium
**Created:** 2026-08-03 10:20:57 UTC · **Closed:** 2026-08-03 12:23:38 UTC
**Plan:** [202608/async\_sidecar\_publication.md](https://github.com/sase-org/sase--plans/blob/main/202608/async_sidecar_publication.md)

## Description

commit: convert `sase commit` and every remaining synchronous agents/beads sidecar writer into enqueue-only callers so no interactive command performs sidecar git work.

## Notes

[2026-08-03T12:23:38Z · sase-ej.4] Verified sase commit and planner approval enqueue agent-hood and prompt, bead-page, and plan-header work; split SDD post-commit pushes enqueue sidecar_push requests; resume coalesces requests without duplication; enqueue paths run no sidecar git or push subprocess; explicit drain coverage preserves publication behavior from the stable primary checkout; full just check passes.

[2026-08-03T12:24:11Z · sase-ej.4] Verified queue-only publication paths and full just check.

## Dependencies

- **Depends on:** [sase-ej.2](sase-ej.2.md) ✓
- **Depends on:** [sase-ej.3](sase-ej.3.md) ✓
- **Blocks:** [sase-ej.5](sase-ej.5.md) ◐
- **Blocks:** [sase-ej.6](sase-ej.6.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ej.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ej.4/README.md) | [sase-ej.4](sase-ej.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`3ac2b09`](https://github.com/sase-org/sase/commit/3ac2b097beac842dc02df1edf88704ff87cd351d) | feat: queue interactive sidecar publication | [sase-ej.4](sase-ej.4.md) | 2026-08-03 12:26:38 |
