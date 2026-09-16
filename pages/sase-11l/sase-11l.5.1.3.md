# Bead: sase-11l.5.1.3 — Preview captures and confirm broad holds

[Bead Pages](../README.md) / [sase-11l.5.1](sase-11l.5.1.md) / sase-11l.5.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11l.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.5.md) · **Assignee:** `sase-11l.5.1.3` · **Size:** medium
**Created:** 2026-09-16 13:44:52 EDT · **Closed:** 2026-09-16 18:36:51 EDT
**Plan:** [202609/hold\_directive\_surface.md](https://github.com/sase-org/sase--plans/blob/main/202609/hold_directive_surface.md)

## Description

preview-confirm: list each hold and its live pending capture in launch previews. Add a capture-threshold config value, gate broad holds behind a TUI modal and a tty prompt in sase run, and document the directive in docs/xprompt.md.

## Notes

[2026-09-16T22:35:44Z · sase-11l.5.1.3--1] PROPOSED FOLLOW-UP: sase-core-rs floor pin is stale relative to published sase-core capabilities already used by this epic; bump per tools/ratchet_core_revision.

[2026-09-16T22:36:17Z · sase-11l.5.1.3--1] PROPOSED FOLLOW-UP: just check-full flake-baseline gate (selection-health --fail-on-new-flake) is red on the same 12 pre-existing reproducible flakes already reported by sase-11r.1 (test_confirmed_toggle_restarts_axe_and_suppresses_duplicates, test_visual_fixtures_embed_no_host_home_paths, test_mutex_groups_found, test_shipped_skill_source_is_discoverable_for_all_skill_providers[sase_questions-expected_phrases11], test_sdd_git_identity_survives_empty_home_subprocess, test_shell_done_marker_writers_stamp_finished_at_through_shared_helper, test_dismissed_agent_save_sites_are_reviewed, test_reviewed_dismissed_agent_save_sites_sync_projection, test_capture_config_default_and_schema, test_show_explains_claim_owner, test_grouping_cycle_palette_commands_follow_grouping_capability, test_rust_dev_install_disables_cargo_incremental_cache); none touch files this phase changed and all pass in isolation. Corroborating, not filing new beads — epic-level triage should confirm sase-11z/sase-120/sase-121 (and siblings) cover the set before landing.

[2026-09-16T22:36:51Z · sase-11l.5.1.3--1] Verified preview-confirm phase: capture-threshold config (agent_hold_confirm_capture_threshold, default 10) wired through default_config.yml/schema/_settings.py/core.py; launch_hold_preview.py predicate + _launch_hold_guard.py TUI mixin confirm broad holds (future+scope=host or pending above threshold) via ConfirmActionModal off the UI thread; sase run prompts 'Arm this hold? [y/N]' under the TTY/non-durable-proc conditions; render_launch_preview_markdown adds a Holds section; docs/xprompt.md documents syntax/semantics/beta flag/limitations. just check and just check-full both ran: all lint gates, SASE validation, committed-plans check, and the full pytest suite (test-cost) pass. sase bead epic-symbols sase-11l.5.1.3: no entries. Two pre-existing, unrelated issues recorded as PROPOSED FOLLOW-UP notes rather than fixed here: (1) sase-core-rs floor-pin staleness (collect_hold_fields/decide_gate_lifecycle/format_hold_directive/hold_fields_to_selectors published but unpinned), (2) check-full's flake-baseline gate red on the same 12 pre-existing flakes already reported by sase-11r.1, none touching this phase's diff and all passing in isolation.

## Dependencies

- **Depends on:** [sase-11l.5.1.1](sase-11l.5.1.1.md) ✓ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11l.5.1.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.5.1.3.md) | [sase-11l.5.1.3](sase-11l.5.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`43c8721`](https://github.com/sase-org/sase/commit/43c87210f5821663c21d9198865f52f02473d009) | feat(agent-hold): preview pending %hold captures and confirm broad holds | [sase-11l.5.1.3](sase-11l.5.1.3.md) | 2026-09-16 18:38:38 EDT |
