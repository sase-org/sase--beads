# Bead: sase-19x.11 — Finish card-block landing gaps

[Bead Pages](../README.md) / [sase-19x](README.md) / sase-19x.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-19x.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19x.land.md) · **Assignee:** `sase-19x.11.land`
**Created:** 2026-09-26 14:47:56 EDT · **Closed:** 2026-09-26 17:45:21 EDT
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

[2026-09-26T21:45:21Z · sase-19x.11.5.land] Rechecked approved plan plan:202609/card_block_landing_gaps.md and all four closed phase beads, their notes and commits (bff09e3cf1, 37c8b79fe4, 64fae010f3, f583cd5097), plus the closed repair child sase-19x.11.5 and its two commits (e95241543d, 74c89a6385). The source retains immediate/deferred scrollbar synchronization, the legacy followup Reply phase boundary, no-reshow block cycling, and the Agent Data Card Block glossary using sase-turn wording. The repair child made the shared scrollbar helper public and regenerated bead memory to restore the creation-reason contract. Focused block and legacy Reply tests pass 24/24; the earlier parent landing verified both block PNG nodes and benchmark improvement; sase memory init --check and both linked plan validations pass. All descendants are closed; sase bead epic-symbols sase-19x.11 has no entries. The prior landing audit reviewed post-start non-epic commits 00f4975d9c, e7dc4be959, 7b209fc9d1 and 752edf9fc8; none needs a new card-block caller. The generated-memory conflict from f583cd5097 and private helper import were repaired by the child, and no non-epic commit followed the child stitches. just check passed every stage before Symvision and stopped solely on the known _legacy_sase_shell_syntax_enabled private import owned by active sase-1ab; post-close just symvision reports the same single external issue.

Follow-up outcomes from the phase notes and previous landing note: .1 #1 PNG fixture and .2 #2 AcePage timeout were declined after current targeted PNG passes; .1 #2 new-subject tall-to-short stale thumb is reproduced and recorded as a DISCOVERED ISSUE on open parent sase-19x, beyond this mode-transition scope; .1 #3 and .4 #1 stale Node Finder epic-symbol proposal was declined because the entry is gone and the function has a non-test caller; .1 #4 broad failure list was declined as an unsized grab-bag, with named cases triaged separately. .2 #1 and .3 #1 Symvision: the child resolved _sync_scrollbar_position and active sase-1ab owns the remaining private import. .3 #2 deck tests: the Ctrl+J node belongs to open flake sase-1a7, and both retired PROC_SHELL enum cases were routed to sase-1ab. .3 #3 benchmark sample-count variance was declined because coalesced paints do not affect the measured in-process cycle time or under-50ms criterion. Epic note #1 from sase-1ap.4.land is fully resolved by the repair child. The child .5.1 #1 proposed three clean-base tests: the PROC_SHELL case and schema-v3 named-proc validator expectation were corroborated on active sase-1ab, while the expanded-header scroll case was corroborated on active sase-th. No distinct unowned follow-up remains for this epic.

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
