# Bead: sase-l.1 — Phase 1 — Enable pytest-xdist by default

[Bead Pages](../README.md) / [sase-l](README.md) / sase-l.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-04-24 00:32:43 UTC · **Closed:** 2026-04-24 00:47:00 UTC
**Plan:** [202604/test\_suite\_speedup.md](https://github.com/sase-org/sase--plans/blob/main/202604/test_suite_speedup.md)

## Description

Edit Justfile test recipe to insert '-n auto --dist=loadfile' before {{ args }}. Drops wall time ~6 min → ~2 min. See plans/202604/test_suite_speedup.md Phase 1.

## Notes

COMMIT: 66fce7a3

## Dependencies

- **Blocks:** [sase-l.2](sase-l.2.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`361257d`](https://github.com/sase-org/sase/commit/361257d743c50c0fc148d9951d0aa41e9c7aec91) | feat: Run \`just test\` in parallel by default via pytest-xdist (sase-l.1) | [sase-l.1](sase-l.1.md) | 2026-04-24 00:47:03 |
