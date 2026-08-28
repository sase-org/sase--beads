# Bead: sase-ud.6 — Gate shells in ACE

[Bead Pages](../README.md) / [sase-ud](README.md) / sase-ud.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0eg](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0eg.md) · **Assignee:** `sase-ud.6` · **Size:** large
**Created:** 2026-08-26 14:02:54 EDT · **Closed:** 2026-08-26 20:56:23 EDT
**Plan:** [202608/gate\_shells.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_shells.md)

## Description

gate-tui: add the ⋔ gate glyph and legend entry, per-kind shell lanes and chips, the GATE sub-section of AGENT REPLY, the selected-gate-shell live pane, fold registration, an individual decision at each of the ten is_monitor filter sites, and PNG goldens.

## Notes

[2026-08-27T00:56:23Z · sase-ud.6] Implemented gate shell rows in ACE: gate metadata loading, family/panel lane counts, list/status rendering, prompt GATE section/live output, fold/keybinding/dismissal behavior, cleanup payload support, and PNG/unit coverage. Verified with focused gate model/widget/keybinding/dismissal suites, targeted gate PNG snapshots, contract/artifact-registry repair checks, and just check (full-suite escalation passed).

## Dependencies

- **Blocks:** [sase-ud.13](sase-ud.13.md) ✓ · ⧖ 2026-08-26
- **Depends on:** [sase-ud.4](sase-ud.4.md) ✓ · ⧖ 2026-08-26
- **Depends on:** [sase-ud.5](sase-ud.5.md) ✓ · ⧖ 2026-08-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ud.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ud.6.md) | [sase-ud.6](sase-ud.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`10d2c17`](https://github.com/sase-org/sase/commit/10d2c17a171ffff1fcf700edadc46be1e4405f2e) | feat(ace): render gate shell rows in agents tui | [sase-ud.6](sase-ud.6.md) | 2026-08-26 21:19:23 EDT |
