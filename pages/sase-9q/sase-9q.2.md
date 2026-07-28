# Bead: sase-9q.2 — Python facade and raw-only placeholder semantics

[Bead Pages](../README.md) / [sase-9q](README.md) / sase-9q.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9q.2` · **Size:** small
**Created:** 2026-07-26 10:06:52 UTC
**Plan:** [sase/repos/plans/202607/raw\_placeholder\_inputs.md](https://github.com/sase-org/sase--plans/blob/main/sase/repos/plans/202607/raw_placeholder_inputs.md)

## Description

'Phase facade' section: add the sase.xprompt.raw_placeholders facade and make highlighting, completion candidates, and common-placeholder recording raw-only.

## Notes

Implemented the Python raw-placeholder facade, raw span propagation, raw-only placeholder highlighting, raw-only common-placeholder recording, and focused/unit/PNG coverage. Verification: just install passed; focused placeholder/history/widget tests passed; placeholder visual snapshots passed after intentional golden update; just check passes format/lint/validation but the full test stage still has an unrelated repeatable agents_renamed_generic_family_root_120x40 PNG mismatch (neighbor count 1 -> 2). The diff-cache and retry visual full-run failures passed in isolation.

## Dependencies

- **Depends on:** [sase-9q.1](sase-9q.1.md) ✓
- **Blocks:** [sase-9q.3](sase-9q.3.md) ✓
- **Blocks:** [sase-9q.6](sase-9q.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9q.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9q.2/README.md) | [sase-9q.2](sase-9q.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`aedbb6b`](https://github.com/sase-org/sase/commit/aedbb6b07ad73fb4c61c4c02db2e0d3e71d8029f) | feat(xprompt): add raw placeholder facade (sase-9q.2) | [sase-9q.2](sase-9q.2.md) | 2026-07-26 11:06:51 |
