# Bead: sase-iy.2 — Fix the deterministic prompt-catalog convergence hang in the PNG lane

[Bead Pages](../README.md) / [sase-iy](README.md) / sase-iy.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xb](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xb/README.md) · **Assignee:** `sase-iy.2` · **Size:** medium
**Created:** 2026-08-10 11:01:31 EDT
**Plan:** [202608/retire\_sase\_ct\_umbrella.md](https://github.com/sase-org/sase--plans/blob/main/202608/retire_sase_ct_umbrella.md)

## Description

catalog: make the ACE startup prompt-catalog rebuild worker stop holding wait_for_visual_idle open for its full 30s deadline. Reproduced deterministically in isolation on clean master; fix it centrally in the visual fixtures rather than per file, and prove the PNG lane green.

## Notes

[2026-08-10T16:32:44Z · sase-iy.2] PROPOSED FOLLOW-UP: Symvision unused-public gate fails on resolve_notification_tab_icon — just check stops at lint (symvision) in untouched src/sase/ace/tui/widgets/notification_tab_style.py; decide whether to privatize/remove the API or whitelist it intentionally.

[2026-08-10T16:33:56Z · sase-iy.2] PROPOSED FOLLOW-UP: Committed plan validation fails on existing large tale plans — just validate-committed-plans reports 21 strict 202608 tale files with size=large; convert them to epics or resize to xsmall/small/medium.

## Dependencies

- **Blocks:** [sase-iy.5](sase-iy.5.md) ◐ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-iy.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-iy.2/README.md) | [sase-iy.2](sase-iy.2.md) | 0 |
