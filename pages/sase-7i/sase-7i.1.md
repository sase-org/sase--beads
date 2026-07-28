# Bead: sase-7i.1 — Once-per key release in the Rust chop engine

[Bead Pages](../README.md) / [sase-7i](README.md) / sase-7i.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-7i.1`
**Created:** 2026-07-19 17:20:02 UTC
**Plan:** [202607/fix\_toobig\_split\_chop\_dedupe.md](https://github.com/sase-org/sase--plans/blob/main/202607/fix_toobig_split_chop_dedupe.md)

## Description

'Once-per key release in the Rust chop engine' section: add a release_chop_once_per engine operation to sase-core with a pyo3 binding and a thin axe_chop_facade wrapper so the runner can remove recorded once-per keys from the seen document.

## Notes

COMMIT: 344d4ab42

## Dependencies

- **Blocks:** [sase-7i.3](sase-7i.3.md) ✓
- **Blocks:** [sase-7i.5](sase-7i.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-7i.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-7i.1/README.md) | [sase-7i.1](sase-7i.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`05c9c1c`](https://github.com/sase-org/sase/commit/05c9c1ccab5c9e8cf4769a09d8a1398aad718626) | feat(axe): persist released chop once-per keys (sase-7i.1) | [sase-7i.1](sase-7i.1.md) | 2026-07-19 17:46:42 |
