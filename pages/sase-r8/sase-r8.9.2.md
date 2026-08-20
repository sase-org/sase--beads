# Bead: sase-r8.9.2 — Require and verify the published core release

[Bead Pages](../README.md) / [sase-r8.9](sase-r8.9.md) / sase-r8.9.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-r8.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-r8.land.md) · **Assignee:** `sase-r8.9.2` · **Size:** small
**Created:** 2026-08-20 09:42:22 EDT · **Closed:** 2026-08-20 11:09:32 EDT
**Plan:** [202608/artifact\_link\_core\_release.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_link_core_release.md)

## Description

floor_integration: raise sase's sase-core-rs floor to the containing published release, refresh the lockfile, remove any obsolete unpublished-capability accommodation, and run the focused artifact-link plus repository verification gates.

## Notes

[2026-08-20T15:00:33Z · sase-r8.9.2] PROPOSED FOLLOW-UP: just check lint (ruff) is red on master for F811 log_dir fixture re-exports in tests/ace/tui/test_logs_pane.py, test_logs_pane_jump.py, test_logs_pane_render.py, and test_logs_pane_toasts.py (`from tests.ace.tui._logs_pane_helpers import log_dir as log_dir` vs pytest params) — not caused by the 0.29.5 floor bump.

[2026-08-20T15:09:32Z · sase-r8.9.2--1] Raised sase-core-rs floor 0.29.4 -> 0.29.5 in pyproject.toml and uv.lock via just ratchet-core-window; tools/probe_core_floor --json reported declared_floor=0.29.5 status=ok (published); tools/check_sase_core_rs_bindings: 0.29.5 exposes all 346 required bindings including bead_add_link and bead_remove_link; tools/validate_sase_core_rs exit 0 with contract test; focused pytest 50 passed (artifact-link beads/store/migrate, CLI link, bead page rendering, validate_sase_core_rs, powerful-variables landing guard); just test 35156 passed, 13 skipped (full suite after packaging-config escalation); epic-symbols sase-r8.9.2 empty. Did not close parent sase-r8.9 or ancestor sase-r8.

[2026-08-20T15:10:58Z · sase-r8.9.2--1] Ratcheted sase-core-rs floor 0.29.4 -> 0.29.5 in pyproject.toml and uv.lock via just ratchet-core-window. tools/probe_core_floor --json: declared_floor=0.29.5, status=ok (published). sase-core-rs 0.29.5 exposes all 346 required bindings including bead_add_link and bead_remove_link; tools/validate_sase_core_rs exit 0. Focused pytest: 50 passed (artifact-link beads/store/migrate, CLI link, bead page rendering, binding contract, landing guard). Full just test: 35156 passed, 13 skipped. epic-symbols: no leftover --epic-symbol entries.

## Dependencies

- **Depends on:** [sase-r8.9.1](sase-r8.9.1.md) ✓ · ⧖ 2026-08-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-r8.9.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-r8.9.2.md) | [sase-r8.9.2](sase-r8.9.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`43b79bf`](https://github.com/sase-org/sase/commit/43b79bf12b5b8c0ef5376319fec8991e7327812a) | build(deps): raise sase-core-rs floor to 0.29.5 | [sase-r8.9.2](sase-r8.9.2.md) | 2026-08-20 11:14:24 EDT |
