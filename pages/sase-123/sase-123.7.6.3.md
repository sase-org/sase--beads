# Bead: sase-123.7.6.3 — Preserve unread descendants and suppress nested duplicate listings

[Bead Pages](../README.md) / [sase-123.7.6](sase-123.7.6.md) / sase-123.7.6.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-123.7.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-123.7.land.md) · **Assignee:** `sase-123.7.6.3` · **Size:** medium
**Created:** 2026-09-18 00:03:34 EDT · **Closed:** 2026-09-18 00:46:58 EDT
**Plan:** [202609/screenshot\_residual\_contracts.md](https://github.com/sase-org/sase--plans/blob/main/202609/screenshot_residual_contracts.md)

## Description

nested-memory-listings: recursively normalize inline-note listings across Markdown, Rich, and JSON while preserving discoverable unread descendants and existing batch deduplication.

## Notes

[2026-09-18T04:46:18Z · sase-123.7.6.3] PROPOSED FOLLOW-UP: Completion snapshot drift for gate cancel - current argparse has --id/--kind and optional ID while tests/completion/snapshots/cli_spec.json does not; discovered during an accidental full-suite escalation before this phase kept its helper internal.

[2026-09-18T04:46:58Z · sase-123.7.6.3] Implemented recursive inline-note suppression and unread descendant rendering; verified focused memory selector tests (67 passed), actual tui.md read audit 558fb6dd13a3, just fix, just check scoped selection (237 files), and epic-symbols reported no entries.

## Dependencies

- **Blocks:** [sase-123.7.6.4](sase-123.7.6.4.md) ✓ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-123.7.6.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-123.7.6.3/README.md) | [sase-123.7.6.3](sase-123.7.6.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`62db470`](https://github.com/sase-org/sase/commit/62db47057cc30b06ecede6e6e4aa704ef6b7b26d) | fix(memory): preserve nested inline note listings | [sase-123.7.6.3](sase-123.7.6.3.md) | 2026-09-18 00:49:12 EDT |
