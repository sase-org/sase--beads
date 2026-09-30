# Bead: sase-1d7.1 — Remote-attention reconciler writes only the rows it changed

[Bead Pages](../README.md) / [sase-1d7](README.md) / sase-1d7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0uc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0uc.md) · **Assignee:** `sase-1d7.1` · **Size:** small
**Created:** 2026-09-30 07:18:06 EDT · **Closed:** 2026-09-30 08:13:06 EDT
**Plan:** [202609/unread\_ack\_reliability\_and\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202609/unread_ack_reliability_and_tui_responsiveness.md)

## Description

reconciler-delta-write: stop reconcile_remote_attention_inbox from handing every store row back to rewrite_notifications, and ignore per-poll observed_at churn in change detection, with a lost-update interleave regression test.

## Notes

[2026-09-30T12:13:06Z · sase-1d7.1--1] Delta-write reconciler done: reconcile_remote_attention_inbox passes only created/refreshed/auto-dismissed rows to rewrite_notifications; observed_at_unix churn ignored in change detection. Verified: 14/14 tests in tests/test_dispatch_attention_inbox.py pass (incl. 2 new regression tests), ruff + mypy clean. just check failed only in _setup plugin-install step (transient; step passes on retry, both Rust builds had succeeded).

## Dependencies

- **Blocks:** [sase-1d7.2](sase-1d7.2.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d7.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d7.1.md) | [sase-1d7.1](sase-1d7.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`279bc27`](https://github.com/sase-org/sase/commit/279bc272d17165ec8f2e44c24760a49c5954c852) | fix(dispatch): preserve concurrent dismissals in remote attention inbox reconcile | [sase-1d7.1](sase-1d7.1.md) | 2026-09-30 08:17:41 EDT |
