# Bead: sase-1h7.3 — Grammar, diagnostics, and persisted policy

[Bead Pages](../README.md) / [sase-1h7](README.md) / sase-1h7.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3v.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3v.linker.w0.md) · **Assignee:** `sase-1h7.3` · **Size:** medium
**Created:** 2026-10-06 18:17:37 EDT · **Closed:** 2026-10-06 22:33:22 EDT
**Plan:** [202610/wait\_for\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202610/wait_for_epic.md)

## Description

contract: accept and strictly validate `for_epic=` on `%wait` with identical launcher and editor errors. Compute the effective positive `wait_for_epics_of` list (default still false), persist it in agent_meta.json and waiting.json and the scan wires, round-trip it through PromptWaitDirective, and add editor completion.

## Notes

[2026-10-07T02:33:04Z · sase-1h7.3--1] PROPOSED FOLLOW-UP: just check lint-symvision still reports _runs private-import in src/sase/agents_sync/v2_snapshot_io.py and src/sase/ace/tui/widgets/decks/final/overview_card.py; both reproduce identically on the clean base tree (triage witness 05b9fc696a324977dde864aadd60a092)

[2026-10-07T02:33:22Z · sase-1h7.3--1] Verified: fixed NEW symvision private-import by renaming _durable_wait_names to public durable_wait_names; fixed missed completion assertion to include for_epic keyword; 96 targeted tests pass (wait_for_epic, directives_wait, macro contract, metadata, completion interactions); ruff, ruff format, and mypy clean on touched files; symvision shows only the 2 pre-existing base-tree _runs items (recorded as follow-up); no epic-symbol leftovers

## Dependencies

- **Depends on:** [sase-1h7.1](sase-1h7.1.md) ✓ · ⧖ 2026-10-06
- **Blocks:** [sase-1h7.5](sase-1h7.5.md) ◐ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h7.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h7.3.md) | [sase-1h7.3](sase-1h7.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@21c539f`](https://github.com/sase-org/sase-core/commit/21c539fd30aff96530611f56903c5026e70ce3c3) | feat(wait): mirror wait\_for\_epics\_of in scan wires and editor grammar (sase-1h7.3) | [sase-1h7.3](sase-1h7.3.md) | 2026-10-06 22:35:05 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h7.3--1][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h7.3.md

<!-- sase:referenced-by:end -->
