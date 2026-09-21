# Bead: sase-14n.7 — Repair the Agents view surfaces the metadata-only default left behind

[Bead Pages](../README.md) / [sase-14n](README.md) / sase-14n.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oe](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oe.md) · **Assignee:** `sase-14n.7` · **Size:** medium
**Created:** 2026-09-20 17:14:15 EDT · **Closed:** 2026-09-21 12:18:58 EDT
**Plan:** [202609/fix\_triaged\_bug\_and\_ci\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202609/fix_triaged_bug_and_ci_beads.md)

## Description

agents_view: dispatch the zoom modal's LLM Calls visibility message and repaint the Agents header view hint on every view-picker exit path.

## Notes

[2026-09-21T16:16:59Z · sase-14n.7] PROPOSED FOLLOW-UP: just check blocked by pre-existing mypy errors in src/sase/dev_update/prebuild.py (DevCommandRunner on_output param, lines 134/162) — reproduced on clean tree without this phase's changes

[2026-09-21T16:17:39Z · sase-14n.7] PROPOSED FOLLOW-UP: agents_waiting_single_bead_labels 120x40/90x32 PNG drift (2 updated) reproduces on clean tree without this phase's changes — likely the broad drift tracked by sase-x5/sase-10u, left untouched

[2026-09-21T16:18:58Z · sase-14n.7] zoom modal dispatches LLMCallsVisibilityChanged via @on (new test test_zoom_modal_llm_calls_visibility_message_dispatches fails without it, 7/7 modal + 11/11 picker tests pass); picker dismiss callback repaints header hint on every exit path and the visual-helper workaround is removed (slow_tools/zoom_context/sase_context goldens unchanged); just _lint-symvision clean; ruff clean; remaining just-check mypy errors and waiting single-bead PNG drift both reproduce on clean tree and are recorded as follow-ups

## Dependencies

- **Depends on:** [sase-14n.1](sase-14n.1.md) ✓ · ⧖ 2026-09-20
- **Depends on:** [sase-14n.2](sase-14n.2.md) ✓ · ⧖ 2026-09-20
- **Depends on:** [sase-14n.4](sase-14n.4.md) ✓ · ⧖ 2026-09-20
- **Depends on:** [sase-14n.5](sase-14n.5.md) ✓ · ⧖ 2026-09-20
- **Depends on:** [sase-14n.6](sase-14n.6.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14n.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14n.7/README.md) | [sase-14n.7](sase-14n.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b3550b5`](https://github.com/sase-org/sase/commit/b3550b56ea3dd109249609dde848040a8a09369d) | fix(agents-view): dispatch zoom LLM Calls visibility message and repaint header hint on every picker exit | [sase-14n.7](sase-14n.7.md) | 2026-09-21 12:21:10 EDT |
