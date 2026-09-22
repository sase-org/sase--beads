# Bead: sase-14n.15.3 — Prove the gate-shell row through the production gate creation path

[Bead Pages](../README.md) / [sase-14n.15](sase-14n.15.md) / sase-14n.15.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-14n.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-14n.land.md) · **Assignee:** `sase-14n.15.3` · **Size:** medium
**Created:** 2026-09-21 15:11:25 EDT · **Closed:** 2026-09-21 18:26:14 EDT
**Plan:** [202609/finish\_sase\_14n\_landing\_leftovers.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_sase_14n_landing_leftovers.md)

## Description

gate_row: find how a shell-block custom gate can reach create_gate without registering a row, stop that path from succeeding silently, and replace the fabricated row test with an end-to-end one.

## Notes

[2026-09-21T22:25:31Z · sase-14n.15.3] PROPOSED FOLLOW-UP: Extend the shell-row guard beyond kind=custom to built-in shell-backed kinds (sudo, plan, question, HITL, launch) and migrate their direct-create_gate tests through create_gate_shell — detail: every src caller was verified to route shell specs through the transaction or pass shell-free specs, so production is covered, but direct create_gate with a built-in shell spec still succeeds rowlessly; scoped to custom here to keep the phase medium and built-in suites green

[2026-09-21T22:26:14Z · sase-14n.15.3] Bypass reproduced then closed: direct create_gate with shell-block custom spec recorded gate_shell with no row; now raises missing_gate_shell_row naming create_gate_shell. E2E via real create_gate_shell in temp home/project asserts mode gate_shell, member row exists, list_gate_shells and sase gate list --all --json return it. Finding: CLI shell-routing predates c04171670, so the historic rowless gate came from direct create_gate or listing-side filters (terminal hidden without --all, wrong project), not the old none default via CLI. Verified: new e2e + bypass tests plus settlement/detach/conformance/fakey/sudo/question suites green; sase tool run check 4538 passed with only 3 failures proven pre-existing on the clean tree (bead free-text classification, question-pane footer, core-rs bindings). Guard scoped to kind=custom; built-in extension left as PROPOSED FOLLOW-UP note.

## Dependencies

- **Depends on:** [sase-14n.15.1](sase-14n.15.1.md) ✓ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14n.15.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14n.15.3/README.md) | [sase-14n.15.3](sase-14n.15.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c6807d2`](https://github.com/sase-org/sase/commit/c6807d24cb3847ced1af4487637448fa35858f19) | fix(gate): refuse rowless shell-block custom gates and prove the row end to end | [sase-14n.15.3](sase-14n.15.3.md) | 2026-09-21 18:27:49 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-14n.15.3][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-14n.15.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14n.15.3/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14n.15.land/README.md

<!-- sase:referenced-by:end -->
