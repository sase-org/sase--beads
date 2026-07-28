# Bead: sase-9w.2 — Plumb summary and body through sase and turn on shape enforcement

[Bead Pages](../README.md) / [sase-9w](README.md) / sase-9w.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9w.2` · **Size:** medium
**Created:** 2026-07-26 18:00:04 UTC · **Closed:** 2026-07-27 10:12:57 UTC
**Plan:** [202607/axe\_multiline\_descriptions.md](https://github.com/sase-org/sase--plans/blob/main/202607/axe_multiline_descriptions.md)

## Description

sase_description_parts: bump the sase-core-rs window, wrap the new split in the chop facade, carry `description_summary` / `description_body` on the AXE config dataclasses and TUI snapshots, add `maxLength` to both description schemas so editors switch to a multi-line text area, and flip `require_description_shape` on in the sase compose and mutation requests.

## Notes

Implemented sase-core-rs 0.11.1 plumbing for split AXE descriptions; cached summary/body on runtime configs and TUI snapshots; enabled description-shape enforcement for composition and mutation; added 2000-character schema bounds and multiline editor coverage. Focused verification: 89 passed. Full just check: all formatting/lint/SASE gates passed and 22,521 tests passed; remaining failures are unrelated suite-gate timing and an auto-hidden tools-panel scrollbar PNG drift.

## Dependencies

- **Depends on:** [sase-9w.1](sase-9w.1.md) ✓
- **Blocks:** [sase-9w.3](sase-9w.3.md) ✓
- **Blocks:** [sase-9w.4](sase-9w.4.md) ✓
- **Blocks:** [sase-9w.5](sase-9w.5.md) ✓
- **Blocks:** [sase-9w.6](sase-9w.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9w.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9w.2/README.md) | [sase-9w.2](sase-9w.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`dd114a6`](https://github.com/sase-org/sase/commit/dd114a6ef057de37974490ff941554e1d25529ec) | feat(axe): plumb structured descriptions (sase-9w.2) | [sase-9w.2](sase-9w.2.md) | 2026-07-26 19:58:22 |
