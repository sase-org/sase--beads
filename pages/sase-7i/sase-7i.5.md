# Bead: sase-7i.5 — Stale-state recovery and end-to-end verification

[Bead Pages](../README.md) / [sase-7i](README.md) / sase-7i.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-7i.5`
**Created:** 2026-07-19 17:20:20 UTC · **Closed:** 2026-07-19 19:33:38 UTC
**Plan:** [202607/fix\_toobig\_split\_chop\_dedupe.md](https://github.com/sase-org/sase--plans/blob/main/202607/fix_toobig_split_chop_dedupe.md)

## Description

'Stale-state recovery and end-to-end verification' section: clear the poisoned toobig_split seen state on the host, exercise a real chop run end-to-end, and confirm agents launch for currently oversized files while inhibit_if and dedupe still behave correctly.

## Notes

COMMIT: e2986ea40

## Dependencies

- **Depends on:** [sase-7i.1](sase-7i.1.md) ✓
- **Depends on:** [sase-7i.2](sase-7i.2.md) ✓
- **Depends on:** [sase-7i.3](sase-7i.3.md) ✓
- **Depends on:** [sase-7i.4](sase-7i.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.fb](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.fb/README.md) | [sase-7i.5](sase-7i.5.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`d8b67d6`](https://github.com/sase-org/sase/commit/d8b67d602c0df6f4c2c7d26f845ec85dad3bc10e) | feat: support agent families as fork sources (sase-7i.5) | [sase-7i.5](sase-7i.5.md) | 2026-07-19 19:34:17 |
