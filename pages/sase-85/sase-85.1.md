# Bead: sase-85.1 — Launch-fresh epic bead reads with loud fallback diagnostics

[Bead Pages](../README.md) / [sase-85](README.md) / sase-85.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-85.1` · **Size:** medium
**Created:** 2026-07-20 14:58:40 UTC
**Plan:** [202607/epic\_clan\_summary\_rich.md](https://github.com/sase-org/sase--plans/blob/main/202607/epic_clan_summary_rich.md)

## Description

'Phase: Launch-fresh epic bead reads with loud fallback diagnostics' section: retry the epic lookup against a synchronously integrated bead store when the epic id is missing from a warm sidecar clone, report script failures to stderr so they land in the agent log, and widen the summary-script timeout budget to cover the blocking retry.

## Notes

COMMIT: 25a29df37

## Dependencies

- **Blocks:** [sase-85.2](sase-85.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-85.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-85.1/README.md) | [sase-85.1](sase-85.1.md) | 1 |
| [bbugyi200.athena.sase-85.1--code](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-85.1.md#member-code) | [sase-85.1](sase-85.1.md) | 0 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`0a1fd5f`](https://github.com/sase-org/sase/commit/0a1fd5f83e0d0bf3ed86b8638bdf266ea80c5557) | fix: refresh missing epic summaries before fallback (sase-85.1) | [sase-85.1](sase-85.1.md) | 2026-07-20 15:21:23 |
