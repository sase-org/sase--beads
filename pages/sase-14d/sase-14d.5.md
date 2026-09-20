# Bead: sase-14d.5 — sase notify rules, doctor check, and docs

[Bead Pages](../README.md) / [sase-14d](README.md) / sase-14d.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0o7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0o7.md) · **Assignee:** `sase-14d.5` · **Size:** medium
**Created:** 2026-09-20 13:11:35 EDT · **Closed:** 2026-09-20 16:52:02 EDT
**Plan:** [202609/notification\_delivery\_rules.md](https://github.com/sase-org/sase--plans/blob/main/202609/notification_delivery_rules.md)

## Description

observability: add the sase notify rules subcommand with per-notification explanation, a config.notification_rules doctor check, and the notifications docs section describing matching, resolution, and playback.

## Notes

[2026-09-20T20:50:30Z · sase-14d.5] PROPOSED FOLLOW-UP: just check is red on master at 0f5a81da70 before it reaches symvision or tests - lint (feature flags) fails with "rule 7: closed flag bead sase-12m still has a surviving service_host definition" (tools/check_feature_flags); every agent hits this gate first

[2026-09-20T20:50:59Z · sase-14d.5] PROPOSED FOLLOW-UP: just _lint-symvision fails at master 0f5a81da70 with 26 unused public symbols in files untouched by sase-14d - service/host_support.py, service/host_reporting.py, sdd/_store_clone_admission.py, sdd/_store_clone_remote.py, ace/tui/models/_agent_runner_slot_capacity.py, completion/runtime_cache_generation.py (whitelist via --epic-symbol, privatize, or delete per symvision.md)

[2026-09-20T20:51:26Z · sase-14d.5] PROPOSED FOLLOW-UP: 7 tests fail identically on clean master 0f5a81da70 (verified with git stash) in just test-scoped - tests/test_capacity_gate_to_admission.py (2, land.queue_weight is None not 2.0), tests/ace/tui/test_lazy_tier2_reconcile_apply.py::test_changed_query_incomplete_load_after_reconcile_rearms, tests/ace/tui/test_epic_panel_arrival_frames.py (4); also tests/doctor/test_checks_beads.py::test_project_beads_skips_when_store_is_absent and tests/completion/test_candidates_project_providers.py::test_bead_candidates_without_a_store_returns_empty_list fail whenever a real bead store exists in the environment

[2026-09-20T20:52:02Z · sase-14d.5] Added sase notify rules (-e/--explain ID with unique-prefix lookup, -j/--json; rules listed in evaluation order with source config layer, criteria, behaviors, and dropped entries with reasons), config.notification_rules doctor check (unknown keys, non-mapping match, malformed values, unclosed [ globs pinned to core behavior, empty criterion lists, missing sound files, no audio player, no-op rules), and the docs/notifications.md Delivery Rules section with the silence-everything-except-gates example plus cli.md/configuration.md rows. Layer provenance replays the config list merge (delivery.configured_notification_rules) and falls back to the poll's rules if it ever disagrees. Removed both sase-14d.5 epic-symbol whitelist lines (notification_delivery_rules, resolve_sound_player now have real consumers); symvision flags none of this phase's symbols and 'sase bead epic-symbols' is empty. Verified: 58+33+21 new tests plus 822 notification/doctor/completion/CLI tests pass; just check fmt/ruff/mypy/pyscripts/waits/changelog/terminology/toobig/validate/committed-plans pass; test-scoped 44130 passed. Not green, all pre-existing and reproduced on clean master 0f5a81da70: lint (feature flags) sase-12m service_host, 26 unrelated symvision symbols, 7 unrelated scoped-test failures (recorded as PROPOSED FOLLOW-UP notes). No TUI layout change, so PNG goldens untouched. Note: plan says sound.py under src/sase/notifications; it actually landed as src/sase/ace/tui/sound_playback.py (added expand_sound_path there).

## Dependencies

- **Depends on:** [sase-14d.2](sase-14d.2.md) ✓ · ⧖ 2026-09-20
- **Depends on:** [sase-14d.3](sase-14d.3.md) ✓ · ⧖ 2026-09-20
- **Depends on:** [sase-14d.4](sase-14d.4.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-14d.6](sase-14d.6.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14d.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14d.5/README.md) | [sase-14d.5](sase-14d.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`03cc36b`](https://github.com/sase-org/sase/commit/03cc36be5c6ff17474f5390ed402bc82d3a53a5d) | feat(notify): add sase notify rules, doctor check, and delivery-rules docs | [sase-14d.5](sase-14d.5.md) | 2026-09-20 16:54:29 EDT |
