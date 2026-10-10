# Bead: sase-1j6.7 — One upserted ↻ notification and live report per update episode

[Bead Pages](../README.md) / [sase-1j6](README.md) / sase-1j6.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.47.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.47.linker.w0.md) · **Assignee:** `sase-1j6.7` · **Size:** medium
**Created:** 2026-10-09 15:02:07 EDT · **Closed:** 2026-10-09 20:21:52 EDT
**Plan:** [202610/update\_skew\_agent\_auto\_restart.md](https://github.com/sase-org/sase--plans/blob/main/202610/update_skew_agent_auto_restart.md)

## Description

episode-notify: replace the healer's minimal notifications with the designed experience: one upserted amber ↻ episode notification with a live ChopReport, title refresh without re-toasting, exactly one information toast, and the loud escalation copy.

## Notes

[2026-10-10T00:05:25Z · sase-1j6.7] PROPOSED FOLLOW-UP: add a decisions-web record for update-skew at-most-once pre-provider-only restarts (plan declined decision_record; land phase to reconsider)

[2026-10-10T00:05:36Z · sase-1j6.7] PROPOSED FOLLOW-UP: trigger phase (sase-1j6.6) should call refresh_episode_report on every scheduler-job settlement so the live report Now column stays live

[2026-10-10T00:05:41Z · sase-1j6.7] PROPOSED FOLLOW-UP: notification store merges neither files on upsert +1 nor via reconcile, so episode rows carry the creating agent’s files only while later agents’ evidence lives in the live report; consider a store-level file-merge if per-row files must be complete

[2026-10-10T00:16:45Z · sase-1j6.7] PROPOSED FOLLOW-UP: just check symvision stage is red on 17 pre-existing auto-restart symbols inherited unchanged from the healer-phase tree (ledger_dir, ledger_record_path, write_recovery, resolve_pending_targets, HealerTarget, SkipDecision, apply_skip_rules, ProbeResult, QuiescenceResult, AgentFailure*Wire x4, AutoRestartLedgerHistoryWire, AutoRestartProbeWire, auto_restart_recovery_is_in_flight, python_wire_schema_version); verified identical on the clean base tree via stash-and-check, needs an owner in trigger/land follow-through

[2026-10-10T00:21:52Z · sase-1j6.7] episode-notify done: one upserted amber ViewReport row per episode (create+4x +1 verified, single info toast, reconcile title refresh with stable activity cursor so no re-toast), live ChopReport at episodes/<slug>.report.json re-rendered on every notify call with live Now column, dismissed-episode rollover to #2, per-situation loud escalation copy (post-provider/already-restarted/decline via user-agent resurface, storm via agent.auto-restart ViewErrorReport at error severity), notes[0] calm-title rule enforced, sender documented in docs/notifications.md; 7 new tests pass plus healer/scan/toast suites (183 total); ruff/mypy/fmt green; only remaining check red is the 17 pre-existing symvision items verified identical on the clean base tree (recorded as follow-ups); refresh_episode_report whitelisted via --epic-symbol to still-open sase-1j6.6

## Dependencies

- **Depends on:** [sase-1j6.5](sase-1j6.5.md) ✓ · ⧖ 2026-10-09
- **Blocks:** [sase-1j6.9](sase-1j6.9.md) ◐ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1j6.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.7/README.md) | [sase-1j6.7](sase-1j6.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6baeb5c`](https://github.com/sase-org/sase/commit/6baeb5cb4c7b523bcc76f6e1e444ce1dcec05254) | feat(auto-restart): episode-notify experience with single upserted episode row and live report | [sase-1j6.7](sase-1j6.7.md) | 2026-10-09 20:23:21 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1j6.7][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.7/README.md

<!-- sase:referenced-by:end -->
