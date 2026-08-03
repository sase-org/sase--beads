# Bead: sase-ei.2 — Plan, ChangeSpec, and compatibility-page rewriters

[Bead Pages](../README.md) / [sase-ei](README.md) / sase-ei.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-eh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-eh/README.md) · **Assignee:** `sase-ei.2` · **Size:** medium
**Created:** 2026-08-03 08:48:02 UTC · **Closed:** 2026-08-03 12:50:51 UTC
**Plan:** [202608/historical\_bead\_reprefix.md](https://github.com/sase-org/sase--plans/blob/main/202608/historical_bead_reprefix.md)

## Description

reference-rewriters: add codec-driven plan and ChangeSpec rewrite planners plus canonical and old-ID compatibility bead pages, with exact-match audit and malformed-input coverage.

## Notes

[2026-08-03T12:36:22Z · sase-ei.2] PROPOSED FOLLOW-UP: Stabilize concurrent bead-mutation lock-timeout regression coverage — the 12-worker full suite failed test_concurrent_bead_mutations_wait_past_the_old_lock_timeout after 49.80s under heavy shared load, while the isolated rerun passed in 3.66s.

[2026-08-03T12:49:13Z · sase-ei.2] PROPOSED FOLLOW-UP: Stabilize async VCS repo-completion close race coverage — the 13-worker full suite failed test_worker_result_dropped_when_menu_closed_before_fetch_finishes under shared load, while its isolated rerun passed in 1.41s.

[2026-08-03T12:49:52Z · sase-ei.2] PROPOSED FOLLOW-UP: Stabilize async VCS repo-completion close race coverage — the 13-worker full suite failed test_worker_result_dropped_when_menu_closed_before_fetch_finishes under shared load, while its isolated rerun passed in 1.41s.

[2026-08-03T12:50:51Z · sase-ei.2] Verified codec-driven plan and active/archive ChangeSpec planners, digest revalidation and atomic ChangeSpec apply, canonical plus old-ID alias page generation/cleanup, canonical alias navigation, malformed/ambiguous blockers, and exact no-op bytes. Focused suite: 54 passed; all just check static/SASE gates passed. Two full-suite runs completed over 25.6k tests each with only unrelated load-sensitive failures, all exact reruns passed; proposed follow-ups recorded.

[2026-08-03T12:52:09Z · sase-ei.2] FOLLOW-UP TRIAGE: The two identical async VCS repo-completion proposals above are one finding; delayed publication of the first note caused the retry.

## Dependencies

- **Depends on:** [sase-ei.1](sase-ei.1.md) ✓
- **Blocks:** [sase-ei.4](sase-ei.4.md) ◐
