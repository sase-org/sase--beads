# Bead: sase-e7.3 — Make agent prompts migrate correct and durable

[Bead Pages](../README.md) / [sase-e7](README.md) / sase-e7.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rt](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rt/README.md) · **Assignee:** `sase-e7.3` · **Size:** medium
**Created:** 2026-08-02 13:28:45 UTC · **Closed:** 2026-08-02 14:21:37 UTC
**Plan:** [202608/finish\_dh\_canonical\_archive.md](https://github.com/sase-org/sase--plans/blob/main/202608/finish_dh_canonical_archive.md)

## Description

migrate-durability: resolve the plans sidecar effective for the caller instead of the first existing clone, and make a write run either publish both sidecars or fail with exact recovery instructions, with restart states tested.

## Notes

[2026-08-02T14:02:07Z · sase-e7.3] PROPOSED FOLLOW-UP: Harden contention-sensitive full-suite tests — under several concurrent host test runs, just check failed fs-watcher coalescing, the retry-countdown PNG snapshot, and the bead lock-wait regression; all three passed immediately when rerun in isolation.

[2026-08-02T14:21:28Z · sase-e7.3] FOLLOW-UP EVIDENCE: A later full run under a competing 27-worker holder also flaked artifact-modal copy, retry-wait kill, and the same bead contention test; all three passed immediately in isolation (3 passed in 7.03s).

[2026-08-02T14:21:37Z · sase-e7.3] Implemented caller-effective plans-sidecar selection using checkout-marker/workspace clone identity; migrate --write now synchronously publishes both agents and plans sidecars, detects restart-pending migration commits, remains dry-run/read-only and idempotent, and emits exact remaining push plus rerun commands after partial publication. Verified caller clone selection, pre-existing archive/remaining snapshot, one-side committed, one-side pushed, and fully migrated no-op restart states; 22 focused archive/handler tests pass, Ruff and mypy pass, and a complete just check passed. Subsequent host-contended full runs had only unrelated timing flakes, all reproduced failures passed immediately in isolation and were recorded as proposed follow-up evidence.

[2026-08-02T14:23:04Z · sase-e7.3] Verified caller-workspace plans resolution, synchronous dual-sidecar publication, exact partial-push recovery, restart idempotence, 22 focused tests, Ruff, mypy, and a complete just check.

## Dependencies

- **Blocks:** [sase-e7.5](sase-e7.5.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-e7.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-e7.3/README.md) | [sase-e7.3](sase-e7.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`7ba7ce6`](https://github.com/sase-org/sase/commit/7ba7ce664afec6308a65b998c47e6e72c444c8e2) | fix(prompts): make archive migration durable | [sase-e7.3](sase-e7.3.md) | 2026-08-02 14:24:00 |
