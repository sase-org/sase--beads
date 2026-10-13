# Bead: sase-1jm.9.8 — Help goldens, visual sweep, benches, and acceptance evidence

[Bead Pages](../README.md) / [sase-1jm.9](sase-1jm.9.md) / sase-1jm.9.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.land.md) · **Assignee:** `sase-1jm.9.8` · **Size:** medium
**Created:** 2026-10-12 14:50:52 EDT · **Closed:** 2026-10-12 23:34:03 EDT
**Plan:** [202610/agents\_archive\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_completion.md)

## Description

land-proof: fix the Archive help PNG scroll stop, regenerate help-modal goldens once, run the targeted Archive, Record, Artifacts, saved-group, and help visual checks, measure the Archive and Inbox j/k and warm ,a benches back to back, walk every epic acceptance gate, and record evidence for the sase-1jm land agent.

## Notes

[2026-10-13T02:08:58Z · sase-1jm.9.8--1] PROPOSED FOLLOW-UP: Clean-base `tests/test_project_display_presentation_audit.py::test_path_label_exemptions_name_existing_sites_and_rationales` reproduces the stale exemption for deleted `src/sase/ace/tui/modals/revive_agent_modal.py::_agent_filter_label`; the same failure is already recorded on root epic `sase-1jm` note #12 (master run 38319566405 after ba89d2a6db), with no separate task owner listed.

[2026-10-13T03:33:42Z · sase-1jm.9.8--2] PROPOSED FOLLOW-UP: Final check ac9315c9cecc365a9aaa86e66cd2c332 has two clean-HEAD failures: test_quitting_from_archive_persists_grouping_only is already recorded in sase-1jm.9.4 note #1; test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data is already owned by sase-1k4. The stale revive_agent_modal path-label exemption was KNOWN in this run and is already recorded in this phase note #1 and epic note #12. No new bead created.

[2026-10-13T03:33:53Z · sase-1jm.9.8--2] VERIFICATION: Acceptance suite: 239 passed across Archive view foundation, guards/readers, controller prewarm and index degradation, arrivals/link-follow, jump routing, real corpus/list order, scope parsing, and agent-search CLI corpus-order parity. Mounted placeholder/header/search/jump checks passed after the visibility fix. Visual strict run b2924af3ef7c4ab89ead975cbecef62a: 70 passed, clean, 0 skipped or updated. Latest Archive bench: warm median 93.6ms (7 samples 88.5–95.3; budget 100); j/k next p50/p95 10.61/13.05ms, prev 9.33/12.14ms (budget p95 <16). Same-host Inbox control: default next 21.89/26.66ms and prev 19.45/37.35ms; named next 19.83/26.29ms and prev 20.98/25.17ms. Archive bench uptime load averages before/after 6.64/8.50/9.00 and 5.58/8.04/8.83; Inbox control 5.45/7.98/8.80 and 5.98/7.65/8.63. Final sase tool run check ac9315c9cecc365a9aaa86e66cd2c332: all lint and validation stages passed; scoped tests 4558 passed, 3 clean-base failures (2 tracked follow-ups and the known path exemption). No memory edits.

[2026-10-13T03:34:03Z · sase-1jm.9.8--2] Verified Archive acceptance gates, strict visuals, current performance budgets, and project check; only documented clean-base failures remain.

## Dependencies

- **Depends on:** [sase-1jm.9.2](sase-1jm.9.2.md) ✓ · ⧖ 2026-10-12
- **Depends on:** [sase-1jm.9.5](sase-1jm.9.5.md) ✓ · ⧖ 2026-10-12
- **Depends on:** [sase-1jm.9.6](sase-1jm.9.6.md) ✓ · ⧖ 2026-10-12
- **Depends on:** [sase-1jm.9.7](sase-1jm.9.7.md) ✓ · ⧖ 2026-10-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.9.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.9.8.md) | [sase-1jm.9.8](sase-1jm.9.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1230bb3`](https://github.com/sase-org/sase/commit/1230bb32c19eea7a5eabad73d2fae48cd5591748) | perf(ace): optimize Archive detail navigation | [sase-1jm.9.8](sase-1jm.9.8.md) | 2026-10-12 23:35:07 EDT |
