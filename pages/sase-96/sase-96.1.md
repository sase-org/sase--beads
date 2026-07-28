# Bead: sase-96.1 — Move pytest scratch off the /tmp tmpfs and bound its retention

[Bead Pages](../README.md) / [sase-96](README.md) / sase-96.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-96.1` · **Size:** medium
**Created:** 2026-07-25 12:15:10 UTC
**Plan:** [202607/tmp\_space\_exhaustion.md](https://github.com/sase-org/sase--plans/blob/main/202607/tmp_space_exhaustion.md)

## Description

'Move pytest scratch off the /tmp tmpfs and bound its retention' section: point the pytest base temp directory at a per-workspace on-disk cache instead of the shared 32G tmpfs, set an explicit tmp_path retention policy and count, and add a bounded reaper that prunes stale run directories without waiting out pytest's 3-day lock timeout.

## Dependencies

- **Blocks:** [sase-96.6](sase-96.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-96.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-96.1/README.md) | [sase-96.1](sase-96.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`15ea05a`](https://github.com/sase-org/sase/commit/15ea05af681131a2266531414b69cf823d574520) | fix(test): move pytest scratch off tmpfs (sase-96.1) | [sase-96.1](sase-96.1.md) | 2026-07-25 15:25:23 |
