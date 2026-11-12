# Bead: sase-1se.4 — Ratchet the core pin, align sase tests and docs, replay the incident

[Bead Pages](../README.md) / [sase-1se](README.md) / sase-1se.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bq](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bq.md) · **Assignee:** `sase-1se.4` · **Size:** medium
**Created:** 2026-11-12 06:15:59 EST · **Closed:** 2026-11-12 09:02:28 EST
**Plan:** [202611/auto\_restart\_update\_skew\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/auto_restart_update_skew_fixes.md)

## Description

pin-docs-verify: move sase's sase-core-revision.txt past the core-origin-precedence commit, update sase-side tests that assert the old classifier verdicts, refresh docs/reference/agent-auto-restart.md, and verify with a read-only `sase agent auto-restart scan` replay of the 2026-11-12 sase@22e1ef1 episode.

## Notes

[2026-11-12T14:02:28Z · sase-1se.4] pin-docs-verify done: sase-core-revision.txt ratcheted 233cb41d->47f1af1c (core-origin-precedence commit, == remote HEAD); added 3 real-binding tests to tests/test_core_agent_auto_restart.py (overlap->tier1, tail-marker ignored, workspace-only still declines); refreshed docs/reference/agent-auto-restart.md (launcher-row resubmission, managed-root-in-workspace precedence, exception-scoped markers); replay: all 7 sase@22e1ef1 rows classify tier1_torn_python/cannot_import_name via the real binding with no workspace_origin/resource_exhausted decline (scan CLI read-only exit 0; wiped rows replayed from surviving runner logs since dirs+bundles are gone); sase tool run check exit 0

## Dependencies

- **Depends on:** [sase-1se.1](sase-1se.1.md) ✓ · ⧖ 2026-11-12
- **Depends on:** [sase-1se.2](sase-1se.2.md) ✓ · ⧖ 2026-11-12
- **Depends on:** [sase-1se.3](sase-1se.3.md) ✓ · ⧖ 2026-11-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1se.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1se.4/README.md) | [sase-1se.4](sase-1se.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cb0a3c9`](https://github.com/sase-org/sase/commit/cb0a3c9a807d692e79850c62cd9b6a493bd43748) | feat(auto-restart): ratchet core pin to 47f1af1c with tests and docs | [sase-1se.4](sase-1se.4.md) | 2026-11-12 09:06:00 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1se.4][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1se.4/README.md

<!-- sase:referenced-by:end -->
