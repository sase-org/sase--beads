# Bead: sase-em.5 — Artifact-file calendar dates in the configured timezone

[Bead Pages](../README.md) / [sase-em](README.md) / sase-em.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sn](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sn/README.md) · **Assignee:** `sase-em.5` · **Size:** medium
**Created:** 2026-08-03 11:46:14 UTC
**Plan:** [202608/timezone\_display\_consistency.md](https://github.com/sase-org/sase--plans/blob/main/202608/timezone_display_consistency.md)

## Description

artifact-dates: mint artifact `created_at` and the retention `now` with the configured-tz offset and make the Rust core bucket calendar dates by that embedded offset, so `date:`/`since:` filtering agrees with the displayed day.

## Dependencies

- **Depends on:** [sase-em.1](sase-em.1.md) ✓
- **Blocks:** [sase-em.6](sase-em.6.md) ◐
