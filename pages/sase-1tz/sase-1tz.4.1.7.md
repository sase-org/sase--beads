# Bead: sase-1tz.4.1.7 — Offer a one-key action that expires a failed blocker's waiters

[Bead Pages](../README.md) / [sase-1tz.4.1](sase-1tz.4.1.md) / sase-1tz.4.1.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.4.md) · **Assignee:** `sase-1tz.4.1.7` · **Size:** medium
**Created:** 2026-11-20 14:00:23 EST
**Plan:** [202611/hygiene\_gateway\_notifications\_retention.md](https://github.com/sase-org/sase--plans/blob/main/202611/hygiene_gateway_notifications_retention.md)

## Description

waiter_expire: under blocked_waiters = offer, the root-blocker notice gets a one-key TUI action. It expires every waiter the notice names through the existing user cancel path for a waiting agent, records the blocker as the reason, and settles the notice. Nothing expires waiters automatically.

## Notes

[2026-11-20T20:38:05Z · sase-1tz.4.1.6] From sase-1tz.4.1.6: root-blocker notice action_data contract (waiters JSON list with artifact_dir/name/project/via, blocker_* keys, wait_checks_auto_dismissed marker) is recorded as a CONTRACT note on sase-1tz.4.1.6 and in the module docstring of src/sase/scripts/_chop_wait_checks_root_notice.py.

## Dependencies

- **Depends on:** [sase-1tz.4.1.6](sase-1tz.4.1.6.md) ✓ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.4.1.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.7/README.md) | [sase-1tz.4.1.7](sase-1tz.4.1.7.md) | 0 |
