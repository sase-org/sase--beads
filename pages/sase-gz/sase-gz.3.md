# Bead: sase-gz.3 — Gates must declare their panel's icon

[Bead Pages](../README.md) / [sase-gz](README.md) / sase-gz.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ui.w1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ui.w1/README.md) · **Assignee:** `sase-gz.3` · **Size:** medium
**Created:** 2026-08-07 10:28:52 EDT · **Closed:** 2026-08-07 11:16:30 EDT
**Plan:** [202608/notification\_tab\_icons.md](https://github.com/sase-org/sase--plans/blob/main/202608/notification_tab_icons.md)

## Description

gate-contract: add the required `presentation.panel_icon` gate field, project it into notification `action_data` as a protected key, and update both bead gate producers that declare `panel: beads`.

## Notes

[2026-08-07T15:15:59Z · sase-gz.3] PROPOSED FOLLOW-UP: `sase validate` fails `init skills --check` on a clean tree — the deployed chezmoi sase_gate SKILL.md copies lag the repo source from commit 7ca857a9a (+12/-2 across all five providers), so `just check` fails for reasons unrelated to any working-tree change; a `sase skill init` deploy is needed once a clean HEAD is an ancestor of the canonical branch.

[2026-08-07T15:16:14Z · sase-gz.3] SCOPE NOTE: added `sase gate create --panel-icon` (-P) beyond the plan text — the CLI has a `--panel` override, and without a matching flag that flag became unusable on its own once panel_icon became required. Documented in the parser epilog and covered by test_gate_create_presentation_overrides_reach_notification.

[2026-08-07T15:16:30Z · sase-gz.3] gate-contract landed: GATE_PANEL_ICON_ACTION_DATA_KEY + normalize_gate_panel_icon (delegating to the shared validate_icon bounds) in presentation.py and exported; validation.py requires presentation.panel_icon whenever presentation.panel is declared (missing_presentation) and adds panel_icon to the protected action_data keys; service.py projects it next to panel; snooze_gate.py and _task_gate_spec.py both declare panel_icon '◈'; added 'sase gate create --panel-icon' so the existing --panel flag stays usable. Tests: extended test_notification_gate_presentation.py (normalize accepts none/one glyph, rejects junk), test_notification_gates.py (required-when-panel, projection, panel_icon-without-panel still projects, malformed rejection, protected-key rejection), test_notification_gate_cli.py, and both bead gate tests. Verified: the 5 gate/bead test files pass (188), and 'just test-scoped' passes 5845 tests; 'just check' lint gates all pass — its only failure is the pre-existing 'init skills --check' chezmoi drift, confirmed identical on a stashed clean tree and recorded as a PROPOSED FOLLOW-UP.

[2026-08-07T15:17:02Z · sase-gz.3] Added presentation.panel_icon to the notification gate contract (normalize_gate_panel_icon + required-with-panel validation + action_data projection), declared panel_icon on the bead snooze/task gate producers, and added a -P/--panel-icon CLI override. Verified: 188 gate/bead tests pass, just test-scoped passes 5845 tests, all just check lint gates pass. Pre-existing unrelated sase validate failure (deployed chezmoi sase_gate/SKILL.md lags repo source) confirmed by stashing; recorded as a PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-gz.5](sase-gz.5.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-gz.6](sase-gz.6.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gz.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gz.3/README.md) | [sase-gz.3](sase-gz.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`61ace08`](https://github.com/sase-org/sase/commit/61ace0852e8d40a4bd99ab5b8a0ad74e2325949e) | feat(gates)!: require gates to declare their panel's icon | [sase-gz.3](sase-gz.3.md) | 2026-08-07 11:17:55 EDT |
