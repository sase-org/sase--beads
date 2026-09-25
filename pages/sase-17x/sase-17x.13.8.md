# Bead: sase-17x.13.8 — Border chrome and floating popup

[Bead Pages](../README.md) / [sase-17x.13](sase-17x.13.md) / sase-17x.13.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17x.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17x.land.md) · **Assignee:** `sase-17x.13.8` · **Size:** medium
**Created:** 2026-09-24 20:28:50 EDT · **Closed:** 2026-09-25 02:31:01 EDT
**Plan:** [202609/command\_line\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_landing_fixes.md)

## Description

chrome-layout: move the title, context chip, key hints and running count onto the frame borders, recomposed on resize. Float the popup over the transcript, anchored above the input at the replace-span column.

## Notes

[2026-09-25T06:29:58Z · sase-17x.13.8] PROPOSED FOLLOW-UP: just check goes red at "SASE validation" on the clean base — sase init memory --check reports sase/memory/README.md drift (+2 -2, last touched by 696026157); it blocks the test lane. Regenerate via sase init memory through /sase_memory_write.

[2026-09-25T06:30:08Z · sase-17x.13.8] PROPOSED FOLLOW-UP: command_line PNG visual tests flake under host load on the clean base — wait_for_visual_idle times out after 30s with pending_workers=[_load] (the grammar loader worker) or unstable frame digests; 2 of 2 targeted base runs failed, 12 of 16 passed in a full-file run. chrome-layout changes every command_line_* golden (borders, floating popup), so goldens-perf must regenerate them once the lane is stable; none were regenerated here.

[2026-09-25T06:30:22Z · sase-17x.13.8] PROPOSED FOLLOW-UP: border key hints render live key_display_name text (Ctrl+R search · escape hide) while the UX mock shows compact ^R search · esc hide; decide on compact key names for the one-line hints (keymap-config territory).

[2026-09-25T06:30:34Z · sase-17x.13.8] PROPOSED FOLLOW-UP: tests/completion/test_candidates_project_providers.py::test_bead_candidates_without_a_store_returns_empty_list fails on hosts with a real bead store (returns the host epics, e.g. bryan-1) — the test does not isolate the bead store from the host.

[2026-09-25T06:31:01Z · sase-17x.13.8] chrome-layout done. Title (bold gold ❯ Command Line) + context chip now sit on the frame's top border and the key hints + N running on the bottom border, composed as padded labels by the new CommandLineFrame (chrome.py) and recomposed on every frame resize; the chip is middle-truncated (middle_truncate in context.py) and the bottom hints yield to the running count. The popup card (list + footer) and the doc peek now float in one overlay-layer, bottom-docked container above the input row (screen_popup_layout.py + popup_layout.py): card width follows the widest row, the candidate text lines up under the replace-span column, and the float is clamped to the frame and re-placed on resize; opening/closing it never moves the frame or transcript. 96% width (max 160) / 65% height / ctrl+t full height kept. Also fixed a real crash found while probing: signature chips used the invalid Rich color 'dim amber', so typing any writes command (bead close, tool stop, plan approve) raised MissingStyle in the text-changed handler (now dim #FFAF00, with a Textual Content regression test). Fixed pre-existing lint left red by earlier phases so just check reaches later stages: test_policy_io _wait_for -> page.wait_for (also makes the off-thread history-store assertion wait instead of racing), symvision CdResolution/PathCompletionRequest made private. Verified: new tests/ace/tui/command_line/test_chrome_layout.py (22: pure label composition/geometry + pilot at 80/100/120/140/160/200 cols for resize alignment, border labels, no-reflow, popup column tracks replace span, clamp and re-clamp on shrink, doc peek beside card, width cap and ctrl+t); updated hint assertions now read the frame's bottom label; tests/ace/tui/command_line + palette e2e + tests/completion = 508 passed (1 unrelated host-bead-store isolation failure in tests/completion, filed as follow-up); just test-scoped 1294 passed; just fix clean; sase tool run check passes fmt/ruff/mypy/flags/pyscripts/test-waits/changelog/terminology/symvision and stops at SASE validation on a pre-existing memory README drift (filed), so validate-committed-plans and test-scoped were run by hand and passed. Scratch pilot PNG renders inspected at 120x40, 160x40 and 70x24 (empty state, tab menu, doc peek, narrow scrolling card). Docs: docs/ace.md Command Line section describes the border chrome and floating popup. Goldens NOT regenerated: the command_line PNG lane flakes on the base under host load (filed) and goldens-perf owns regeneration/live walkthrough per the plan.

## Dependencies

- **Depends on:** [sase-17x.13.5](sase-17x.13.5.md) ✓ · ⧖ 2026-09-24
- **Depends on:** [sase-17x.13.7](sase-17x.13.7.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17x.13.9](sase-17x.13.9.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.13.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.13.8/README.md) | [sase-17x.13.8](sase-17x.13.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`403586e`](https://github.com/sase-org/sase/commit/403586e27127f4a0afd6479416957b13de1bc3dd) | feat(command-line): border chrome and floating popup (sase-17x.13.8) | [sase-17x.13.8](sase-17x.13.8.md) | 2026-09-25 02:31:58 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17x.13.8][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.13.8/README.md

<!-- sase:referenced-by:end -->
