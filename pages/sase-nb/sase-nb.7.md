# Bead: sase-nb.7 — sase flag and the flag doctor checks

[Bead Pages](../README.md) / [sase-nb](README.md) / sase-nb.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03v](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03v.md) · **Assignee:** `sase-nb.7` · **Size:** medium
**Created:** 2026-08-16 12:26:02 EDT · **Closed:** 2026-08-16 19:05:29 EDT
**Plan:** [202608/feature\_flags.md](https://github.com/sase-org/sase--plans/blob/main/202608/feature_flags.md)

## Description

cli: add the sase flag group with list, new, and show, and register the flags.* doctor checks covering registry integrity, override hygiene, and overdue flags.

## Notes

[2026-08-16T23:05:00Z · sase-nb.7] PROPOSED FOLLOW-UP: escalated just check full suite had 7 unrelated failures — test_models_panel_history (3) missing History footer key; fakey usage-limit e2e; test_clear_config_cache_forces_reload golden drifted extra user config keys; test_family_container_badge_does_not_alter_status_chip (format_agent_option unexpected parallel_family_counts); test_agy_captured_failure_disables_small_pool_member StopIteration. None import or call sase flag / flags.* doctor.

[2026-08-16T23:05:29Z · sase-nb.7] Added sase flag {list,new,show} (bare group defaults to list) and flags.registry / flags.overrides / flags.due doctor checks. list/show work in any project; new requires is_sase_managed: true and never cites sase/memory/sase_flags.md. Verified: sase flag -h lists list/new/show alphabetically with the managed-checkout gate; sase flag list prints the empty-registry hint; sase doctor -C flags registers all three checks and is OK on the empty registry; focused tests 32 passed (parser, list/show/new, OK/WARN/ERROR doctor fixtures, new creates a flag bead with today+90 / minor+2); just check lint gates all green (fmt, ruff, mypy, flags, symvision, validate). Scoped lane escalated (Justfile --epic-symbol cleanup after this CLI started using flag_key_chip / flag_due_chip / flag_due_presentation); 31702 passed, 7 unrelated failures recorded as PROPOSED FOLLOW-UP. Also re-exported HistoryWordCompletionMetadata and removed unused artifact-tab action helpers so mypy/symvision/collection could pass.

[2026-08-16T23:06:20Z · sase-nb.7] Verified sase flag list/new/show CLI (managed-checkout gate on new), flags.registry/overrides/due doctor checks with OK/WARN/ERROR fixtures, focused flag/doctor tests, and just check lint gates. Scoped suite escalated on Justfile epic-symbol change; remaining failures are unrelated and recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-nb.2](sase-nb.2.md) ✓ · ⧖ 2026-08-16
- **Depends on:** [sase-nb.4](sase-nb.4.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-nb.9](sase-nb.9.md) ✓ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-nb.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-nb.7/README.md) | [sase-nb.7](sase-nb.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`497d383`](https://github.com/sase-org/sase/commit/497d383aa16a9bbfb24bc001ed9f99fd9e03e2b7) | feat(cli): add sase flag group and flags.\* doctor checks | [sase-nb.7](sase-nb.7.md) | 2026-08-16 19:07:38 EDT |
