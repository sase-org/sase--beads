# Bead: sase-dz.6 — Confirm a fully green master run

[Bead Pages](../README.md) / [sase-dz](README.md) / sase-dz.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rm](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rm/README.md) · **Assignee:** `sase-dz.6` · **Size:** small
**Created:** 2026-08-02 10:46:10 UTC · **Closed:** 2026-08-02 13:05:21 UTC
**Plan:** [202608/ci\_green\_restoration.md](https://github.com/sase-org/sase--plans/blob/main/202608/ci_green_restoration.md)

## Description

verify-green: watch a full master run after the other phases land, confirm every job is green, and re-tune the test timeout if the slowest leg still lands close to the limit.

## Notes

[2026-08-02T13:04:59Z · sase-dz.6] PROPOSED FOLLOW-UP: Investigate prompt-catalog parallel test flakes — local just check initially failed tests/ace/tui/test_prompt_bar_xprompt_selector_requests.py::{test_vcs_tag_offers_project_local_xprompts_by_canonical_name,test_vcs_tag_directory_key_spelling_also_resolves} and tests/ace/tui/test_prompt_catalog.py::test_catalog_loading_worker_does_not_block_event_loop, but all three passed on immediate direct rerun.

[2026-08-02T13:05:21Z · sase-dz.6] Verified CI run https://github.com/sase-org/sase/actions/runs/30746162827 on c081bb6e: build-core, published-core-minimum-smoke, lint, visual-test, perf-floors, and test 3.14 were green; test 3.12 finished in 62m22s, so the 90m timeout has headroom and needs no retune. Fixed the remaining CI failures locally: isolated the bead-store refresh fake clock from global time.monotonic and made prompt validate help assertions accept argparse metavar rendering. Verified targeted tests and final just check passed.

[2026-08-02T13:06:57Z · sase-dz.6] Verified CI run 30746162827 reached current master checks; 3.12 finished in 62m22s so no timeout retune was needed; local targeted tests and final just check passed.

## Dependencies

- **Depends on:** [sase-dz.1](sase-dz.1.md) ✓
- **Depends on:** [sase-dz.2](sase-dz.2.md) ✓
- **Depends on:** [sase-dz.3](sase-dz.3.md) ✓
- **Depends on:** [sase-dz.4](sase-dz.4.md) ✓
- **Depends on:** [sase-dz.5](sase-dz.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-dz.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dz.6/README.md) | [sase-dz.6](sase-dz.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`d0f0b61`](https://github.com/sase-org/sase/commit/d0f0b6161984c44f80d5e0eeaf242033a6399892) | test: stabilize ci restoration checks | [sase-dz.6](sase-dz.6.md) | 2026-08-02 13:07:48 |
