# Bead: sase-gz.5 — Adopt the released core and verify end to end

[Bead Pages](../README.md) / [sase-gz](README.md) / sase-gz.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ui.w1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ui.w1/README.md) · **Assignee:** `sase-gz.5` · **Size:** small
**Created:** 2026-08-07 10:29:06 EDT · **Closed:** 2026-08-07 11:54:49 EDT
**Plan:** [202608/notification\_tab\_icons.md](https://github.com/sase-org/sase--plans/blob/main/202608/notification_tab_icons.md)

## Description

core-floor: raise the `sase-core-rs` floor to the release carrying the tab icon and verify a gate-declared panel icon reaches the tab strip and the indicator through the real core.

## Notes

[2026-08-07T15:54:28Z · sase-gz.5] PROPOSED FOLLOW-UP: `just check`/`sase validate` currently fail this workspace at `init memory --check` (sase/memory/README.md +2-2) and `init skills --check` (sase_gate skill wants panel_icon additions deployed to chezmoi) on a clean sync of master, confirmed via `git stash` before any of this phase's edits. Neither touches tab-icon code; the skills drift looks like it may be the docs-skill phase (sase-gz.6) deploying its chezmoi skill template early despite its plan explicitly saying not to run `sase skill init` mid-epic. Worth a look once sase-gz.6 lands to confirm whether this was transient concurrent-agent drift or a real gap.

[2026-08-07T15:54:49Z · sase-gz.5] Raised the sase-core-rs floor from >=0.19.0,<0.20.0 to >=0.19.2,<0.20.0 (pyproject.toml + uv.lock refreshed via uv lock); confirmed 0.19.2 is published on PyPI and its CHANGELOG/GitHub release carries ce8c04b 'donate a per-tab icon from the newest declaring row'. Verified the gate-declared-icon rung end to end through the real core: called classify_notification_tabs on a CustomGate notification declaring action_data={'panel': 'deployments', 'panel_icon': '🚀'} and found the Rust binding correctly returns icon in its raw payload, but src/sase/core/notification_store_wire.py's _NotificationTabWire dataclass had no icon field, so known_field_kwargs silently dropped it and notification_tabs_from_core's getattr(tab, 'icon', None) always returned None -- the sender-declared rung was dead on arrival despite icon-chain's resolve_notification_tab_icon being correct. Fixed by adding icon: str | None = None to _NotificationTabWire (mirroring color exactly), added a real-core regression test (test_a_gate_declared_panel_icon_reaches_the_classified_tab in tests/test_notification_modal_tags.py) that would have caught this, and updated the hardcoded 0.19.0 assertion in test_sase_core_rs_telemetry_smoke_tool.py to 0.19.2. Confirmed with a manual script that resolve_notification_tab_icon now resolves to the gate-declared '🚀' through the full chain. just fmt/ruff/mypy clean; full just test-scoped suite (26987 passed, 7 skipped) green. just check's SASE-validation gate still fails on two pre-existing, unrelated checks (init memory --check, init skills --check) reproduced identically on a clean stash of master before any of these changes -- recorded as a PROPOSED FOLLOW-UP note rather than fixed here since it touches protected memory/skill files outside this phase's scope.

[2026-08-07T15:55:29Z · sase-gz.5] Raised sase-core-rs floor to >=0.19.2,<0.20.0 (published on PyPI, carries tab-icon feature); fixed _NotificationTabWire missing icon field that silently dropped gate-declared panel icons; added real-core regression test; fixed stale version assertion in telemetry smoke test. just fmt/ruff/mypy clean; just test-scoped green (26,987 passed). just check's SASE-validation gate has 2 pre-existing unrelated failures (confirmed on clean master), recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-gz.1](sase-gz.1.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-gz.2](sase-gz.2.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-gz.3](sase-gz.3.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gz.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gz.5/README.md) | [sase-gz.5](sase-gz.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`94430f0`](https://github.com/sase-org/sase/commit/94430f0f945002114ee1621cc1f0f0eb2abd4477) | fix(notifications): declare icon field on \_NotificationTabWire, raise sase-core-rs floor to 0.19.2 | [sase-gz.5](sase-gz.5.md) | 2026-08-07 11:56:08 EDT |
