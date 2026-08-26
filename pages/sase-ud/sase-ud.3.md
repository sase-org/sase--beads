# Bead: sase-ud.3 — Gate shell creation, handoff, and settlement

[Bead Pages](../README.md) / [sase-ud](README.md) / sase-ud.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0eg](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0eg.md) · **Assignee:** `sase-ud.3` · **Size:** large
**Created:** 2026-08-26 14:02:52 EDT
**Plan:** [202608/gate\_shells.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_shells.md)

## Description

gate-shell: add the additive `shell` block to the v3 gate request, create the gate-shell family member with promotion and claim transfer, hand off and kill the creator through .sase_gate_pending, run the ordered settlement, short-circuit %auto, and bound pending gate shells with a required timeout and a reclaim chop.

## Dependencies

- **Depends on:** [sase-ud.2](sase-ud.2.md) ✓ · ⧖ 2026-08-26
- **Blocks:** [sase-ud.4](sase-ud.4.md) ◐ · ⧖ 2026-08-26
- **Blocks:** [sase-ud.5](sase-ud.5.md) ◐ · ⧖ 2026-08-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ud.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ud.3.md) | [sase-ud.3](sase-ud.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1cb772d`](https://github.com/sase-org/sase/commit/1cb772d9c38e648f432460e0a097e78e4ef06df6) | feat(gate): add gate shell lifecycle | [sase-ud.3](sase-ud.3.md) | 2026-08-26 16:52:30 EDT |
