# Bead: sase-17x.13.10.1 — Bring screen\_completion.py under the line-count limit

[Bead Pages](../README.md) / [sase-17x.13.10](sase-17x.13.10.md) / sase-17x.13.10.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17x.13.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17x.13.land.md) · **Assignee:** `sase-17x.13.10.1` · **Size:** small
**Created:** 2026-09-25 08:41:40 EDT · **Closed:** 2026-09-25 09:45:37 EDT
**Plan:** [202609/command\_line\_landing\_gaps.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_landing_gaps.md)

## Description

split-completion: extract a cohesive helper module from the 1039-line `screen_completion.py` so `just lint` (toobig, enforced by the master-gate CI job) passes again, keeping symvision and import paths green.

## Notes

[2026-09-25T13:45:37Z · sase-17x.13.10.1] Split screen_completion.py (1039→681) into cd_completion.py, completion_probe.py, and screen_completion_keys.py; extras.prepend_marked_row. toobig no longer flags screen_completion; just symvision green; mypy green on the split modules; tests/ace/tui/command_line/test_completion_popup.py 31 passed. Public import sase.ace.tui.command_line.screen_completion.CommandLineScreenCompletionMixin unchanged.

## Dependencies

- **Blocks:** [sase-17x.13.10.3](sase-17x.13.10.3.md) ◐ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.13.10.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17x.13.10.1.md) | [sase-17x.13.10.1](sase-17x.13.10.1.md) | 0 |
