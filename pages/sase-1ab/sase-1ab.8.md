# Bead: sase-1ab.8 — Core pin bump and mirrors

[Bead Pages](../README.md) / [sase-1ab](README.md) / sase-1ab.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ss](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ss.md) · **Assignee:** `sase-1ab.8` · **Size:** medium
**Created:** 2026-09-26 00:15:14 EDT · **Closed:** 2026-09-27 06:14:44 EDT
**Plan:** [202609/sase\_turn\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_turn_rename.md)

## Description

pin-bump: move sase-core-revision.txt to the contract commit, update the Python schema-version mirrors and the fixtures and goldens that capture core output, and keep every durable legacy reader.

## Notes

[2026-09-27T10:14:03Z · sase-1ab.8] PROPOSED FOLLOW-UP: land the contract-flip core change then do the pin-bump mirrors — sase-core origin/master (fe1e065) has no flip commit; the flip sits uncommitted in the sase_41 workspace linked sase-core checkout (37 files, scan-11/index-34/proc-4, gate_turn_id, legacy bindings removed); once landed, move sase-core-revision.txt, bump mirrors AGENT_SCAN 10->11, INDEX 33->34, PROC 3->4, FLEET_PROTOCOL 2->3, LAUNCH_PLAN 2->3 plus health.py/validate probes, and flip the fleet parity/projection fixtures to agent_turn/historical_turn (they pass only with legacy spellings against pre-flip core, proven in this phase)

[2026-09-27T10:14:23Z · sase-1ab.8] PROPOSED FOLLOW-UP: run the full just check gate at landing — 4 inline attempts in this phase all died in the setup chain (cold sase_core rebuild, checkout refresh to v0.35.0, LSP server build) past the 9-minute single-turn limit; focused proof is green (145 tests across proc/launch/reconcile/scan/fleet suites, ruff+mypy+format clean, validate_sase_core_rs exit 0) but whole-repo lint gates plus diff-scoped lane never completed in-turn

[2026-09-27T10:14:44Z · sase-1ab.8] Pin-bump prerequisites verified; pin move deferred (no contract commit upstream). Fixed 3 legacy-reader corruptions from d5fc75864 that rejected proc-shell lifecycles (proc.py normalization, submission._should_reconcile, launch dispatch gate) plus 1 new regression test. Green: 145 focused tests (incl. 14 previously red launch tests), ruff+mypy+format clean, validate_sase_core_rs exit 0 against rebuilt 0.35.0 pre-flip core; fleet fixtures intentionally untouched (pass only with legacy spellings pre-flip). Full just-check left for landing (exceeds single-turn limit); 2 PROPOSED FOLLOW-UP notes recorded.

## Dependencies

- **Depends on:** [sase-1ab.7](sase-1ab.7.md) ✓ · ⧖ 2026-09-26
- **Blocks:** [sase-1ab.9](sase-1ab.9.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ab.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ab.8/README.md) | [sase-1ab.8](sase-1ab.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`25a7bd2`](https://github.com/sase-org/sase/commit/25a7bd24fef6553c4b27a19dbbf916ab9ac20c98) | fix(procs): restore legacy proc-shell readers corrupted by rename | [sase-1ab.8](sase-1ab.8.md) | 2026-09-27 06:17:52 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ab.8][1] | Need the phase scope and design file | 2 |
| read-by | [agent:sase-1ah.8.4.land][2] | Need child scope | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ab.8/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ah.8.4.land/README.md

<!-- sase:referenced-by:end -->
