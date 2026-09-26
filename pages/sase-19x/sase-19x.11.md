# Bead: sase-19x.11 — Finish card-block landing gaps

[Bead Pages](../README.md) / [sase-19x](README.md) / sase-19x.11

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-19x.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19x.land.md) · **Assignee:** `sase-19x.11.land`
**Created:** 2026-09-26 14:47:56 EDT
**Plan:** [202609/card\_block\_landing\_gaps.md](https://github.com/sase-org/sase--plans/blob/main/202609/card_block_landing_gaps.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/card_block_landing_gaps.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/card_block_landing_gaps.md

<!-- sase:links:end -->

## Description

Card-block transitions, legacy Reply visuals, navigation latency, and glossary context satisfy the remaining acceptance requirements found while landing sase-19x.

## Notes

[2026-09-26T20:56:16Z · sase-1ap.4.land] DISCOVERED ISSUE from the sase-1ap.4 landing at 752edf9fc.

(1) Commit f583cd509 (sase-19x.11.4) regenerated sase/memory/sase_beads.md and removed the creation-reason contract that sase-1ap.2 commit d588a461b had published. The template src/sase/main/init_memory/templates/memory-sase-beads.template.md still contains `-w "<why this bead was filed>"` and the paragraph that requires -w/--reason. `sase init memory --check --diff` wants sase/memory/sase_beads.md +6/−1 and the README.md line and token counts +4/−4. sase-1ap.4 is not authorized to rewrite generated memory. Restore the generated note with `sase memory init` so the checked-in bead memory matches that template.

(2) just symvision exits 1 on private _sync_scrollbar_position in src/sase/ace/tui/widgets/decks/main_view_blocks.py, imported by src/sase/ace/tui/widgets/decks/panel_transitions.py. That helper landed in bff09e3cf (sase-19x.11.1). The phase notes already call it KNOWN; at this HEAD the lint still fails the recipe. The same symvision run also reports the separate sase-1ab private import _legacy_sase_shell_syntax_enabled.

[2026-09-26T21:14:03Z · sase-19x.11.land] FOLLOW-UP TRIAGE for the close note. Landing is interrupted for a child repair epic; copy these outcomes into the sase-19x.11 close note. Do not file them again.

Verified on this tree before the repair plan: 24 passed in test_deck_block_paged_pilot.py and test_legacy_followup_reply_blocks.py, including the scrollbar sync test and both no-reshow latency tests. test_agents_deck_blocks_micro_png_snapshot passed and the golden matched. test_agents_deck_blocks_spread_landing_png_snapshot passed in 5.7s. Glossary strand Agent Data Card Block links Agent Data Card and uses glossary:sase-turn. sase bead epic-symbols sase-19x.11 lists nothing. just symvision still fails on _sync_scrollbar_position (this epic, bff09e3cf1) and _legacy_sase_shell_syntax_enabled (sase-1ab).

Integration since f583cd5097, excluding this epic's commits: 00f4975d9c is a core pin; e7dc4be959 is prompt-stash trash and does not touch decks; 7b209fc9d1 PromptsModal CSS is scoped under PromptsModal; 752edf9fc8 is created-bead Context goldens, not Reply blocks. No card-block call site in those commits needs the new helper. The one real integration break is f583cd5097 regenerating sase/memory/sase_beads.md without the creation-reason contract from sase-1ap.2. sase memory init --check --diff wants sase_beads.md +6/−1 and README.md counts +4/−4. That repair, plus making sync_scrollbar_position public, is the child epic. Do not close this bead from that child phase.

Outcomes:
- sase-19x.11.1 #1 PNG fixture agent_session failure: declined. The micro PNG test passes and the golden matches.
- sase-19x.11.1 #2 new-subject tall-to-short stale thumb: reproduced (spread, scroll_y 0, position 86). Not caused by the mode-change fix. DISCOVERED ISSUE noted on open epic sase-19x. No task.
- sase-19x.11.1 #3 and sase-19x.11.4 #1 stale --epic-symbol sase-19i.7.3.3.2(describe_node_finder_row_from_facts): declined. The Justfile entry is gone and the function is used by src/sase/ace/tui/actions/agents/_node_finder_snapshot.py. Do not delete it.
- sase-19x.11.1 #4 unscoped ~90 full-suite failures: declined as a new grab-bag. check-full was not run. The two named deck nodes were reproduced separately and routed below.
- sase-19x.11.2 #1 and sase-19x.11.3 #1 symvision: _sync_scrollbar_position stays in the repair child epic. _legacy_sase_shell_syntax_enabled is already on sase-1ab. No task.
- sase-19x.11.2 #2 AcePage spread-landing timeout: declined. The PNG test passes on this tree.
- sase-19x.11.3 #2 deck tests: test_files_ctrl_j_scrolls_page_anchor_to_top is open flake sase-1a7 (not re-run, no +1). test_files_probe_empty_kinds and test_preferred_card_and_partial_empty_body fail on AgentType.PROC_SHELL and were noted on sase-1ab. No task.
- sase-19x.11.3 #3 block-cycle bench capturing 16 to 20 of 20 keys: declined. Not a product defect. Faster cycles coalesce paints inside the 0.01s gap; the recorded in-process cycle time and the under-50ms bench bar already meet the phase.
- Epic note #1 from sase-1ap.4.land (memory drift and _sync_scrollbar_position): both are the repair child epic, not external tasks.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19x.11.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19x.11.land.md) | [sase-19x.11](sase-19x.11.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ap.4.land][1] | Need epic notes before recording the memory regression and scrollbar import | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ap.4.land/README.md

<!-- sase:referenced-by:end -->
