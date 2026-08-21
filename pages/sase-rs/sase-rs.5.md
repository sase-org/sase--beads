# Bead: sase-rs.5 — Beautiful Config Flags pane and controlled restart flow

[Bead Pages](../README.md) / [sase-rs](README.md) / sase-rs.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.09g](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.09g.md) · **Assignee:** `sase-rs.5` · **Size:** medium
**Created:** 2026-08-21 09:58:42 EDT · **Closed:** 2026-08-21 13:50:53 EDT
**Plan:** [202608/feature\_flag\_control\_center.md](https://github.com/sase-org/sase--plans/blob/main/202608/feature_flag_control_center.md)

## Description

tui: create the default-on sunset rollout flag and its live call site, add the lazy Config > Flags list/detail pane with filtering, provenance, removal metadata, confirmation and narrow layouts, and apply successful toggles through the existing proc-aware ACE plus AXE restart path.

## Notes

[2026-08-21T17:50:11Z · sase-rs.5] PROPOSED FOLLOW-UP: polish Config chrome docs and leftover goldens — docs/configuration.md and docs/ace.md still describe the six-child Config strip; existing Config-tab PNG goldens that show the hub strip need refresh now that Flags is default-on. Also consider updating the Config tab description ("Browse glossary, launch, …") to mention Flags when admin_center_flags is on.

[2026-08-21T17:50:27Z · sase-rs.5] PROPOSED FOLLOW-UP: unrelated just check / full-suite failures — just check is red on Symvision private imports of _load_* helpers from src/sase/finalizers/declaration.py into commit.py (not in this phase diff). Escalated full suite also reported contract_manifest 54 vs 53 budget, missing sase-xprompt-lsp, artifact doctor, skills inventory, fakey retry e2e, and finalizers_protocol_harness NameError override_flags.

[2026-08-21T17:50:53Z · sase-rs.5] Created sunset flag admin_center_flags (flag bead sase-rx) with a non-import-time Config catalog call site. When on, Config is 01 Flags through 07 XPrompts with recalibrated strip thresholds; when off, the six-child catalog and numbering are unchanged. The Flags pane loads flag_views off-thread, filters/preserves selection, paints list/detail/footer, confirms cancel-first (including self-disable recovery via sase flag enable admin_center_flags), mutates only through set_saved_feature_flag, and restarts ACE+AXE via restart_after_update_when_ready(restart_axe=True, purpose='apply feature-flag changes'). Verified both rollout states, prefix/resume fallback, mutation cancel/failure/duplicate suppression, restart queue/expiry, navigation does no state I/O, check_feature_flags, and Flags PNG goldens (120x40 light/dark, 70x32, empty, confirm). just check ruff/mypy/feature-flag/toobig/validate passed; whole-repo just check is currently blocked by unrelated Symvision private-import errors in src/sase/finalizers/declaration.py.

[2026-08-21T17:51:57Z · sase-rs.5] Created sunset flag admin_center_flags (flag bead sase-rx) with a non-import-time Config catalog call site. When on, Config is 01 Flags through 07 XPrompts with recalibrated strip thresholds; when off, the six-child catalog and numbering are unchanged. The Flags pane loads flag_views off-thread, filters/preserves selection, paints list/detail/footer, confirms cancel-first (including self-disable recovery via sase flag enable admin_center_flags), mutates only through set_saved_feature_flag, and restarts ACE+AXE via restart_after_update_when_ready(restart_axe=True, purpose='apply feature-flag changes'). Verified both rollout states, prefix/resume fallback, mutation cancel/failure/duplicate suppression, restart queue/expiry, navigation does no state I/O, check_feature_flags, and Flags PNG goldens (120x40 light/dark, 70x32, empty, confirm). just check ruff/mypy/feature-flag/toobig/validate passed; whole-repo just check is currently blocked by unrelated Symvision private-import errors in src/sase/finalizers/declaration.py.

## Dependencies

- **Depends on:** [sase-rs.3](sase-rs.3.md) ✓ · ⧖ 2026-08-21
- **Blocks:** [sase-rs.6](sase-rs.6.md) ◐ · ⧖ 2026-08-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rs.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rs.5/README.md) | [sase-rs.5](sase-rs.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b8a827b`](https://github.com/sase-org/sase/commit/b8a827bea3807b40ab11d9f61056a77c31227376) | feat(tui): add Config Flags pane with sunset rollout and ACE+AXE restart | [sase-rs.5](sase-rs.5.md) | 2026-08-21 13:54:05 EDT |
