# Bead: sase-110.2 — Typed sudo gate kind with the sase sudo front doors

[Bead Pages](../README.md) / [sase-110](README.md) / sase-110.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0kl](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0kl.md) · **Assignee:** `sase-110.2` · **Size:** large
**Created:** 2026-09-14 11:33:15 EDT · **Closed:** 2026-09-14 12:37:12 EDT
**Plan:** [202609/agent\_sudo\_requests.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_sudo_requests.md)

## Description

sudo-gate: register the sudo gate kind, add the sase sudo request/answer/list/show CLI group with a questions-style single-turn handoff, requires_tty option enforcement, risk badges, the batch ledger follow-up prompt, and the agent_sudo_requests beta flag.

## Notes

[2026-09-14T16:37:12Z · sase-110.2] Implemented the feature-flagged typed sudo gate and sase sudo front doors; verified with focused pytest, just _lint-symvision, just check (scoped escalated to full suite), and sase bead epic-symbols sase-110.2.

## Dependencies

- **Blocks:** [sase-110.4](sase-110.4.md) ◐ · ⧖ 2026-09-14
- **Blocks:** [sase-110.5](sase-110.5.md) ◐ · ⧖ 2026-09-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-110.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-110.2.md) | [sase-110.2](sase-110.2.md) | 0 |
