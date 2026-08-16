# Bead: sase-nb.9 — The first two real flags

[Bead Pages](../README.md) / [sase-nb](README.md) / sase-nb.9

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03v](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03v.md) · **Assignee:** `sase-nb.9` · **Size:** medium
**Created:** 2026-08-16 12:26:24 EDT
**Plan:** [202608/feature\_flags.md](https://github.com/sase-org/sase--plans/blob/main/202608/feature_flags.md)

## Description

consumer: convert one opt-in beta env gate and one disable_* env gate into registered flags with real flag beads, and record why plugin discovery cannot be the first consumer.

## Notes

[2026-08-16T23:38:38Z · sase-nb.9] WHY NOT plugins_enabled: discover_plugin_resources("sase_config") feeds the plugin:* config layers, so a flag resolved from config cannot gate plugin discovery without a bootstrap cycle (config needs plugins, plugins would need the flag, the flag needs config). If plugins_enabled is ever wanted, it needs an explicit bootstrap scope resolved from the registry default and SASE_FEATURE_FLAGS only — a later decision, not a v1 consumer.

[2026-08-16T23:39:03Z · sase-nb.9] PROPOSED FOLLOW-UP: sase flag new printed the pre-collision id — `sase flag new coder_inherits_planner_chat` reported Created flag bead: sase-nv, but sase-nv is a pre-existing task bead and the flag bead that was actually committed is sase-nw. The returned Issue.id is the pre-commit allocation; a remint on collision is not reflected in the scaffold. Registry was corrected to sase-nw by hand.

[2026-08-16T23:40:08Z · sase-nb.9] PROPOSED FOLLOW-UP: just check is red on master HEAD before this phase — tools/check_test_wait_helpers fails tests/test_config_cache.py:622,666 and tests/test_config_cache_isolation.py:127 (fixed-sleep-missing-pragma). Confirmed with my consumer diff stashed. Also, sase-nb.7 left a stray HistoryWordCompletionMetadata = _HistoryWordCompletionMetadata alias (NameError/F811); deleted that one line so ruff could run.

## Dependencies

- **Blocks:** [sase-nb.10](sase-nb.10.md) ◐ · ⧖ 2026-08-16
- **Depends on:** [sase-nb.5](sase-nb.5.md) ✓ · ⧖ 2026-08-16
- **Depends on:** [sase-nb.6](sase-nb.6.md) ✓ · ⧖ 2026-08-16
- **Depends on:** [sase-nb.7](sase-nb.7.md) ✓ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-nb.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-nb.9/README.md) | [sase-nb.9](sase-nb.9.md) | 0 |
