# Bead: sase-1h3.1 — Legacy instruction renderer exposes structured, cwd-free memory units

[Bead Pages](../README.md) / [sase-1h3](README.md) / sase-1h3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0xc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0xc.md) · **Assignee:** `sase-1h3.1` · **Size:** medium
**Created:** 2026-10-06 12:43:25 EDT · **Closed:** 2026-10-06 13:40:28 EDT
**Plan:** [202610/e2\_instruction\_bundles\_shadow\_mode.md](https://github.com/sase-org/sase--plans/blob/main/202610/e2_instruction_bundles_shadow_mode.md)

## Description

memory-units: refactor the legacy AGENTS.md renderer onto a structured, side-effect-free per-root units API (title, contract inputs, core, reference, and web units with sources), threading the project root through hidden cwd reads; legacy output stays byte-identical.

## Notes

[2026-10-06T17:40:07Z · sase-1h3.1--1] PROPOSED FOLLOW-UP: symvision flags private _runs in src/sase/agents_sync/v2_snapshot_io.py and src/sase/ace/tui/widgets/decks/final/overview_card.py as imported by non-test files (triage witness 48f36c668a00e9661681cf4de3ff932a, no owner); reproduces identically on clean base HEAD 9e4b9767d2, unrelated to memory-units — triage to owning bead or make public

[2026-10-06T17:40:28Z · sase-1h3.1--1] memory-units done: new amd/memory_units.py units API (title/contract/core/reference/web) threaded off hidden cwd reads, legacy render byte-identical; 25/25 targeted tests pass incl legacy-parity and cwd-independence; just check green except 2 symvision _runs flags that reproduce identically on clean base HEAD 9e4b9767d2 (recorded as PROPOSED FOLLOW-UP, witness 48f36c66); no epic-symbol leftovers

## Dependencies

- **Blocks:** [sase-1h3.3](sase-1h3.3.md) ✓ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h3.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h3.1.md) | [sase-1h3.1](sase-1h3.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ed2a8f7`](https://github.com/sase-org/sase/commit/ed2a8f78ad273cf6dccb40b5c041e77e2f70976a) | feat(instructions): expose structured cwd-free memory units for legacy renderer | [sase-1h3.1](sase-1h3.1.md) | 2026-10-06 13:41:54 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h3.1--1][1] | Verify phase completion and notes before close | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h3.1.md

<!-- sase:referenced-by:end -->
