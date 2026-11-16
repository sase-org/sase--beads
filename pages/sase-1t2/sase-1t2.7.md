# Bead: sase-1t2.7 — Real-pipeline hijack canary

[Bead Pages](../README.md) / [sase-1t2](README.md) / sase-1t2.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ct](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ct.md) · **Assignee:** `sase-1t2.7` · **Size:** medium
**Created:** 2026-11-15 20:00:10 EST · **Closed:** 2026-11-16 03:56:23 EST
**Plan:** [202611/agent\_hijack\_dependability.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack_dependability.md)

## Description

canary: a fakey end-to-end test that launches through the normal pipeline (anonymous workflow, real bootstrap, real directive extraction), asserts the real loader row gets an immediate decision, hijacks through the TUI's own submission path, asserts HIJACKED with the workspace held, runs Continue, and asserts the successor settles in the same workspace.

## Notes

[2026-11-16T08:56:23Z · sase-1t2.7--2] Closed by explicit `sase stitch create -B close` after create_commit landed 8254254e2f ("feat(agent-hijack): add real-pipeline hijack canary"). The commit author requested bead completion after verifying the bead scope. Reopen with `sase bead open sase-1t2.7` if more work remains.

## Dependencies

- **Depends on:** [sase-1t2.5](sase-1t2.5.md) ✓ · ⧖ 2026-11-15
- **Depends on:** [sase-1t2.6](sase-1t2.6.md) ✓ · ⧖ 2026-11-15
- **Blocks:** [sase-1t2.8](sase-1t2.8.md) ◐ · ⧖ 2026-11-15
- **Blocks:** [sase-1t2.9](sase-1t2.9.md) ◐ · ⧖ 2026-11-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t2.7.md) | [sase-1t2.7](sase-1t2.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8254254`](https://github.com/sase-org/sase/commit/8254254e2f61726db20f2313ce4f8afb9b7e4300) | feat(agent-hijack): add real-pipeline hijack canary | [sase-1t2.7](sase-1t2.7.md) | 2026-11-16 03:55:28 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1t2.7--2][1] | Need assigned phase scope, notes, and completion criteria after tree_drift_before_execution recovery | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t2.7.md

<!-- sase:referenced-by:end -->
