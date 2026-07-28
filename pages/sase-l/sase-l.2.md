# Bead: sase-l.2 — Phase 2 — Make coverage opt-in via just test-cov

[Bead Pages](../README.md) / [sase-l](README.md) / sase-l.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-04-24 00:32:47 UTC · **Closed:** 2026-04-24 00:55:40 UTC
**Plan:** [202604/test\_suite\_speedup.md](https://github.com/sase-org/sase--plans/blob/main/202604/test_suite_speedup.md)

## Description

Remove --cov flags from pyproject.toml addopts; add a new just test-cov recipe; rewire just check to call test-cov. Drops wall time ~2 min → ~50 s. See plans/202604/test_suite_speedup.md Phase 2.

## Notes

COMMIT: 1e277b01

## Dependencies

- **Depends on:** [sase-l.1](sase-l.1.md) ✓
- **Blocks:** [sase-l.3](sase-l.3.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`a2bb0bc`](https://github.com/sase-org/sase/commit/a2bb0bc870076c0243ef8a90d5668df5bf94725b) | feat: Make coverage opt-in via \`just test-cov\` (sase-l.2) | [sase-l.2](sase-l.2.md) | 2026-04-24 00:55:43 |
