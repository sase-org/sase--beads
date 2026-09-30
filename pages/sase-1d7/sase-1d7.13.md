# Bead: sase-1d7.13 — Notification store retention and wait-check payload diet

[Bead Pages](../README.md) / [sase-1d7](README.md) / sase-1d7.13

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0uc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0uc.md) · **Assignee:** `sase-1d7.13` · **Size:** large
**Created:** 2026-09-30 07:18:24 EDT · **Closed:** 2026-09-30 18:36:32 EDT
**Plan:** [202609/unread\_ack\_reliability\_and\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202609/unread_ack_reliability_and_tui_responsiveness.md)

## Description

notification-store-diet: shorten live retention of dismissed rows and bound wait_checks plus_ones and action_data so every full read, rewrite and lock window scales with a much smaller store.

## Notes

[2026-09-30T21:30:06Z · sase-1d7.13] notification-store-diet measurement (private copy, production untouched): before 3933 rows / 19140180 bytes (wait_checks 179 rows, 22923 stored +1, max len 500); after new 3-day + 32-entry compaction 1562 rows / 4876800 bytes (wait_checks 160 rows, 2771 stored +1, max len 32, dropped exact with saturation); archived 2371 rows / 10102350 bytes; live -74.5% vs projection -74% (4.94MB). Second read idempotent: generation stable, no duplicate archive. Copy deleted after measurement.

[2026-09-30T22:36:17Z · sase-1d7.13--1] notification-store-diet verification follow-up: fixed one real regression from the retention change (test_compact_preserves_unread_and_actionable_notifications used an exactly-3-day-old dismissed row as fresh; under the new 3-day policy with strict < cutoff it archives after ms elapse, so the fixture now uses 2 days, mirroring the Rust parity update -3 to -2). Verified: 82/82 Rust notification_store_parity pass, 243/243 tests/test_core_facade pass, 39/39 wait-checks+retention pass, ruff+mypy clean on touched files. Full just check (run 8ffdf8c9797c7ea3de129d6c4e598e1f) still reports failures outside this change: PROPOSED FOLLOW-UP: tests/ace/tui/widgets/test_agent_header_panel.py collection ImportError (imports test_hint_document_forces_expansion, which no longer exists in test_agent_header_panel_basic.py; both files untouched by this phase, fails identically on base), and test_force_reuse_launch_seam_consume.py::test_launch_query_wipe_failure_records_and_emits which passes in isolation (parallel-lane flake); remaining failures carry KNOWN triage witnesses. --message

## Dependencies

- **Depends on:** [sase-1d7.12](sase-1d7.12.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1d7.2](sase-1d7.2.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d7.13](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d7.13.md) | [sase-1d7.13](sase-1d7.13.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@5a59e78`](https://github.com/sase-org/sase-core/commit/5a59e7859ed39d41f59f0ae1d5eb902c65f0b410) | feat(notifications): 3-day archival retention and wait\_checks 32-entry plus-one cap | [sase-1d7.13](sase-1d7.13.md) | 2026-09-30 18:38:36 EDT |
| sase | [`788a931`](https://github.com/sase-org/sase/commit/788a9311f8e6bada7f030f28c47126322e75ad8e) | feat(notifications): shorten dismissed retention to 3 days and bound wait\_checks payloads | [sase-1d7.13](sase-1d7.13.md) | 2026-09-30 19:23:54 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1d7.13--1][1] | implement notification_store_diet plan follow-up after failed check | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d7.13.md

<!-- sase:referenced-by:end -->
