# Bead: sase-w.2 — Phase 2 — ChangeSpec j/k Hot Path: Detail-Only Refresh + Row Patching + Cached Widget Refs

[Bead Pages](../README.md) / [sase-w](README.md) / sase-w.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-w.2`
**Created:** 2026-04-27 16:16:35 UTC · **Closed:** 2026-04-27 16:52:01 UTC
**Plan:** [202604/tui\_perf\_overhaul\_1.md](https://github.com/sase-org/sase--plans/blob/main/202604/tui_perf_overhaul_1.md)

## Description

Add _refresh_changespec_detail_only() in actions/changespec/_display.py that updates only detail/ancestors/footer/info-panel for new selection (pure j/k must NOT call ChangeSpecList.update_list()). Preserve full _refresh_display() for query/filter/fold/hint/mark/reload/visibility changes. Add patch_changespec_row(idx, changespec, *, selected, marked, hint) on widgets/changespec_list.py modeled on AgentList.patch_agent_row, with row-index maps (_option_idx_by_changespec_name, _last_row_signature_by_idx, _row_widths_by_idx). Cache stable widget refs after mount (self._w_changespec_list, _w_changespec_detail, _w_ancestors_children, _w_footer, _w_agent_detail). Acceptance: 50 idx changes produce 0 update_list() calls; mark toggle calls patch_changespec_row once; trace shows query_one count drops to ~0 on stable panels during 50-key burst; 50-key j/k p95 < 16ms on 500-spec fixture.

## Notes

COMMIT: 2095b572

## Dependencies

- **Depends on:** [sase-w.1](sase-w.1.md) ✓
- **Blocks:** [sase-w.3](sase-w.3.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`b4d5fdc`](https://github.com/sase-org/sase/commit/b4d5fdce13c3bc3e84b20ca37931f4ac7a132dac) | feat(ace/tui/perf): ChangeSpec j/k detail-only refresh + row patching (sase-w.2) | [sase-w.2](sase-w.2.md) | 2026-04-27 16:52:05 |
