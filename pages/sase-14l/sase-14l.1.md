# Bead: sase-14l.1 — Rust store matches row-owned settlement notifications

[Bead Pages](../README.md) / [sase-14l](README.md) / sase-14l.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.17](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.17.md) · **Assignee:** `sase-14l.1` · **Size:** small
**Created:** 2026-09-20 16:56:55 EDT · **Closed:** 2026-09-20 17:13:20 EDT
**Plan:** [202609/epic\_launch\_read\_dismiss.md](https://github.com/sase-org/sase--plans/blob/main/202609/epic_launch_read_dismiss.md)

## Description

core-match: teach the notification store's agent-keyed dismissal to match host-owned settlement rows by exact (cl_name, raw_suffix), with parity tests that pin the exact-match requirement.

## Notes

[2026-09-20T21:13:20Z · sase-14l.1] Added matches_agent_settlement_notification(_for_agents) in sase-core notifications/store.rs (exact (cl_name, raw_suffix), no cl_name fallback) and wired it into the DismissAgentCompletionsMatchingAgents arm; 3 new parity tests in notification_store_parity.rs; cargo fmt clean, notification_store_parity 62 passed, core just check rc=0. sase-core-revision.txt untouched; pin move belongs to sase-14l.2.

## Dependencies

- **Blocks:** [sase-14l.2](sase-14l.2.md) ◐ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-14l.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-14l.1/README.md) | [sase-14l.1](sase-14l.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@1655a12`](https://github.com/sase-org/sase-core/commit/1655a1298fc99a906d1c0ae9607b8a142aec08e8) | feat(notifications): dismiss row-owned settlement rows by exact agent key | [sase-14l.1](sase-14l.1.md) | 2026-09-20 17:14:43 EDT |
