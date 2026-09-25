# Bead: sase-17m.5.1.6.3 — Agent-session test identifiers in top-level TUI, models, and contract tests plus new-shape fleet fixtures

[Bead Pages](../README.md) / [sase-17m.5.1.6](sase-17m.5.1.6.md) / sase-17m.5.1.6.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.5.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17m.5.1.land.md) · **Assignee:** `sase-17m.5.1.6.3` · **Size:** medium
**Created:** 2026-09-25 04:39:12 EDT · **Closed:** 2026-09-25 07:01:35 EDT
**Plan:** [202609/agent\_session\_ace\_cutover\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_ace_cutover_finish.md)

## Description

tui-tests: rename the family-concept test functions, helpers, locals, fixture kwargs, and docstrings in tests/ace/tui/*.py, tests/ace/tui/models, tests/ace/tui/artifacts_contract, and tests/ace/*.py (including _family() in _agent_enter_targets_helpers.py and owner_roster_fixture family= kwargs). Name the fleet summary and locator fixtures as legacy wire fixtures and add new-shape fleet fixture coverage that proves the new agent-session keys are read first.

## Notes

[2026-09-25T10:49:57Z · sase-17m.5.1.6.3] PROPOSED FOLLOW-UP: core/Python new-spelling mismatch for fleet keys — core validates agent_session_label (labels) and rejects top-level agent_session/agent_session_id/session_label, while models/_fleet_agents_nodes.py and _fleet_agents_identity.py read labels session_label and summary agent_session_id/agent_session; needs core-contract (sase-17m.8) alignment

[2026-09-25T11:01:35Z · sase-17m.5.1.6.3] tui-tests done: renamed family-concept test identifiers across tests/ace/tui/*.py, models, artifacts_contract, tests/ace/*.py; fleet fixtures legacy-named (legacy_family_id/legacy_family_role) with new-shape coverage proving new keys read first (nodes/rows/identity/promotion + end-to-end). sase tool run check green (lint+symvision+scoped tests). Remaining famil hits: unrelated meanings, marked legacy readers, named durable pins, opaque visual data. Follow-up noted: core/Python new-spelling mismatch (agent_session_label vs session_label).

## Dependencies

- **Depends on:** [sase-17m.5.1.6.2](sase-17m.5.1.6.2.md) ✓ · ⧖ 2026-09-25
- **Blocks:** [sase-17m.5.1.6.4](sase-17m.5.1.6.4.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.5.1.6.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.5.1.6.3/README.md) | [sase-17m.5.1.6.3](sase-17m.5.1.6.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ea130c6`](https://github.com/sase-org/sase/commit/ea130c678afbe48d0249d00311d2e4af0a5ddbf7) | feat(scope): describe the completed work | [sase-17m.5.1.6.3](sase-17m.5.1.6.3.md) | 2026-09-25 07:02:51 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.5.1.6.3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.5.1.6.3/README.md

<!-- sase:referenced-by:end -->
