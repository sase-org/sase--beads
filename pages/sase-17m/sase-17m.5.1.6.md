# Bead: sase-17m.5.1.6 — Finish ACE agent session surfaces (ace-cutover landing gaps)

[Bead Pages](../README.md) / [sase-17m.5.1](sase-17m.5.1.md) / sase-17m.5.1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.5.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.5.1.land.md) · **Assignee:** `sase-17m.5.1.6.land`
**Created:** 2026-09-25 04:39:08 EDT · **Closed:** 2026-09-25 13:27:58 EDT
**Plan:** [202609/agent\_session\_ace\_cutover\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_ace_cutover_finish.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:c1b4bdfa5d04bf58b7338f83 | attached via sase artifact create --bead |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

<!-- sase:links:end -->

## Description

The ACE agent-session cutover is complete: every non-visual test in tests/ace and tests/perf passes, no visible "family" copy for the agent-session concept remains in ACE, family-concept test identifiers in tests/ace use agent-session naming, new-shape fleet keys have fixture coverage, docs name the renamed perf scenarios and copy, the j/k benches show no regression, and `sase tool run check` passes.

## Notes

[2026-09-25T12:32:00Z · sase-17d.land] DISCOVERED ISSUE (sase-17d.land, master 8fd6a054fd, sase tool run check 3a18109b85b6805eda8d0c4c5375bc31): four non-visual tests still assert the retired 'family' spelling and fail deterministically after the ACE session rename (b79b9da246 / cdf491254c): (1) tests/test_keymaps_defaults_modes.py::test_zoom_and_agents_fold_defaults_are_in_sync_with_help expects ('z1 / z2', 'Set family level 1-2'), help now 'Set session level 1-2'; (2) tests/test_keymaps_app_bindings.py::test_h_binding_metadata_describes_navigation_and_contextual_collapse expects 'Collapse Selected Workflow/Family ...', runtime says 'Workflow/Session'; (3) tests/test_copy_agent_name.py::test_copy_agent_reference_warns_for_agent_session_container expects 'The selected family container has no agent reference', got 'session container'; (4) tests/test_dynamic_agent_session_root_zero_suffix.py::test_plan_chain_session_is_unaffected expects header 'FAMILY\nName: foo', got 'SESSION\nName: foo'. Not caused by sase-17d (deck/card epic). Node (1) is also tracked in sase-18s.

[2026-09-25T12:32:49Z · sase-17x.13.land] DISCOVERED ISSUE (sase-17x.13 land, master ea130c678, 2026-09-25): tests/ace/tui/visual/snapshots/png/agents_retry_e2e_plan_session_countdown_120x40.png is stale. ea130c678 (sase-17m.5.1.6.3) renamed the retry fixture from 'retry-family' to 'retry-session' (tests/ace/tui/_retry_agent_session_loader_fixture.py) without regenerating the golden, so a full just test-visual check at ea130c678 reports it as updated (the golden shows 'retry-family (RETRYING (9s))' / 'retry-family · 2 shells'; the render shows 'retry-session'). Regenerate it with just fix-tui-screenshots -- tests/ace/tui/visual/<retry e2e test> and inspect the diff (see sase-173 for the separate random-hex flake on these goldens).

[2026-09-25T13:58:12Z · sase-17m.5.1.6.land] LANDING PAUSED (sase-17m.5.1.6.land): audited all four closed phases and their notes, read the implementation and commits cdf491254c, d039244c00, ea130c678a, 24615e18d4. Copy assertions from epic note #1 were fixed by 24615e18d4; source composition uses session and docs/perf scenarios match. New-shape fleet precedence tests exist. Remaining epic-caused work from note #2: ea130c678a renamed the retry fixture to retry-session, but test_real_loader_plan_agent_session_retry_countdown_png_snapshot still queries retry-family and its golden still depicts the old name. Planned only this repair as sase_plan_retry_session_visual_gap.md (parent_bead this epic); this workspace lacks textual, so targeted visual execution belongs to that phase after install. FOLLOW-UP OUTCOMES: 5.1.6.2#2 three onboarding/decks goldens routed as DISCOVERED ISSUE on active command-line child epic sase-17x.13.10, whose golden phase owns onboarding; the fourth single-glyph fleet_followed_partial_offline observation noted on existing visual-drift task sase-x5 without asserting a shared cause or accepting pixels. 5.1.6.3#1 core/Python fleet-key mismatch routed to core-contract phase sase-17m.8. 5.1.6.4#1 selected-tribe timing corroborated on sase-lx (+1); other clan/Fleet/Axe latency misses matched pre-epic under load and yielded no isolated product regression, so no separate latency task until controlled evidence exists. 5.1.6.4#2 Axe sample-window assertion filed as ready task sase-199, related to but distinct from sase-lx. Post-start non-epic commits 4fb63b05a1/15fa5cd796 (net revert), 8fd6a054fd (decks/docs), 245dcb5536, 7757bacc9d, 27d03a7b72 (Files deck/session goldens), 43f724619f (bead previews) were reviewed; the overlapping ACE docs and session-panel changes show no further rename integration need. sase bead epic-symbols reports none. Do not close until the child plan lands and just check verifies.

[2026-09-25T17:27:58Z · sase-17m.5.1.6.5.land--1] Verified parent epic sase-17m.5.1.6 is complete after child sase-17m.5.1.6.5 closed.

Children: 5.1.6.1-4 closed previously; 5.1.6.5 closed done (ced0b15e0: retry-session query+golden, no retry-family left). Note #1 copy pins fixed by 24615e18d4; note #2 visual gap fixed by the child. Prior follow-ups already routed (sase-17x.13.10, sase-x5, sase-17m.8, sase-lx, sase-199). Child 5.1.6.5.1 follow-ups (not epic-caused): +1 sase-12f, created ready flake tasks sase-19c and sase-19d.

Integration: post-pause ACE commits (waiting chip 8e82089e8, deck picker ce1336eec, note wrap 204a4993e, command-line ea25ee2bf) add no agent-family copy. Four origin-only commits since HEAD (4e18680d3 zero-weight, 0b70c2c3d xprompt card, 7a5559cc7 note preview, e01d34651 command-line) already use agent-session naming; no remaining integration.

just check (monitor 4s0jgas16mkg, tool 5534b3088505fbef) timed out at 1h during test (scoped) under load1 30-47; fmt/lint/mypy/symvision/SASE validation all passed; tests were SIGKILL incomplete, not a failed assertion. Equivalent isolation-pass contention (sase-12f / sase-19c / sase-19d), not remaining epic work. sase bead epic-symbols reported none.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.5.1.6.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.5.1.6.land.md) | [sase-17m.5.1.6](sase-17m.5.1.6.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.5.1.6.5.land--1][1] | Need parent epic scope, children, parent_bead, and notes after child close | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.5.1.6.5.land.md

<!-- sase:referenced-by:end -->
