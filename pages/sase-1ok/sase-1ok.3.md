# Bead: sase-1ok.3 — Warn or refuse when an agent targets a one-segment near-miss of its assigned bead

[Bead Pages](../README.md) / [sase-1ok](README.md) / sase-1ok.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.14p](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.14p.md) · **Assignee:** `sase-1ok.3` · **Size:** medium
**Created:** 2026-10-26 18:10:50 EDT · **Closed:** 2026-10-26 21:26:38 EDT
**Plan:** [202610/stranded\_phase\_detection\_and\_wrong\_bead\_guard.md](https://github.com/sase-org/sase--plans/blob/main/202610/stranded_phase_detection_and_wrong_bead_guard.md)

## Description

assigned-bead-near-miss: detect, inside SASE agents, bead IDs that differ from the assigned bead by one inserted or deleted non-trailing segment; banner the read output, refuse close/open per the near_miss_mutation decision, and tighten the phase and task work prompts.

## Notes

[2026-10-27T01:26:19Z · sase-1ok.3] PROPOSED FOLLOW-UP: FLAKY tests/ace/tui/test_machines_pane.py::test_status_check_is_user_triggered_and_records_observation timed out under full-lane load — already tracked by sase-1ax

[2026-10-27T01:26:23Z · sase-1ok.3] PROPOSED FOLLOW-UP: just check test-scoped exited 1 with no_new_failures — 3 KNOWN capacity-scan tests (witness 0eefa7f1c9ee0383c9c47942325079fe; already noted on sase-1ok.1): test_capacity_only_skips_done_dirs_and_keeps_active_ones, test_capacity_blocked_waiter_does_not_park_the_queue_behind_it, test_capacity_blocked_head_then_high_budget_launch_uses_real_scan

[2026-10-27T01:26:38Z · sase-1ok.3] Assigned-bead one-segment near-miss: helper in src/sase/bead/assigned_near_miss.py; read banners top+bottom (JSON on stderr); close/open refuse before write; note/update/epic-symbols warn; not-found did-you-mean; fast-path open refuse + update defer only on a hit; bd/work_phase_bead and bd/work_task prompts tell agents a closed read without a host notice is a copied-ID miss. Tests: tests/test_bead/test_assigned_near_miss.py + test_cli_assigned_near_miss.py (53 targeted passed). just fix green. sase bead epic-symbols sase-1ok.3 empty. sase tool run check c6ba95cd7ec6d1eb0b97d35ed34ec705: lint/mypy/symvision green, 57742 passed, 4 failed all KNOWN/FLAKY (verdict no_new_failures).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ok.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ok.3/README.md) | [sase-1ok.3](sase-1ok.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9cb3585`](https://github.com/sase-org/sase/commit/9cb35859c9454b01d0d130e4cd74cb6d38f55251) | feat(beads): warn or refuse assigned-bead one-segment near-misses | [sase-1ok.3](sase-1ok.3.md) | 2026-10-26 21:28:07 EDT |
