# Bead: sase-em.1 — Shared display helpers in sase.core.time

[Bead Pages](../README.md) / [sase-em](README.md) / sase-em.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sn](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sn/README.md) · **Assignee:** `sase-em.1` · **Size:** small
**Created:** 2026-08-03 07:45:00 EDT · **Closed:** 2026-08-03 08:50:26 EDT
**Plan:** [202608/timezone\_display\_consistency.md](https://github.com/sase-org/sase--plans/blob/main/202608/timezone_display_consistency.md)

## Description

helpers: add `parse_local`/`format_local` to `sase.core.time` so every display site has one way to turn a stored timestamp (aware-UTC ISO, naive ISO, or epoch) into an aware configured-tz value, plus divergence-fixture unit tests.

## Notes

[2026-08-03T12:50:26Z · sase-em.1] Added parse_local/format_local to sase.core.time (aware-UTC/naive-ISO/epoch/datetime -> configured-tz) plus docstring update and __all__; added tests/test_timezone_display_consistency.py covering all normalization and formatting cases under the tz_divergence fixture; added --epic-symbol entries for sase-em(parse_local)/sase-em(format_local) in Justfile since consumers land in later epic phases. Verified: just install, just fmt, and just check (fmt/lint/symvision/toobig/test) all pass; the one test failure seen on a contended run (test_concurrent_bead_mutations_wait_past_the_old_lock_timeout) is a pre-existing flake unrelated to this change, confirmed passing in isolation and on a clean full just check run.

## Dependencies

- **Blocks:** [sase-em.2](sase-em.2.md) ✓
- **Blocks:** [sase-em.3](sase-em.3.md) ✓
- **Blocks:** [sase-em.4](sase-em.4.md) ✓
- **Blocks:** [sase-em.5](sase-em.5.md) ◐
- **Blocks:** [sase-em.6](sase-em.6.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-em.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-em.1/README.md) | [sase-em.1](sase-em.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2c70516`](https://github.com/sase-org/sase/commit/2c70516acaad31563eb4a07866a5a3f424204259) | feat(core-time): add parse\_local/format\_local display helpers | [sase-em.1](sase-em.1.md) | 2026-08-03 08:52:56 EDT |
