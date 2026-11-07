# Bead: sase-1rq.3.1.1 — Make the install\_ui EarnedEta test hermetic to CARGO\_INCREMENTAL

[Bead Pages](../README.md) / [sase-1rq.3.1](sase-1rq.3.1.md) / sase-1rq.3.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.3.md) · **Assignee:** `sase-1rq.3.1.1` · **Size:** small
**Created:** 2026-11-07 08:10:11 EST · **Closed:** 2026-11-07 08:28:19 EST
**Plan:** [202611/bob\_cli\_ci\_green.md](https://github.com/sase-org/sase--plans/blob/main/202611/bob_cli_ci_green.md)

## Description

lint-incremental: fix the one deterministic lint-job failure. In the check-scripts step, EarnedEtaTests.test_seeded_history_shows_bar_range_plan_and_summary seeds history rows with incremental=True, but CI's rust-cache sets CARGO_INCREMENTAL=0, so no row matches and the "usually" ETA text never renders. Make the test independent of the caller's CARGO_INCREMENTAL, then prove it with and without the variable.

## Notes

[2026-11-07T13:28:05Z · sase-1rq.3.1.1] PROPOSED FOLLOW-UP: pre-existing failure install_ui.tests.test_live.RunnerPtyTests.test_real_cargo_install_transcript_uses_correct_phases_and_hides_chatter fails identically on clean base tree with and without CARGO_INCREMENTAL (StopIteration: no spinner frame contains "compiling dependencies 87/235"); unrelated to lint-incremental fix, looks like PTY spinner-frame timing sensitivity -r recording out-of-scope pre-existing failure

[2026-11-07T13:28:19Z · sase-1rq.3.1.1] Sandbox.base_env now scrubs CARGO_INCREMENTAL so the child install_all process always sees incremental-enabled, matching seeded rows (incremental=True). Verified: target EarnedEta test passes with CARGO_INCREMENTAL=0 and unset; all 24 test_install_all tests pass with CARGO_INCREMENTAL=0; just fmt, just lint (warnings only), just check-release-tools pass with CARGO_INCREMENTAL=0. Full discover suite 145/146 both ways; the one failure (test_live PTY spinner-frame test) reproduces identically on the clean base tree and is recorded as PROPOSED FOLLOW-UP. No production code changed; fix is in scripts/lib/install_ui/tests/test_install_all.py only.

## Dependencies

- **Blocks:** [sase-1rq.3.1.4](sase-1rq.3.1.4.md) ✓ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.3.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.3.1.1/README.md) | [sase-1rq.3.1.1](sase-1rq.3.1.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1rq.3.1.1][1] | check prior notes/history | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.3.1.1/README.md

<!-- sase:referenced-by:end -->
