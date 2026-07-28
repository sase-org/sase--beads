# Bead: sase-96.2 — Stop copying multi-megabyte PNG assets into every scaffolded test home

[Bead Pages](../README.md) / [sase-96](README.md) / sase-96.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-96.2` · **Size:** medium
**Created:** 2026-07-25 12:15:15 UTC
**Plan:** [202607/tmp\_space\_exhaustion.md](https://github.com/sase-org/sase--plans/blob/main/202607/tmp_space_exhaustion.md)

## Description

'Stop copying multi-megabyte PNG assets into every scaffolded test home' section: find the scaffolding path that installs the sdd and memory directory-map PNGs, and make asset installation skippable or redirectable so each per-test temp home costs kilobytes instead of ~2.3 MB.

## Notes

COMMIT: e82cc553c

## Dependencies

- **Blocks:** [sase-96.6](sase-96.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-96.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-96.2/README.md) | [sase-96.2](sase-96.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`7340235`](https://github.com/sase-org/sase/commit/7340235b22b94173d94dc752127932895552f749) | perf(test): avoid copying large directory map assets (sase-96.2) | [sase-96.2](sase-96.2.md) | 2026-07-25 13:26:44 |
