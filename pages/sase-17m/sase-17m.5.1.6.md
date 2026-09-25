# Bead: sase-17m.5.1.6 — Finish ACE agent session surfaces (ace-cutover landing gaps)

[Bead Pages](../README.md) / [sase-17m.5.1](sase-17m.5.1.md) / sase-17m.5.1.6

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.5.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.5.1.land.md) · **Assignee:** `sase-17m.5.1.6.land`
**Created:** 2026-09-25 04:39:08 EDT
**Plan:** [202609/agent\_session\_ace\_cutover\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_ace_cutover_finish.md)

## Description

The ACE agent-session cutover is complete: every non-visual test in tests/ace and tests/perf passes, no visible "family" copy for the agent-session concept remains in ACE, family-concept test identifiers in tests/ace use agent-session naming, new-shape fleet keys have fixture coverage, docs name the renamed perf scenarios and copy, the j/k benches show no regression, and `sase tool run check` passes.

## Notes

[2026-09-25T12:32:00Z · sase-17d.land] DISCOVERED ISSUE (sase-17d.land, master 8fd6a054fd, sase tool run check 3a18109b85b6805eda8d0c4c5375bc31): four non-visual tests still assert the retired 'family' spelling and fail deterministically after the ACE session rename (b79b9da246 / cdf491254c): (1) tests/test_keymaps_defaults_modes.py::test_zoom_and_agents_fold_defaults_are_in_sync_with_help expects ('z1 / z2', 'Set family level 1-2'), help now 'Set session level 1-2'; (2) tests/test_keymaps_app_bindings.py::test_h_binding_metadata_describes_navigation_and_contextual_collapse expects 'Collapse Selected Workflow/Family ...', runtime says 'Workflow/Session'; (3) tests/test_copy_agent_name.py::test_copy_agent_reference_warns_for_agent_session_container expects 'The selected family container has no agent reference', got 'session container'; (4) tests/test_dynamic_agent_session_root_zero_suffix.py::test_plan_chain_session_is_unaffected expects header 'FAMILY\nName: foo', got 'SESSION\nName: foo'. Not caused by sase-17d (deck/card epic). Node (1) is also tracked in sase-18s.

[2026-09-25T12:32:49Z · sase-17x.13.land] DISCOVERED ISSUE (sase-17x.13 land, master ea130c678, 2026-09-25): tests/ace/tui/visual/snapshots/png/agents_retry_e2e_plan_session_countdown_120x40.png is stale. ea130c678 (sase-17m.5.1.6.3) renamed the retry fixture from 'retry-family' to 'retry-session' (tests/ace/tui/_retry_agent_session_loader_fixture.py) without regenerating the golden, so a full just test-visual check at ea130c678 reports it as updated (the golden shows 'retry-family (RETRYING (9s))' / 'retry-family · 2 shells'; the render shows 'retry-session'). Regenerate it with just fix-tui-screenshots -- tests/ace/tui/visual/<retry e2e test> and inspect the diff (see sase-173 for the separate random-hex flake on these goldens).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.5.1.6.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.5.1.6.land/README.md) | [sase-17m.5.1.6](sase-17m.5.1.6.md) | 0 |
