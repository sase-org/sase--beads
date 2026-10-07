# Bead: sase-1h9.3 — Finalizer-owned turns refuse turn-ending handoffs

[Bead Pages](../README.md) / [sase-1h9](README.md) / sase-1h9.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0xo](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0xo.md) · **Assignee:** `sase-1h9.3` · **Size:** medium
**Created:** 2026-10-07 07:52:35 EDT · **Closed:** 2026-10-07 08:08:51 EDT
**Plan:** [202610/finalizer\_repair\_hardening.md](https://github.com/sase-org/sase--plans/blob/main/202610/finalizer_repair_hardening.md)

## Description

owned-turn-handoffs: share the SASE_FINALIZER_OWNED_TURN guard that gate turns already use, refuse `sase monitor start` and the other turn-ending handoffs inside finalizer-owned turns, stop tool-run escalation from advertising a monitor join there, and stop a handoff from masking a failed finalizer as a completed run.

## Notes

[2026-10-07T12:08:23Z · sase-1h9.3] PROPOSED FOLLOW-UP: stale sase_core_rs binding breaks gate suites (content-layout schema 5 vs 7, missing normalize_macro_config_layer) — reproduces identically on clean base, blocks full just-check verification

[2026-10-07T12:08:33Z · sase-1h9.3] PROPOSED FOLLOW-UP: suppress already-spawned monitor continuation when a finalizer-turn handoff fires anyway — defense-in-depth here only names finalizer_turn_handoff and fixes the done outcome, the bogus monitor still runs

[2026-10-07T12:08:51Z · sase-1h9.3] Refusals in place (monitor start CLI+flow, pipe/plan-propose/questions via handoff guard+marker write, gate via shared check, is_joinable/escalation join suppressed) plus finalizer_turn_handoff diagnostic and failed-finalizer done-outcome guard. Verified: 13 new tests pass, gate refusal test passes, ruff+mypy clean on touched files; neighboring suite failures are pre-existing stale sase_core_rs wire errors proven identical on clean base

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h9.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h9.3/README.md) | [sase-1h9.3](sase-1h9.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9e5cc41`](https://github.com/sase-org/sase/commit/9e5cc41598ffc07e6ec725a78ec4ec8e60c25bad) | feat(finalizers): refuse turn-ending handoffs on finalizer-owned turns | [sase-1h9.3](sase-1h9.3.md) | 2026-10-07 08:10:48 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h9.3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h9.3/README.md

<!-- sase:referenced-by:end -->
