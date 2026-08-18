# Bead: sase-q3.4 — Configurable panel keymaps and modal footers

[Bead Pages](../README.md) / [sase-q3](README.md) / sase-q3.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.06q](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.06q.md) · **Assignee:** `sase-q3.4` · **Size:** small
**Created:** 2026-08-18 15:29:39 EDT · **Closed:** 2026-08-18 18:09:19 EDT
**Plan:** [202608/gate\_input\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_input_panel.md)

## Description

keys: add open_inputs, next_input, and previous_input to the gate keymap scope, thread the effective keys into the panel and both gate-modal footers, and keep declared gate-action keys from stealing them.

## Notes

[2026-08-18T22:00:26Z · sase-q3.4] PROPOSED FOLLOW-UP: tests/_suite_gate.py is 1197 lines and fails just check toobig (limit 1000) on an otherwise untouched tree — split or raise the tests/ toobig limit so agent just check can pass.

[2026-08-18T22:09:19Z · sase-q3.4] Added remappable gate.open_inputs/next_input/previous_input (defaults i/tab/shift+tab), threaded them into GateBranchControls + GateInputPanel + both host-modal footers, and withheld i from declared gate-action keys. Verified remapped o opens the panel and appears in both footers, remapped Ctrl+N/Ctrl+P walk the panel ring, activate_control still aliases submit_primary, and the escalated full suite passed (33759 passed). just check lint gates passed except a pre-existing toobig on untouched tests/_suite_gate.py (1197 lines).

[2026-08-18T22:10:18Z · sase-q3.4] Added remappable gate.open_inputs/next_input/previous_input (defaults i/tab/shift+tab), threaded them into GateBranchControls + GateInputPanel + both host-modal footers, and withheld i from declared gate-action keys. Verified remapped o opens the panel and appears in both footers, remapped Ctrl+N/Ctrl+P walk the panel ring, activate_control still aliases submit_primary, and the escalated full suite passed (33759 passed). just check lint gates passed except a pre-existing toobig on untouched tests/_suite_gate.py (1197 lines).

## Dependencies

- **Depends on:** [sase-q3.3](sase-q3.3.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-q3.5](sase-q3.5.md) ◐ · ⧖ 2026-08-18
- **Blocks:** [sase-q3.6](sase-q3.6.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-q3.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-q3.4/README.md) | [sase-q3.4](sase-q3.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3f913c7`](https://github.com/sase-org/sase/commit/3f913c7b29516b4db7fb686fb959da587fb15b2b) | feat(tui): add remappable gate input-panel keymaps and footer hints | [sase-q3.4](sase-q3.4.md) | 2026-08-18 18:11:08 EDT |
