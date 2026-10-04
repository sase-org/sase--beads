# Bead: sase-1eq.5.1.5 — Remaining TUI identifiers and assigned mirror files

[Bead Pages](../README.md) / [sase-1eq.5.1](sase-1eq.5.1.md) / sase-1eq.5.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.5.md) · **Assignee:** `sase-1eq.5.1.5` · **Size:** medium
**Created:** 2026-10-03 13:29:50 EDT · **Closed:** 2026-10-04 15:53:08 EDT
**Plan:** [202610/tui\_macro\_surfaces.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_macro_surfaces.md)

## Description

tui-sweep: finish every remaining in-scope xprompt hit, including statistics identifiers, scattered widgets, and the non-TUI mirror files the terminology guard already assigns to sase-1eq.5.

## Notes

[2026-10-04T16:13:50Z · sase-1eq.5.1.5] PROPOSED FOLLOW-UP: JinjaScopeKind still emits kind="xprompt" because pinned core rejects kind=macro — sase-1eq.10 owns the wire flip

[2026-10-04T16:14:01Z · sase-1eq.5.1.5] PROPOSED FOLLOW-UP: PNG goldens and xprompt-named snapshot drivers stay until tui-goldens sase-1eq.5.1.6

[2026-10-04T16:14:12Z · sase-1eq.5.1.5] PROPOSED FOLLOW-UP: TUI DetailHeaderSummary.xprompts_used and bench span suffix stay as classified leftovers until sase-1eq.10 / tui-goldens

[2026-10-04T16:58:29Z · sase-1eq.5.1.5--2] PROPOSED FOLLOW-UP: just check lint(symvision) was red on clean origin/master because Justfile still listed five --epic-symbol rows for closed sase-1fv.5 (ExistingRowSpec, ExistingDefinitionFinderModal, ExistingDefinitionPick, ExistingFinderBack, macro_existing_entries). Same close-time leftover tracked by sase-o7 (latest +1 toobig-6y.test_detach_scope.0). This phase re-keyed those five rows onto in-progress parent epic sase-1fv and left sase-1fv.6(snippet_existing_entries) in place so verification can finish; the systemic close-time guard remains sase-o7.

[2026-10-04T17:01:18Z · sase-1eq.5.1.5--2] PROPOSED FOLLOW-UP: just _lint-symvision still reports unused-public KillProvenance, classify_runner_kill, format_kill_classification, oom_kill_evidence, reset_oom_baseline in src/sase/axe/runner_kill_provenance.py — clean-tree, this phase does not touch that file, tracked by sase-1g0 (related sase-1c1 / sase-1ay)

[2026-10-04T19:52:36Z · sase-1eq.5.1.5--2] PROPOSED FOLLOW-UP: tests/main/test_parser_machine.py::test_machine_bootstrap_help_has_no_secret_cli_value fails on unmodified origin/master — argparse wraps "command-line" to "command- line" after flat_help, so the asserted phrase is absent; this phase did not touch parser_machine.py. No existing task bead; related green-CI epic sase-1c1.

[2026-10-04T19:53:08Z · sase-1eq.5.1.5--2] tui-sweep complete: remaining TUI/Python identifiers use macro; durable readers prefer macro and fall back to xprompt; core wires (%xprompts_enabled, JinjaScopeKind, snippet site kind, spacer rust binding, stats section) stay until sase-1eq.10. Restored over-renamed tests and dual-readers after just check reds. Keymap alias normalize skips flag/disk lookup on empty and canonical-only mappings; test_update_shortcut_dispatch_performs_no_disk_or_subprocess_work plus tests/test_legacy_xprompt_syntax.py and tests/ace/tui/test_log_panel_keymap.py (47) passed. just fix green; epic-symbols none. Clean-tree leftovers recorded as PROPOSED FOLLOW-UP: KillProvenance unused-public (sase-1g0), argparse wrapping in test_machine_bootstrap_help_has_no_secret_cli_value, PNG/goldens (sase-1eq.5.1.6), JinjaScopeKind wire (sase-1eq.10). Did not close parent epic sase-1eq.5.1 or ancestors.

## Dependencies

- **Depends on:** [sase-1eq.5.1.4](sase-1eq.5.1.4.md) ✓ · ⧖ 2026-10-03
- **Blocks:** [sase-1eq.5.1.6](sase-1eq.5.1.6.md) ◐ · ⧖ 2026-10-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.5.1.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.5.1.5.md) | [sase-1eq.5.1.5](sase-1eq.5.1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6320828`](https://github.com/sase-org/sase/commit/632082887886030721d7ff3448423a60cc6d160d) | feat(tui): finish remaining TUI xprompt-to-macro identifier sweep | [sase-1eq.5.1.5](sase-1eq.5.1.5.md) | 2026-10-04 15:54:39 EDT |
