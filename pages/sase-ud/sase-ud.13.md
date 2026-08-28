# Bead: sase-ud.13 — Collapse the status machinery and remove the flag

[Bead Pages](../README.md) / [sase-ud](README.md) / sase-ud.13

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0eg](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0eg.md) · **Assignee:** `sase-ud.13` · **Size:** large
**Created:** 2026-08-26 14:02:59 EDT · **Closed:** 2026-08-28 13:08:14 EDT
**Plan:** [202608/gate\_shells.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_shells.md)

## Description

status-collapse: fold the flat monitor_* and gate_* wire blocks into one nested family_shell record at wire schema v7, retire the notification status overrides, family status predicates, synthetic planner children, and colour-ladder branches after pinning their accents, and remove the beta flag.

## Notes

[2026-08-28T17:09:37Z · sase-ud.13.1.land--1] LAND VERIFICATION (sase-ud.13.1 land agent): this phase closed automatically when its only child epic sase-ud.13.1 closed ("delegated work landed"), so this note records the verification that would have gone in the close note. Every item in this phase description is done on the tree at f24aed1df: the flat monitor_*/gate_* wire blocks are folded into one nested FamilyShellWire record at AGENT_SCAN_WIRE_SCHEMA_VERSION 7 on both the Python and Rust sides, with family_shell_from_mapping as the single flat/nested compatibility projection and pinned core 6ac162e09 (v0.32.12) containing it; the notification status overrides (_notification_status_overrides.py, models/_agent_status_overrides.py, _agent_pre_question_status) are gone; _agent_status_family_policy.py keeps only the concrete post-gate handoff labels whose reachability rationale is recorded on sase-ud.13.1.3; every synthetic-planner child symbol is absent; the agent-list colour ladder is collapsed so all gate-owned statuses resolve through gate_status_presentation; the plan and epic gate accents are pinned against the ladder table by tests/plan_shell/test_create.py; and the gate_shell_handoff beta flag with its blocking Off branch is removed (gate_shell/flag.py, FeatureFlag.gate_shell_handoff, the config schema property, handle_plan_approval, create_plan_approval_gate, run_agent_helpers_questions.py, create_user_question_gate). Verification: just check exit 0 and just check-full exit 0 in 18m56s (monitor 7pvnmzt53w49) — all lint gates, the full pytest suite, committed plans, test cost, and flake baseline green, with only advisory wall-clock cost overages (tracked by sase-j0). sase bead epic-symbols sase-ud.13 reports no entries and just symvision is clean; the two surviving --epic-symbol entries belong to still-open beads sase-n4 and sase-ud. Grandparent epic sase-ud is intentionally left to its own land agent.

## Dependencies

- **Depends on:** [sase-ud.12](sase-ud.12.md) ✓ · ⧖ 2026-08-26
- **Blocks:** [sase-ud.14](sase-ud.14.md) ✓ · ⧖ 2026-08-26
- **Depends on:** [sase-ud.6](sase-ud.6.md) ✓ · ⧖ 2026-08-26
- **Depends on:** [sase-ud.9](sase-ud.9.md) ✓ · ⧖ 2026-08-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ud.13](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ud.13.md) | [sase-ud.13](sase-ud.13.md) | 0 |
