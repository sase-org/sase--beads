# Bead: sase-1jc.2 — Make typed Agent and Proc launches unconditional

[Bead Pages](../README.md) / [sase-1jc](README.md) / sase-1jc.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zb.md) · **Assignee:** `sase-1jc.2` · **Size:** medium
**Created:** 2026-10-09 22:28:24 EDT
**Plan:** [202610/retire\_all\_feature\_flags.md](https://github.com/sase-org/sase--plans/blob/main/202610/retire_all_feature_flags.md)

## Description

typed-launch: Follow phase 2 and the shared removal checklist. Retire typed_launch_units and close sase-s7. Remove Python and Rust/LSP opt-in checks, disabled diagnostics, hidden-completion paths, and obsolete environment transport while preserving mixed-unit dispatch, static and script conditions, recovery, and code-fence safety. Keep queue_capacity_budget functional for phase 3. Verify both repositories sequentially and include the core revision pin in host finalization.

## Notes

[2026-10-10T03:51:46Z · sase-1jc.2] PROPOSED FOLLOW-UP: Update macros.md to describe typed Proc launches as unconditional (skipped per epic macro_memory=no decision)

[2026-10-10T03:51:51Z · sase-1jc.2] PROPOSED FOLLOW-UP: Update tui_perf.md to describe refresh tokens as unconditional (skipped per epic refresh_memory=no decision)

[2026-10-10T05:25:13Z · sase-1jc.2--1] PROPOSED FOLLOW-UP: just check (tool run ab016319ad3c1eb06b43e2cd154bbc2f) triaged no_new_failures — 10 KNOWN + 3 FLAKY, all touched=false with witnesses predating this phase (e.g. test_config_schema spare_process_patterns mismatch, completion snapshot drift, mutex_groups, parser help, install flow); none implicate typed_launch_units retirement

[2026-10-10T05:51:46Z · sase-1jc.2--2] PROPOSED FOLLOW-UP: just check (tool run b0035f0231261c8d55b2347d4f2ebc63, monitor hhrdcpngwggy) triaged no_new_failures — 13 failed, 10 KNOWN + 3 FLAKY with pre-existing witnesses (e.g. pypi flow, file-hook digest, timezone guard, parser help, query profile, wire agent meta, marker audits, import budget, config schema, completion snapshots, mutex groups); none implicate typed_launch_units retirement

[2026-10-10T06:18:23Z · sase-1jc.2--3] PROPOSED FOLLOW-UP: just check (tool run 7c0c5c644c10f9301e630fa90fd6906f, monitor zmkz19d92ywf) triaged no_new_failures — 14 failed, 10 KNOWN + 4 FLAKY with pre-existing witnesses (1cf7efd448d1a406baca9f3dc6a33bd4, 05b9fc696a324977dde864aadd60a092, 12f0afcd7ea6adf90135b7544987c81b; e.g. spare_process_patterns schema mismatch, completion snapshot drift, mutex_groups 21 vs 20, parser help, install flow); none implicate typed_launch_units retirement

[2026-10-10T06:44:04Z · sase-1jc.2--4] PROPOSED FOLLOW-UP: just check (tool run d0c85a6fd12289708db245f6c13f8ad5, monitor 1j3gcmya1gsa) triaged no_new_failures — 13 failed, 10 KNOWN + 3 FLAKY, all touched=false with pre-existing witnesses (e.g. file-hook digest witness 05b9fc696a324977dde864aadd60a092, completion snapshot drift witness 12f0afcd7ea6adf90135b7544987c81b, timezone guard witness 1cf7efd448d1a406baca9f3dc6a33bd4; plus query profile, config schema, mutex_groups, marker audits, pypi flow, import budget, parser help, wire agent meta); none implicate typed_launch_units retirement. Fourth consecutive identical verdict on an unchanged tree (newest edit 01:23 EDT predates 06:20 UTC check start).

## Dependencies

- **Depends on:** [sase-1jc.1](sase-1jc.1.md) ✓ · ⧖ 2026-10-09
- **Blocks:** [sase-1jc.3](sase-1jc.3.md) ◐ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jc.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jc.2.md) | [sase-1jc.2](sase-1jc.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@e42eb5c`](https://github.com/sase-org/sase-core/commit/e42eb5cab5442eaa36eb3850c06277ad90ba86ea) | feat(launch): retire typed launch-units opt-in; unconditional typed diagnostics | [sase-1jc.2](sase-1jc.2.md) | 2026-10-10 02:45:23 EDT |
