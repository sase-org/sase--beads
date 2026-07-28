# Bead: sase-93.1 — Stop the agents sidecar from blocking \`init repo --check\`

[Bead Pages](../README.md) / [sase-93](README.md) / sase-93.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-93.1` · **Size:** small
**Created:** 2026-07-25 11:27:09 UTC · **Closed:** 2026-07-25 12:31:17 UTC
**Plan:** [202607/restore\_green\_ci.md](https://github.com/sase-org/sase--plans/blob/main/202607/restore_green_ci.md)

## Description

'Phase: lint-agents-sidecar' section: make the read-only repo-init plan skip the machine-level agents sidecar when no owning SASE project key can be resolved, instead of raising a hard blocker.

## Notes

COMMIT: c442252a1

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-93.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-93.1/README.md) | [sase-93.1](sase-93.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`53d25b3`](https://github.com/sase-org/sase/commit/53d25b3173ae0df30909d3f4e256c9d4d52d08f6) | fix(init): warn instead of blocking when the agents sidecar has no project key (sase-93.1) | [sase-93.1](sase-93.1.md) | 2026-07-25 12:32:18 |
