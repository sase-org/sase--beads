# Bead: sase-1j6.8 — Agents-tab ↻ RESTARTING state, provenance line, help, and update hint

[Bead Pages](../README.md) / [sase-1j6](README.md) / sase-1j6.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.47.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.47.linker.w0.md) · **Assignee:** `sase-1j6.8` · **Size:** medium
**Created:** 2026-10-09 15:02:07 EDT · **Closed:** 2026-10-09 20:33:20 EDT
**Plan:** [202610/update\_skew\_agent\_auto\_restart.md](https://github.com/sase-org/sase--plans/blob/main/202610/update_skew_agent_auto_restart.md)

## Description

ux-surfaces: render in-flight recoveries as amber ↻ RESTARTING with a dim reason, add decline hints and the replacement's ↻ provenance line with its preserved error report as a `v` file hint, and update the help modal and the `sase update` advisory hint, with visual snapshots.

## Notes

[2026-10-10T00:33:06Z · sase-1j6.8] PROPOSED FOLLOW-UP: decisions-web record declined per epic plan (update-skew restarts at most once per lineage, pre-provider only, signature/witness/probe gated) — record decisions:update-skew-auto-restart with claim, rejected alternatives, cost, and reopen condition

[2026-10-10T00:33:11Z · sase-1j6.8] PROPOSED FOLLOW-UP: symvision unused-public failures reproduce identically on clean base (write_recovery, apply_skip_rules, resolve_pending_targets, SkipDecision, HealerTarget, AgentFailure*Wire, AutoRestart*Wire, ProbeResult, QuiescenceResult, python_wire_schema_version, ledger_dir, ledger_record_path, episode_dedup_key from healer/scan/core-verdict phases) — privatize or wire epic-symbol rows for the still-open 1j6.6/1j6.7 consumers

[2026-10-10T00:33:20Z · sase-1j6.8] ux-surfaces done: RESTARTING status via done-wire loaders (snapshot+filesystem), amber row with dim hints, declined/stale FAILED hints, replacement chip + provenance block + error_report v hint, help legend rows, sase update hint (CLI+TUI) gated on enabled+holders, UPDATE_RECOVERY_GLYPH. Verified: 19/19 new ux tests, 155 related, 1289 widget, 172 keymaps/dev-update pass; ruff+mypy+12 other check stages pass; 2 visual goldens created+inspected (rows, provenance); symvision NEWs reproduce identically on clean base (recorded as follow-up). No epic-symbols for this bead.

## Dependencies

- **Depends on:** [sase-1j6.5](sase-1j6.5.md) ✓ · ⧖ 2026-10-09
- **Blocks:** [sase-1j6.9](sase-1j6.9.md) ✓ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1j6.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.8/README.md) | [sase-1j6.8](sase-1j6.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a58036d`](https://github.com/sase-org/sase/commit/a58036da0dec25b28396ed7150696e3b125ec019) | feat(auto-restart): Agents-tab RESTARTING state, provenance line, help, and update hint | [sase-1j6.8](sase-1j6.8.md) | 2026-10-09 20:35:13 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1j6.8][1] | Need full bead incl notes | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.8/README.md

<!-- sase:referenced-by:end -->
