# Bead: sase-17m.3.1.1 — Core pin bump and new binding names

[Bead Pages](../README.md) / [sase-17m.3.1](sase-17m.3.1.md) / sase-17m.3.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.3.md) · **Assignee:** `sase-17m.3.1.1` · **Size:** medium
**Created:** 2026-09-24 02:56:44 EDT · **Closed:** 2026-09-24 03:57:05 EDT
**Plan:** [202609/agent\_session\_wire\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_wire_cutover.md)

## Description

pin-bindings: ratchet sase-core-revision.txt to the landed core-expand commit, switch every caller to parse_agent_session_name, resolve_agent_session_parent, reconcile_agent_artifact_index_dismissed_agent_session_members, and fleet_followed_batch_agent_session_promotions, rename the Python facade wrappers for them, update tools/validate_sase_core_rs and the demo seed, and tighten the dual-shape directive tests to session-only.

## Notes

[2026-09-24T07:56:31Z · sase-17m.3.1.1] PROPOSED FOLLOW-UP: pre-existing mypy attr-defined error at src/sase/ace/tui/widgets/file_panel/_content.py:132 (FilePanelContentMixin has no attribute parent) fails just check on pristine tree too — blocks the pin-bindings exit gate

[2026-09-24T07:57:05Z · sase-17m.3.1.1] pin-bindings done: core pin ae9dbf6, all 4 bindings renamed (parse/resolve/reconcile/promotion) with facade wrappers, validate tool + demo seed on new spellings, directive tests session-only, exit grep clean, no epic-symbols left. Verified: just install ok, ruff/keep-sorted/fmt ok, ~690 area tests green, validate_sase_core_rs exit 0. just check red only on pre-existing mypy error in untouched file_panel/_content.py:132 (proven via stash; recorded as PROPOSED FOLLOW-UP)

## Dependencies

- **Blocks:** [sase-17m.3.1.2](sase-17m.3.1.2.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.3.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.1/README.md) | [sase-17m.3.1.1](sase-17m.3.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bb81b99`](https://github.com/sase-org/sase/commit/bb81b993a0df13a300baaa784c902d51e74201ec) | refactor(agent-session): pin core-expand bindings to agent\_session spellings | [sase-17m.3.1.1](sase-17m.3.1.1.md) | 2026-09-24 04:00:06 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.3.1.1][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-17m.3.1.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.land/README.md

<!-- sase:referenced-by:end -->
