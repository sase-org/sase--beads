# Bead: sase-1vh.1 — Opt-in busy patience at the lookup facades, installed by the agent runner

[Bead Pages](../README.md) / [sase-1vh](README.md) / sase-1vh.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1gu](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1gu.md) · **Assignee:** `sase-1vh.1` · **Size:** medium
**Created:** 2026-11-26 14:45:31 EST · **Closed:** 2026-11-26 16:21:33 EST
**Plan:** [202611/launch\_lookup\_busy\_resilience.md](https://github.com/sase-org/sase--plans/blob/main/202611/launch_lookup_busy_resilience.md)

## Description

runner-lookup-patience: add a process-wide LookupPatience policy and retry_while_busy helper, wrap the artifact and dismissed-bundle lookup facades so busy-incomplete results retry with capped backoff under patience, install it in the agent runner entry with concise retry log lines, and test the default single-attempt path stays unchanged.

## Notes

[2026-11-26T21:21:33Z · sase-1vh.1] Implemented opt-in 60s busy lookup patience for artifact and dismissed-bundle facades, installed it in the agent runner, and added injected-clock, facade, named/group lookup, and runner logging tests. Focused tests passed (39 tests, then 14 changed-helper/runner tests). sase tool run check passed (exit 0; scoped tests escalated to and passed the full suite). git diff --check passed; no epic symbols remain.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vh.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vh.1/README.md) | [sase-1vh.1](sase-1vh.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`47605d5`](https://github.com/sase-org/sase/commit/47605d5cb53a420e22998d9c3a6e2072101eb723) | feat(agent-runner): retry busy index lookups during launches | [sase-1vh.1](sase-1vh.1.md) | 2026-11-26 16:23:41 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1vh.1][1] | Need the phase scope, notes, epic decisions, and design file before completing the assigned phase | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vh.1/README.md

<!-- sase:referenced-by:end -->
