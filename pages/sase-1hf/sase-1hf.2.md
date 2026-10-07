# Bead: sase-1hf.2 — Point wait\_checks and bead\_claim\_checks at the completion pulse

[Bead Pages](../README.md) / [sase-1hf](README.md) / sase-1hf.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0y0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0y0.md) · **Assignee:** `sase-1hf.2` · **Size:** small
**Created:** 2026-10-07 14:45:44 EDT · **Closed:** 2026-10-07 15:14:38 EDT
**Plan:** [202610/wait\_lane\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202610/wait_lane_repair.md)

## Description

pulse-trigger: replace the blind ace-run/* fs glob with the per-project .ace_refresh_pulse, touch the pulse on dependency waiting-marker writes, audit done.json writers, and rewrite the trigger tests on the real YYYYMM/DD/<run> layout.

## Notes

[2026-10-07T19:14:09Z · sase-1hf.2] pulse-trigger done.json audit: every terminal-success writer already touches the project pulse — write_done_marker_and_update_index (agent runs, gate/monitor settlement, handoff, repeat-stop via run_agent_runner_repeat), runner_artifacts.write_done_marker (hook runners via runner_utils re-export), plus direct touches in plan_propose_handler, turns/handoff, gate_turn/transaction, notification decision, finalizers status_summary. run_agent_runner_finalize.write_error_done_marker writes failed outcomes only (cannot satisfy a wait: resolution needs completed/noop/epic_approved/plan_committed) so no touch needed. handoff_inflight only mutates an existing done.json (creation already pulsed). _revive_artifacts bundle-restore writes are recovery-only, not new completions; left on the max_quiet backstop. No missing touch found; no code change required by the audit.

[2026-10-07T19:14:23Z · sase-1hf.2] PROPOSED FOLLOW-UP: repo test/lint lanes are red on stale sase_core_rs binding (content-layout wire schema 5 < required 7; every load_axe_config test errors) plus 2 pre-existing symvision private-import flags in agents_sync/v2_snapshot_io.py and ace/tui/widgets/decks/final/overview_card.py — all reproduce identically on the clean base tree, none caused by pulse-trigger.

[2026-10-07T19:14:38Z · sase-1hf.2] pulse-trigger done: waits-lane triggers now watch per-project artifacts/.ace_refresh_pulse (default_config.yml + docs/configuration.md mirror); write_waiting_marker touches the pulse only for dependency-carrying payloads via new waiting_payload_has_dependencies helper; TUI wait editor touches the pulse on dep edits; done.json audit found every terminal-success writer already pulsing (no change needed); trigger tests rewritten on real ace-run/YYYYMM/DD/<run> layout (idle/done/dep-fire, slot-queue/lock-file/day-dir-skip, max_quiet intact). Verified: ruff+mypy+prettier clean, 24/24 functional checks against real writers/token pass; pytest module red identically on clean base (stale sase_core_rs binding, recorded as follow-up); epic-symbols clean.

## Dependencies

- **Blocks:** [sase-1hf.5](sase-1hf.5.md) ◐ · ⧖ 2026-10-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1hf.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1hf.2/README.md) | [sase-1hf.2](sase-1hf.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ea7d138`](https://github.com/sase-org/sase/commit/ea7d1388db061f2f4c0233e5a7dd650b292dcfb3) | fix(axe): fire wait fs triggers on dependency pulse, not artifact glob | [sase-1hf.2](sase-1hf.2.md) | 2026-10-07 15:16:35 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1hf.2][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1hf.2/README.md

<!-- sase:referenced-by:end -->
