# Bead: sase-6r.2 — TTL-gate sidecar store network integration

[Bead Pages](../README.md) / [sase-6r](README.md) / sase-6r.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-6r.2`
**Created:** 2026-07-18 11:26:07 UTC
**Plan:** [202607/fast\_bead\_reads.md](https://github.com/sase-org/sase--plans/blob/main/202607/fast_bead_reads.md)

## Description

'TTL-gate sidecar store network integration' section: reuse the bead-refresh integration marker to skip the synchronous fetch+rebase in ensure_sidecar_sdd_clone when the clone integrated recently.

## Notes

COMMIT: 9a2ab4a53

## Dependencies

- **Blocks:** [sase-6r.3](sase-6r.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-6r.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-6r.2/README.md) | [sase-6r.2](sase-6r.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`0c1c875`](https://github.com/sase-org/sase/commit/0c1c875d4179c9d1a4dd5293336c8561b81677ea) | perf: gate sidecar integration with freshness TTL (sase-6r.2) | [sase-6r.2](sase-6r.2.md) | 2026-07-18 11:48:58 |
