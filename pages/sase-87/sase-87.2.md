# Bead: sase-87.2 — The bead= kwarg on %wait

[Bead Pages](../README.md) / [sase-87](README.md) / sase-87.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-87.2` · **Size:** medium
**Created:** 2026-07-20 15:01:49 UTC
**Plan:** [202607/bead\_gated\_wait.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_gated_wait.md)

## Description

'The bead= kwarg on %wait' section: extend the %wait directive grammar with a repeatable bead=<bead_id> keyword collected alongside time=/runners=, expose AgentDirectives.wait_beads, keep bare-wait rewriting and templates ignoring bead-only occurrences, and round-trip the kwarg through directive editing.

## Notes

COMMIT: de0a23484

## Dependencies

- **Blocks:** [sase-87.3](sase-87.3.md) ✓
- **Blocks:** [sase-87.4](sase-87.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-87.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-87.2/README.md) | [sase-87.2](sase-87.2.md) | 1 |
| [bbugyi200.athena.sase-87.2--code](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-87.2.md#member-code) | [sase-87.2](sase-87.2.md) | 0 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`e6c865e`](https://github.com/sase-org/sase/commit/e6c865e9ab838696545d21e6509a7eb5b7d612bd) | feat(xprompt): support bead waits (sase-87.2) | [sase-87.2](sase-87.2.md) | 2026-07-20 16:01:57 |
