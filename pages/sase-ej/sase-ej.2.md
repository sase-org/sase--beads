# Bead: sase-ej.2 — Durable sidecar publication queue

[Bead Pages](../README.md) / [sase-ej](README.md) / sase-ej.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sh/README.md) · **Assignee:** `sase-ej.2` · **Size:** medium
**Created:** 2026-08-03 06:20:20 EDT · **Closed:** 2026-08-03 06:50:44 EDT
**Plan:** [202608/async\_sidecar\_publication.md](https://github.com/sase-org/sase--plans/blob/main/202608/async_sidecar_publication.md)

## Description

queue: generalize the agents publication outbox into a workspace-independent, per-project queue that also records pending bead-page and plan-header publication work, with enqueue, drain, quarantine, and retire semantics.

## Notes

[2026-08-03T10:50:44Z · sase-ej.2] Verified schema-v4 typed sidecar requests for agent_hood, bead_pages, plan_header, and sidecar_push; v1-v3 agent outboxes retain their logical keys; rank ordering, coalescing, attempts, quarantine, retire, acknowledge, drop, and two-process enqueue safety pass; enqueue_committed_agent_publication performs no git work; agent sync ignores non-agent requests; focused publication coverage passed (77 tests), and full just check passed.

[2026-08-03T10:51:21Z · sase-ej.2] Verified schema-v4 typed sidecar queue round trips, v1-v3 compatibility, deterministic rank ordering, lifecycle and two-process safety, no-git enqueue, non-agent sync retention, 77 focused tests, and full just check.

## Dependencies

- **Blocks:** [sase-ej.3](sase-ej.3.md) ✓
- **Blocks:** [sase-ej.4](sase-ej.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ej.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ej.2/README.md) | [sase-ej.2](sase-ej.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6e39779`](https://github.com/sase-org/sase/commit/6e397794552c9e7e8e2feb593cb57f7382fd6b37) | feat: add durable sidecar publication queue | [sase-ej.2](sase-ej.2.md) | 2026-08-03 06:53:09 EDT |
