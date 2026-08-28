# Bead: sase-v2.2 — Gate the countdown tick on prompt typing, not just j/k

[Bead Pages](../README.md) / [sase-v2](README.md) / sase-v2.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0fe](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0fe.md) · **Assignee:** `sase-v2.2` · **Size:** small
**Created:** 2026-08-28 09:01:19 EDT · **Closed:** 2026-08-28 09:28:49 EDT
**Plan:** [202608/tui\_freeze\_regression.md](https://github.com/sase-org/sase--plans/blob/main/202608/tui_freeze_regression.md)

## Description

countdown_gate: extend the activity gate so the one-second countdown tick defers its Agents-tab repaint work while the user is typing in the prompt input, matching the documented tui_perf activity-gate rule.

## Notes

[2026-08-28T13:28:49Z · sase-v2.2] Implemented Agents-tab countdown prompt-input gate; verified .venv/bin/python -m pytest -q tests/ace/tui/test_event_handlers_nav_gate.py tests/ace/tui/test_prompt_editor_suspend.py tests/ace/tui/test_event_handlers_prompt_input_dirty_flags.py, just check, and sase bead epic-symbols sase-v2.2 reported no entries.

## Dependencies

- **Blocks:** [sase-v2.6](sase-v2.6.md) ✓ · ⧖ 2026-08-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-v2.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-v2.2/README.md) | [sase-v2.2](sase-v2.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a01d3e5`](https://github.com/sase-org/sase/commit/a01d3e56cb466e47baecf1da507a4b5e8132385e) | fix(tui): defer countdown repaint during prompt input | [sase-v2.2](sase-v2.2.md) | 2026-08-28 09:30:24 EDT |
