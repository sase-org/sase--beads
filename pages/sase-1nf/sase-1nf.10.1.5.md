# Bead: sase-1nf.10.1.5 — Render selected hoods and their affected browsing indexes

[Bead Pages](../README.md) / [sase-1nf.10.1](sase-1nf.10.1.md) / sase-1nf.10.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nf.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.10.md) · **Assignee:** `sase-1nf.10.1.5` · **Size:** medium
**Created:** 2026-10-20 15:40:52 EDT · **Closed:** 2026-10-20 22:05:31 EDT
**Plan:** [202610/publication\_drain\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/publication_drain_fixes.md)

## Description

payload-scope: produce targeted page payloads while preserving complete manifests and indexes, keep strict validation, reuse unchanged validated metadata within a transaction, and extend the read-only profiler.

## Notes

[2026-10-21T02:05:22Z · sase-1nf.10.1.5] PROPOSED FOLLOW-UP: test_tagged_commit_publishes_and_pushes_every_sidecar_before_returning fails identically on the clean base tree (verified via git stash: fails without these changes too) with leftover AgentPublicationOutboxItem after drain; needs a task bead for the inline drain acknowledgment path

[2026-10-21T02:05:31Z · sase-1nf.10.1.5] payload-scope landed: plan_targeted_hoods produces selected snapshots/pages plus complete manifests and root/user/machine indexes, omitting unrelated pages; publish_agent_hood routes to targeted while reconcile stays full; per-prepare shared snapshot cache with retry-pull invalidate; profiler gains read-only --hood targeted mode preserving comparison mode; 7 new regression tests in tests/agents_sync/test_publication_targeted.py pass; sase tool run check: 2426 passed, all lint gates green, single failure is test_tagged_commit_publishes_and_pushes_every_sidecar_before_returning which reproduces identically on the clean base tree (recorded as PROPOSED FOLLOW-UP)

## Dependencies

- **Depends on:** [sase-1nf.10.1.4](sase-1nf.10.1.4.md) ✓ · ⧖ 2026-10-20
- **Blocks:** [sase-1nf.10.1.6](sase-1nf.10.1.6.md) ✓ · ⧖ 2026-10-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.10.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.5/README.md) | [sase-1nf.10.1.5](sase-1nf.10.1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8c6699f`](https://github.com/sase-org/sase/commit/8c6699f413fd89607a250cb82d04cffbb9d91ae8) | feat(agents-sync): render targeted payloads for selected hoods | [sase-1nf.10.1.5](sase-1nf.10.1.5.md) | 2026-10-20 22:06:51 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nf.10.1.5][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.5/README.md

<!-- sase:referenced-by:end -->
