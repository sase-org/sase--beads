# Bead: sase-1ux.1 — Project held staged monitors as a first-class state in sase-core

[Bead Pages](../README.md) / [sase-1ux](README.md) / sase-1ux.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1f4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1f4.md) · **Assignee:** `sase-1ux.1` · **Size:** medium
**Created:** 2026-11-22 08:33:06 EST · **Closed:** 2026-11-22 09:20:09 EST
**Plan:** [202611/failed\_clan\_visibility.md](https://github.com/sase-org/sase--plans/blob/main/202611/failed_clan_visibility.md)

## Description

core-held: in sase-core, project a staged monitor member whose `monitor_stage_held` flag is set as monitor turn state `held`. Add `NOT ADOPTED` to the status-bucket table as Failed, teach the staged-membership facts about `held`, expose a binding for Python fallback loaders, and make previously indexed held members re-project.

## Notes

[2026-11-22T14:20:09Z · sase-1ux.1] core-held done in sase-core: project_monitor_turn_state maps staged+held flag to held (flat and nested scanner paths, stale flag on other states ignored); held shares staged membership facts; NOT ADOPTED buckets as Failed; project_monitor_turn_state binding exposed; index bumped 38 to 39 with in-place record_json re-projection (sigs and fast lookups preserved). sase-core just check gate passed (STATE succeeded, EXIT 0), including new scanner, membership, status, binding, and v39 migration tests. Consumer audit: stranded classify, runner capacity/occupancy, run-state marker, fleet facts, list projection, and staged reconcile all treat held like staged; gateway has no turn-state matching. Sase-repo mirror bump to 39 and pin move left to held-state phase.

## Dependencies

- **Blocks:** [sase-1ux.2](sase-1ux.2.md) ✓ · ⧖ 2026-11-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ux.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ux.1/README.md) | [sase-1ux.1](sase-1ux.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@1fb9701`](https://github.com/sase-org/sase-core/commit/1fb9701f40b6609ec810326c0e78ee07722de26d) | feat(staged-handoff): project held staged monitors as first-class state | [sase-1ux.1](sase-1ux.1.md) | 2026-11-22 09:21:03 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ux.1][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1ux.5][2] | Check earlier phases landed | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ux.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ux.5/README.md

<!-- sase:referenced-by:end -->
