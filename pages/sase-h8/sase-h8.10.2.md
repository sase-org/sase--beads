# Bead: sase-h8.10.2 — Fix the four nodes that failed the sase-h8.9 exit criterion

[Bead Pages](../README.md) / [sase-h8.10](sase-h8.10.md) / sase-h8.10.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-h8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.land/README.md) · **Assignee:** `sase-h8.10.2` · **Size:** medium
**Created:** 2026-08-08 10:56:28 EDT · **Closed:** 2026-08-08 11:41:26 EDT
**Plan:** [202608/flake\_class\_residue.md](https://github.com/sase-org/sase--plans/blob/main/202608/flake_class_residue.md)

## Description

residue: fix the four nodes `just test-contention` failed on at the land attempt — three wall-clock-shaped (`test_first_page_paints_before_full_extension`, `test_lowered_threshold_soak_keeps_fixed_paths_responsive`, `test_timed_out_summary_script_never_blocks_launch`) and one off-pump (`test_apostrophe_enters_jump_mode_with_hints_skipping_headers`) — using the conventions `clock` establishes and the sase-h8.2 wait primitive.

## Notes

[2026-08-08T15:41:26Z · sase-h8.10.2] Implemented load-tolerant diagnostic waits and state-based waits for the four residue nodes. Verified targeted pytest on the four named nodes (4 passed), restricted SASE_CONTENTION_REPEAT=6 just test-contention on the four affected files (27 passed per repeat; tally 0 failed nodes across 6 repeats), and just check (all gates green; scoped selected 40 files).

[2026-08-08T15:43:01Z · sase-h8.10.2] Verified targeted four nodes passed; restricted contention soak passed 0 failed nodes across 6 repeats; just check passed.

## Dependencies

- **Depends on:** [sase-h8.10.1](sase-h8.10.1.md) ✓ · ⧖ 2026-08-08
- **Blocks:** [sase-h8.10.4](sase-h8.10.4.md) ◐ · ⧖ 2026-08-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h8.10.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.10.2/README.md) | [sase-h8.10.2](sase-h8.10.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9360e85`](https://github.com/sase-org/sase/commit/9360e850c640e8932f6aa6a52a21933c0cec1c9d) | test: deflake phase residue timing tests | [sase-h8.10.2](sase-h8.10.2.md) | 2026-08-08 11:43:51 EDT |
