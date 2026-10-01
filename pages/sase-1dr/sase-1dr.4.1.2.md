# Bead: sase-1dr.4.1.2 — Version classes, summaries, and commit provenance

[Bead Pages](../README.md) / [sase-1dr.4.1](sase-1dr.4.1.md) / sase-1dr.4.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1dr.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1dr.4.md) · **Assignee:** `sase-1dr.4.1.2` · **Size:** medium
**Created:** 2026-09-30 20:38:53 EDT · **Closed:** 2026-09-30 22:01:22 EDT
**Plan:** [202609/memory\_history\_core.md](https://github.com/sase-org/sase--plans/blob/main/202609/memory_history_core.md)

## Description

classify: assign every committed version a class, a hidden-by-default bit, a summary, a sparkline volume, and footer provenance from prose_diff stats and the commit message.

## Notes

[2026-10-01T02:00:38Z · sase-1dr.4.1.2] PROPOSED FOLLOW-UP: sase tool run check in sase-core fails on 9 pre-existing clippy lints (nonminimal_bool, collapsible_match, manual_range_contains) in agent_runtime, agent_scan, finalizer, fleet_owner_facts, provider_usage, tool_run — reproduced identically on clean base tree via just clippy; memory_history files are clippy-clean

[2026-10-01T02:01:22Z · sase-1dr.4.1.2] classify.rs fills class/hidden/summary/volume/provenance/boilerplate plus memory-source cause witnesses for all corpus versions; 13/13 memory_history tests pass (7 new), just fast + fmt-check green, new files clippy-clean; full check blocked only by 9 pre-existing clippy lints reproduced on clean base (recorded as follow-up)

## Dependencies

- **Depends on:** [sase-1dr.4.1.1](sase-1dr.4.1.1.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1dr.4.1.3](sase-1dr.4.1.3.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1dr.4.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.4.1.2/README.md) | [sase-1dr.4.1.2](sase-1dr.4.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@1c49a65`](https://github.com/sase-org/sase-core/commit/1c49a650c66f5ad05e3c860549abecffe1bc6789) | feat(memory-history): add subject classifier with priority list and summary | [sase-1dr.4.1.2](sase-1dr.4.1.2.md) | 2026-09-30 22:04:25 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1dr.4.1.2][1] | Need the phase scope and design file | 2 |
| read-by | [agent:sase-1dr.4.1.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.4.1.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.4.1.land/README.md

<!-- sase:referenced-by:end -->
