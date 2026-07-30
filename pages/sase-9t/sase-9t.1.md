# Bead: sase-9t.1 — Rust core accepts lumberjack descriptions and can require them

[Bead Pages](../README.md) / [sase-9t](README.md) / sase-9t.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9t.1` · **Size:** medium
**Created:** 2026-07-26 12:53:16 UTC · **Closed:** 2026-07-26 13:10:30 UTC
**Plan:** [sase/repos/plans/202607/axe\_required\_descriptions.md](https://github.com/sase-org/sase--plans/blob/main/sase/repos/plans/202607/axe_required_descriptions.md)

## Description

'Phase 1 — Rust core description support' section: teach sase_core's AXE validator about `lumberjacks.<name>.description`, add non-blank validation for both lumberjack and chop descriptions, and implement an opt-in `require_descriptions` flag on the validation, compose, and entry-mutation wires that defaults to false so the release stays backwards compatible.

## Dependencies

- **Blocks:** [sase-9t.2](sase-9t.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9t.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9t.1/README.md) | [sase-9t.1](sase-9t.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@8b76c42`](https://github.com/sase-org/sase-core/commit/8b76c424578cb99e2eacdee389634d8f2dec5892) | feat(axe): support required config descriptions (sase-9t.1) | [sase-9t.1](sase-9t.1.md) | 2026-07-26 13:04:34 |
