# Bead: sase-hp.3 — Target-aware \<enter\> chooser with a single-key save

[Bead Pages](../README.md) / [sase-hp](README.md) / sase-hp.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.vy](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.vy/README.md) · **Assignee:** `sase-hp.3` · **Size:** medium
**Created:** 2026-08-08 15:52:17 EDT · **Closed:** 2026-08-08 17:02:10 EDT
**Plan:** [202608/xprompt\_target\_mode.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_target_mode.md)

## Description

menu: open the submit chooser whenever the stack is multi-pane or targeted, and add the single-key "save to the targeted xprompt" and "save as a new xprompt" rows with dirty/clean-aware copy.

## Notes

[2026-08-08T21:02:10Z · sase-hp.3] Implemented target-aware Enter chooser trigger, targeted submit/save/save-as rows, clean/dirty save copy, targeted single-pane subtitle, and synced the Help Enter hint. Verified focused widget regressions with uv run pytest tests/ace/tui/widgets/test_prompt_stack_submit_cancel.py tests/ace/tui/widgets/test_prompt_stack_subtitles.py (37 passed), and just check (scoped lane escalated to full suite and passed).

[2026-08-08T21:03:51Z · sase-hp.3] Implemented and verified target-aware Enter chooser behavior; focused submit/subtitle tests passed and just check passed.

## Dependencies

- **Depends on:** [sase-hp.1](sase-hp.1.md) ✓ · ⧖ 2026-08-08
- **Blocks:** [sase-hp.5](sase-hp.5.md) ◐ · ⧖ 2026-08-08
- **Blocks:** [sase-hp.6](sase-hp.6.md) ◐ · ⧖ 2026-08-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-hp.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hp.3/README.md) | [sase-hp.3](sase-hp.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`48e8f10`](https://github.com/sase-org/sase/commit/48e8f10d3c792e027750318533a5518c94df4260) | feat(tui): add target-aware prompt submit chooser | [sase-hp.3](sase-hp.3.md) | 2026-08-08 17:05:16 EDT |
