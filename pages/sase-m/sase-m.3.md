# Bead: sase-m.3 — Phase 3: Gate PDF integration test + verification sweep

[Bead Pages](../README.md) / [sase-m](README.md) / sase-m.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-04-24 14:30:59 UTC · **Closed:** 2026-04-24 14:54:22 UTC
**Plan:** [202604/speed\_up\_slow\_tests.md](https://github.com/sase-org/sase--plans/blob/main/202604/speed_up_slow_tests.md)

## Description

Register a slow pytest marker, apply it to test_build_integration_produces_pdf, exclude slow tests from the default run via addopts, add a just test-slow recipe, and run the final verification sweep comparing new top-20 durations against the baseline.

## Notes

COMMIT: 4c784266

## Dependencies

- **Depends on:** [sase-m.1](sase-m.1.md) ✓
- **Depends on:** [sase-m.2](sase-m.2.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`4c78426`](https://github.com/sase-org/sase/commit/4c7842661642ae6e6bb0cca48ec1d21cd93d2810) | chore: gate PDF integration test behind a \`slow\` marker (sase-m.3) | [sase-m.3](sase-m.3.md) | 2026-04-24 14:54:26 |
