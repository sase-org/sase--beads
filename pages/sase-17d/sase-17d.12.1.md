# Bead: sase-17d.12.1 — Make the Files deck spread live and repair the broken deck visual tests

[Bead Pages](../README.md) / [sase-17d.12](sase-17d.12.md) / sase-17d.12.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17d.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17d.land.md) · **Assignee:** `sase-17d.12.1` · **Size:** medium
**Created:** 2026-09-25 08:46:14 EDT · **Closed:** 2026-09-25 09:20:29 EDT
**Plan:** [202609/finish\_agent\_decks\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_agent_decks_landing.md)

## Description

files-spread-probe: fix DeckPanelFilesMixin.on_worker_state_changed so the Files spread probe result is applied (task sase-18m), drop the hand-fed probe from the spread-Files golden test, retarget the session fold-levels PNG test off the removed agent-xprompt anchor (task sase-18y), then regenerate and inspect every Agents-tab golden these changes move.

## Notes

[2026-09-25T13:20:29Z · sase-17d.12.1] Verified. (1) Files deck spread fixed (task sase-18m closed): on_worker_state_changed gates on WorkerState (SUCCESS applies event.worker.result; ERROR/CANCELLED clear _files_pending_probe and leave the mode alone; non-terminal and other workers ignored, no event.stop); probe worker uses exit_on_error=False so a probe error can no longer exit the app; duplicated if/pass block removed from _on_files_probe_result. The handler runs on DeckPanel because the probe worker is started by DeckPanel.run_worker and StateChanged (bubble=False) targets that node; AgentFilePanel's _fetch.py handler only sees its own workers. New tests/ace/tui/widgets/decks/test_deck_files_probe.py (14 tests, live spread pilot fails on the old code). (2) _apply_files_spread_probe deleted; agents_decks_single_files_spread_160x40 passes unchanged, 5/5 repeats. (3) Task sase-18y closed: fold-levels PNG test retargeted agent-xprompt -> agent-prompt; inspected and re-baselined agents_session_conversation_level_1/2_120x40 and agents_session_panel_level_2_120x40, and agents_session_panel_level_1_120x40 (also stale since 4af219ebae). (4) Golden sweep: ran fix-tui-screenshots --check over every test_ace_png_snapshots_agents*.py module plus llm_calls (141 tests, 176 goldens). Only the four session goldens above moved, so no golden meant to show paged Files started spreading; Files decks in external_repos, linked_repos, session panel gate/monitor already pin paged via pin_decks_paged, and the spread-Files golden is the only unpinned Files deck and is unchanged. Remaining drift is 4 nodes that reproduce identically on the clean base tree with my changes stashed: agents_decks_single_empty_120x40, agents_onboarding_120x40, agents_onboarding_no_plugins_120x40 (Command Line onboarding tip, sase-18o) and agents_retry_e2e_plan_session_countdown_120x40 (family->session rename, sase-18s); left untouched. just fix clean; sase tool run check passed (run a733236f28166b66b6d355bdf18b4969: mypy, symvision, test waits, scoped tests all green). No --epic-symbol entries for this phase.

## Dependencies

- **Blocks:** [sase-17d.12.2](sase-17d.12.2.md) ✓ · ⧖ 2026-09-25
- **Blocks:** [sase-17d.12.3](sase-17d.12.3.md) ◐ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17d.12.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17d.12.1/README.md) | [sase-17d.12.1](sase-17d.12.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`27d03a7`](https://github.com/sase-org/sase/commit/27d03a7b7224afca6a9083ea8061b9eecb34d4c9) | fix(ace-tui): apply the Files deck spread probe result (sase-17d.12.1) | [sase-17d.12.1](sase-17d.12.1.md) | 2026-09-25 09:21:27 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17d.12.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17d.12.1/README.md

<!-- sase:referenced-by:end -->
