# Bead: sase-ud.13.1.4 — Collapse the agent-list status colour ladder

[Bead Pages](../README.md) / [sase-ud.13.1](sase-ud.13.1.md) / sase-ud.13.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ud.13](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ud.13.md) · **Assignee:** `sase-ud.13.1.4` · **Size:** medium
**Created:** 2026-08-27 08:49:07 EDT · **Closed:** 2026-08-28 12:22:21 EDT
**Plan:** [202608/gate\_shell\_status\_collapse.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_shell_status_collapse.md)

## Description

ladder-collapse: fold the hand-written status branches in the agent-list row renderer into the shared pair-accent path, delete the plan-approval `status_label` plumbing that fed the optimistic overrides, drop the vestigial `MONITORED` terminal-status special case, and rebaseline the PNG goldens.

## Notes

[2026-08-28T16:22:21Z · sase-ud.13.1.4--5] Verified ladder-collapse on this tree: gate-owned agent-list status colours now come from gate_status_presentation (PLAN/TALE/EPIC/FEEDBACK/APPROVED/COMMITTED/REJECTED/QUESTION/ANSWERED/PLAN DONE/TALE DONE branches removed); WORKING PLAN/WORKING TALE kept. Plan-approval status_label plumbing and optimistic _agent_status_overrides writes are gone; the answer path requests a bounded agents refresh instead. MONITORED dropped from _TERMINAL_STATUSES. PNG goldens rebaselined for intended ladder-collapse hue changes only.

Verification: just check passed (fmt, lint, SASE validation, scoped 1306/3467 files). just check-full already passed earlier. just test-visual passed 842/1 skipped without --sase-update-visual-snapshots. Restored artifacts_beads_reopened_detail_120x40.png from HEAD after a raced unlabeled-footer capture (keys b c w z without labels vs settled `b issue · c close · w launch · z snooze`); hardened that test to wait for KeybindingFooter label "issue" and SVG sentinel "issue" before wait_for_visual_idle. No leftover --epic-symbol entries for this phase. Did not raise CPU budgets further. Parent epic sase-ud.13.1 and ancestors left open.

## Dependencies

- **Depends on:** [sase-ud.13.1.1](sase-ud.13.1.1.md) ✓ · ⧖ 2026-08-27
- **Depends on:** [sase-ud.13.1.3](sase-ud.13.1.3.md) ✓ · ⧖ 2026-08-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ud.13.1.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ud.13.1.4.md) | [sase-ud.13.1.4](sase-ud.13.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f24aed1`](https://github.com/sase-org/sase/commit/f24aed1dfa6eaad588d456b7f41270a46646ff18) | feat(ace): collapse the agent-list status colour ladder | [sase-ud.13.1.4](sase-ud.13.1.4.md) | 2026-08-28 12:23:56 EDT |
