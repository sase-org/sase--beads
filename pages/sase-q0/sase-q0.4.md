# Bead: sase-q0.4 — Detect and surface occupancy conflicts

[Bead Pages](../README.md) / [sase-q0](README.md) / sase-q0.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.06g](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.06g.md) · **Assignee:** `sase-q0.4` · **Size:** small
**Created:** 2026-08-18 13:44:19 EDT · **Closed:** 2026-08-18 17:13:10 EDT
**Plan:** [202608/workspace\_exclusivity.md](https://github.com/sase-org/sase--plans/blob/main/202608/workspace_exclusivity.md)

## Description

detect: add a doctor check and a concurrency regression test that prove simultaneous allocation bursts never hand the same workspace to two agents and that a conflicting occupant is reported rather than silently overwritten.

## Notes

[2026-08-18T21:10:12Z · sase-q0.4] PROPOSED FOLLOW-UP: just check/just check-full stay red on a pre-existing project_accent_map import — src/sase/main/project_handler.py and sase.ace.tui.modals.projects_pane import project_accent_map from sase.ace.tui.project_styles, but that name is now private (_project_accent_map). This is the leftover sase-n4 / sase-pw.8 accent cleanup, not this phase. It also cascades into 200+ TUI collection errors and tests/test_contract_manifest.py during a full suite.

[2026-08-18T21:13:10Z · sase-q0.4--1] Detect phase complete: workspace.occupancy_conflicts doctor check added (report-only; no auto-repair); occupancy_conflicts detector consumes ledger_path + read_ledger_records and annotates last mutation/caller. Concurrency burst (4 launcher + 4 deferred claims) proved no duplicate workspace numbers. Incident-shape test: A holds N, B deferred claim skips N, occupancy guard blocks stolen prep. sase bead epic-symbols sase-q0.4: no leftover --epic-symbol entries. just check-full (gz5q191ky0v0) failed only on pre-existing mypy attr-defined in src/sase/main/project_handler.py (project_accent_map now private in project_styles) — already recorded as PROPOSED FOLLOW-UP, not this phase. fmt/ruff/keep-sorted passed; tests did not run because mypy aborted check-full.

[2026-08-18T21:13:57Z · sase-q0.4--1] Doctor check workspace.occupancy_conflicts added (report-only). Detector uses ledger_path + read_ledger_records and annotates last mutation/caller tag. Concurrency burst: 4 launcher + 4 deferred claims never share a workspace number. Incident shape: A holds N, B deferred claim skips N, occupancy guard blocks stolen prep. Epic-symbols clean (no leftover --epic-symbol). just check-full failed only on pre-existing mypy: project_handler.py imports missing project_accent_map (already PROPOSED FOLLOW-UP); fmt/ruff/keep-sorted passed; tests did not run because mypy aborted the gate.

## Dependencies

- **Depends on:** [sase-q0.1](sase-q0.1.md) ✓ · ⧖ 2026-08-18
- **Depends on:** [sase-q0.3](sase-q0.3.md) ✓ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-q0.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-q0.4.md) | [sase-q0.4](sase-q0.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`716e9de`](https://github.com/sase-org/sase/commit/716e9de98f2f6346ef0ae23ba92be08f17397730) | feat(doctor): detect workspace occupancy conflicts | [sase-q0.4](sase-q0.4.md) | 2026-08-18 17:14:53 EDT |
