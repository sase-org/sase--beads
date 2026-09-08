# Bead: sase-y6.4 — ci\_watch incident-combination notifications

[Bead Pages](../README.md) / [sase-y6](README.md) / sase-y6.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05k](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05k.md) · **Assignee:** `sase-y6.4` · **Size:** medium
**Created:** 2026-09-07 17:06:59 EDT · **Closed:** 2026-09-08 06:02:53 EDT
**Plan:** [202609/ci\_watch\_notification\_plus\_one.md](https://github.com/sase-org/sase--plans/blob/main/202609/ci_watch_notification_plus_one.md)

## Description

chop: collapse per-repo ci_watch failure notifications into one incident-combination notification that +1s material deltas, supersedes itself when a new repo starts failing, and falls back to legacy behavior on older sase CLIs.

## Notes

[2026-09-08T10:02:53Z · sase-y6.4] Reworked bugyi-chops ci_watch onto incident-combination notifications: one create per announced failing-repo set, quiet +1 on fingerprint/recovery/re-fail deltas, superseding create when a new repo goes red, resolution +1 on all-green, v1-state migration, and argparse-signature fallback to legacy per-repo notify. Verified with bugyi-chops just check (ruff, mypy, 128 pytest tests at 93% coverage, sdist/wheel).

## Dependencies

- **Depends on:** [sase-y6.2](sase-y6.2.md) ✓ · ⧖ 2026-09-07
- **Blocks:** [sase-y6.5](sase-y6.5.md) ◐ · ⧖ 2026-09-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-y6.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-y6.4/README.md) | [sase-y6.4](sase-y6.4.md) | 0 |
