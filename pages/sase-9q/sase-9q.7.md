# Bead: sase-9q.7 — Documentation, help popup, and end-to-end check

[Bead Pages](../README.md) / [sase-9q](README.md) / sase-9q.7

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9q.7` · **Size:** small
**Created:** 2026-07-26 10:07:09 UTC
**Plan:** [sase/repos/plans/202607/raw\_placeholder\_inputs.md](https://github.com/sase-org/sase--plans/blob/main/sase/repos/plans/202607/raw_placeholder_inputs.md)

## Description

'Phase docs' section: document the feature in ace.md/xprompt.md/configuration.md, update the ? help popup, and run the end-to-end verification checklist.

## Notes

Documented raw placeholder prompt inputs in ace/xprompt/configuration docs; updated ACE ? help popup rows; fixed two pre-existing check blockers found during verification (agents_sync core AgentType boundary and diff-cache provider-cache test isolation). Verification: just install; SASE_PYTEST_WORKERS=4 just check; SASE_PYTEST_WORKERS=4 just test-visual; focused prompt-input checklist subset passed.

## Dependencies

- **Depends on:** [sase-9q.5](sase-9q.5.md) ✓
- **Depends on:** [sase-9q.6](sase-9q.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9q.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9q.7/README.md) | [sase-9q.7](sase-9q.7.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`a397e5b`](https://github.com/sase-org/sase/commit/a397e5b6bef5c0d46749bb8e47c8c9ed6b1a856c) | docs: document raw placeholder prompt inputs (sase-9q.7) | [sase-9q.7](sase-9q.7.md) | 2026-07-26 14:52:23 |
