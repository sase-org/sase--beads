# Bead: sase-1ao.1 — Implement shared model edits and protect alternation targets

[Bead Pages](../README.md) / [sase-1ao](README.md) / sase-1ao.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1x](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.1x.md) · **Assignee:** `sase-1ao.1` · **Size:** medium
**Created:** 2026-09-26 10:14:34 EDT · **Closed:** 2026-09-26 11:21:41 EDT
**Plan:** [202609/model\_shortcut\_replacement.md](https://github.com/sase-org/sase--plans/blob/main/202609/model_shortcut_replacement.md)

## Description

core_selection: implement and test alternation-aware model and project-tag selection in sase-core, including LSP completion edits.

## Notes

[2026-09-26T15:20:59Z · sase-1ao.1] PROPOSED FOLLOW-UP: sase-core clippy gate is red on the clean base tree (7 pre-existing nonminimal_bool/manual_range_contains lints in agent_runtime, agent_scan/index/maintenance, fleet_owner_facts, provider_usage x2, tool_run/store/receipt, tool_run/store/triage); just test fully green (4509 passed) and none of the lints are in phase files

[2026-09-26T15:21:41Z · sase-1ao.1] core_selection done in sase-core: alternation-aware multi-edit model shortcut accept (earliest standalone %model/%m per --- segment wins, extras removed, trigger deleted) with compat wire (additional_edits serde-defaulted, schema v1), project_tag accept protects branch tags/refs and stays local for inside triggers, LSP primary=trigger deletion + additionalTextEdits with coincident merge, Jinja scan no longer swallows %{ alts, directive-value exclusion narrowed to glued values. Verified: just test 4509 passed/0 failed; focused core/PyO3/LSP-unit/jsonrpc-e2e all green; fmt+features clean; clippy shows only the 7 pre-existing base-tree lints (recorded as follow-up). No epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-1ao.2](sase-1ao.2.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1ao.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ao.1/README.md) | [sase-1ao.1](sase-1ao.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@e1179e6`](https://github.com/sase-org/sase-core/commit/e1179e65bacefa91593c7dfbbd5480459ecfa504) | feat(core): alternation-aware model shortcut accept with protected branch targets | [sase-1ao.1](sase-1ao.1.md) | 2026-09-26 11:23:03 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ao.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ao.1/README.md

<!-- sase:referenced-by:end -->
