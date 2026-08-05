# Bead: sase-fc.6 — Mobile wire, bead pages, and clan epic summary

[Bead Pages](../README.md) / [sase-fc](README.md) / sase-fc.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tc](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tc/README.md) · **Assignee:** `sase-fc.6` · **Size:** medium
**Created:** 2026-08-05 16:29:03 EDT · **Closed:** 2026-08-05 17:24:22 EDT
**Plan:** [202608/bead\_create\_time.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_create_time.md)

## Description

wire_pages: add created_at to the mobile helper bead summary wire, add a Created column to the bead pages phase and dependency tables while keeping page bytes stable, and show creation time in the clan epic summary header and phase lines.

## Notes

[2026-08-05T21:23:55Z · sase-fc.6] PROPOSED FOLLOW-UP: tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout is flaky under parallel load — it failed once in a full `just check` run (44s under xdist contention) and passes in 3.7s in isolation; pre-existing and unrelated to bead-time presentation changes.

[2026-08-05T21:24:22Z · sase-fc.6] Wired bead creation time into the three wire_pages surfaces. Mobile helper: _bead_summary_wire now carries raw ISO created_at (Data tier), inherited by _bead_detail_wire. Bead pages: _render_instant delegates to bead_instant_label with identity-block bytes verified unchanged (golden diff touches only the new table columns); render_phases gained a Created column and dependency rows a '· ⧖ <date>' suffix, both absolute-only per the live-vs-persisted rule; goldens regenerated. Clan epic summary: header and phase rows now show '⧖ <age>' with reserved width so nothing overflows _SUMMARY_WIDTH. Added bead_date_label to the shared module (bead_created_cli now uses it) plus unit tests, page-table tests (present and missing created_at), mobile wire assertions, and clan-summary tests with a pinned clock. Dropped the now-satisfied bead_created_chip/bead_instant_label symvision epic whitelist entries. just check: lint clean, 25889 passed including the PNG visual suite; the single failure (test_concurrent_bead_mutations_wait_past_the_old_lock_timeout) is a pre-existing load-sensitive flake that passes in isolation — noted as a proposed follow-up.

## Dependencies

- **Depends on:** [sase-fc.1](sase-fc.1.md) ✓ · ⧖ 2026-08-05
- **Blocks:** [sase-fc.7](sase-fc.7.md) ◐ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fc.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fc.6/README.md) | [sase-fc.6](sase-fc.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`734d2e0`](https://github.com/sase-org/sase/commit/734d2e0c261834051c4c2c7bd139e7f848a8f071) | feat(bead): surface bead creation time on mobile, page tables, and clan summaries | [sase-fc.6](sase-fc.6.md) | 2026-08-05 17:25:40 EDT |
