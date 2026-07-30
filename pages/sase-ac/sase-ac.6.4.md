# Bead: sase-ac.6.4 — Invalidate the xprompt identity cache on project mutations

[Bead Pages](../README.md) / [sase-ac.6](sase-ac.6.md) / sase-ac.6.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ac.6.4` · **Size:** small
**Created:** 2026-07-28 13:14:50 UTC · **Closed:** 2026-07-28 13:44:00 UTC
**Plan:** [202607/xprompt\_identity\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202607/xprompt_identity_landing.md)

## Description

identity_cache: wire `project_identity`'s process-lifetime caches into the existing project mutation invalidation paths so a long-running `sase ace` does not keep resolving stale project identities.

## Notes

[2026-07-28T13:43:47Z · sase-ac.6.4] Implemented public invalidate_xprompt_project_identity() and wired it into display-name, alias, lifecycle, project-file, bare-repo, and workspace-dir mutation paths. Replaced test private cache clears with the public invalidator and added regressions for explicit invalidation, PROJECT_NAME mutation, alias mutation, and lifecycle enable after stale registry state. Also repaired the missing PROMPT backlink in plans:202607/xprompt_identity_landing.md so SASE validation passes. Verification: just install; focused identity tests pass (9 passed); adjacent catalog/alias/lifecycle/project-creation/workspace-provider/bare-git tests pass (87 passed); .venv/bin/sase validate passes; just lint passes. Ran just check twice: lint/SASE validation/committed-plans passed both times; full pytest failed on unrelated non-repeating tests (first artifacts plans filtering, then suite gate + enrich agent plan meta), and all failed node IDs passed on isolated rerun.

## Dependencies

- **Blocks:** [sase-ac.6.5](sase-ac.6.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ac.6.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ac.6.4/README.md) | [sase-ac.6.4](sase-ac.6.4.md) | 2 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`02eee83`](https://github.com/sase-org/sase/commit/02eee837542948dba30c2327120de3a9c8e6fb3d) | fix: invalidate xprompt identity on project mutations (sase-ac.6.4) | [sase-ac.6.4](sase-ac.6.4.md) | 2026-07-28 13:47:00 |
| [`sase--plans@bf8c8ed`](https://github.com/sase-org/sase--plans/commit/bf8c8ed1e585ad08d610290939cb14eb9b045b59) | docs: link xprompt identity landing prompt (sase-ac.6.4) | [sase-ac.6.4](sase-ac.6.4.md) | 2026-07-28 13:47:57 |
