# Bead: sase-1rg.3 — Scope monitor retention evidence to the monitor's own workspace

[Bead Pages](../README.md) / [sase-1rg](README.md) / sase-1rg.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.cp--5` · **Assignee:** `sase-1rg.3` · **Size:** medium
**Created:** 2026-11-06 05:46:49 EST · **Closed:** 2026-11-06 07:26:07 EST
**Plan:** [202611/agent\_health\_watch\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_health_watch_fixes.md)

## Description

retain-scope: stop epic-launch monitors from probing the plan agent's former workspace during terminal retention, and fix the swallowed Workspace held notification.

## Notes

[2026-11-06T12:26:07Z · sase-1rg.3] retain-scope done: starter evidence folds in only for same-workspace starters (workspace_num/checkout match), foreign starter records outside the monitor checkout are dropped, baselines merge from both dirs (monitor wins), is_primary only for the monitor checkout, diff snapshots keyed by repo id + path hash, and notify_retained_workspace passes plus_one_note/timestamp so the Workspace-held notice stores. Verified: 3 new lifecycle tests + snapshot disambiguation test + real-store notification test (replacing the mock) all pass; full retention/turns suites green (101 + 45 + 17); sase tool run check run 7db9a90d4061f4d36026bde570a5ccac STATE succeeded with all lint gates and 328 scoped test files green.

## Dependencies

- **Blocks:** [sase-1rg.5](sase-1rg.5.md) ✓ · ⧖ 2026-11-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rg.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rg.3/README.md) | [sase-1rg.3](sase-1rg.3.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1rg.3][1] | Need full scope including notes and design | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rg.3/README.md

<!-- sase:referenced-by:end -->
