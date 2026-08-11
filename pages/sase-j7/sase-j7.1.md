# Bead: sase-j7.1 — Fix the confirmed xprompt VCS-tag cache leak

[Bead Pages](../README.md) / [sase-j7](README.md) / sase-j7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-j0.w1.f0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j0.w1.f0/README.md) · **Assignee:** `sase-j7.1` · **Size:** medium
**Created:** 2026-08-10 15:44:32 EDT · **Closed:** 2026-08-10 16:23:11 EDT
**Plan:** [202608/fix\_sase\_ct\_flake\_class.md](https://github.com/sase-org/sase--plans/blob/main/202608/fix_sase_ct_flake_class.md)

## Description

vcs-cache - give the caches derived from workspace-provider metadata a real invalidation entry point and restore them on teardown, so a test that fakes plugin metadata stops poisoning every later test in its worker.

## Notes

[2026-08-10T20:23:11Z · sase-j7.1] Fixed the confirmed xprompt VCS-tag cache leak (vcs-cache phase): added sase.workspace_provider.reset_workflow_metadata_caches() as the single invalidation entry point clearing get_all_workflow_metadata plus all derived caches (both mirrored _VCS_TAG_PATTERN/_VCS_TAG_EMBEDDED_PATTERN/_VCS_REPLACE_PATTERN copies, _VCS_UNDERSCORE_NORMALIZER, _LAUNCH_XPROMPT_AT_REF_RE, and renamed _workflow_names -> known_workflow_names); made tests/_workspace_provider_helpers.py's patch_*_metadata restore on monkeypatch teardown (not just setup) via a _TeardownResetTrigger that fires reset_workflow_metadata_caches() on both patch and undo; added an autouse snapshot/restore backstop fixture in tests/conftest.py. Verified: both plan reproduction commands pass (poisoner tests/test_removed_hg_workspace_workflow.py followed by each of the three previously-poisoned victims), new tests/test_workspace_metadata_cache_teardown.py regression test passes now and was confirmed to fail on the parent commit, and 'just check' is green (14/14 gates, scoped test lane escalated to the full suite because tests/conftest.py changed).

## Dependencies

- **Blocks:** [sase-j7.4](sase-j7.4.md) ✓ · ⧖ 2026-08-10
- **Blocks:** [sase-j7.5](sase-j7.5.md) ◐ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-j7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j7.1/README.md) | [sase-j7.1](sase-j7.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c052094`](https://github.com/sase-org/sase/commit/c0520947de793ff7c10422d4cf18fef19f81f5b4) | fix(cache): give workspace-provider metadata caches a real invalidation entry point | [sase-j7.1](sase-j7.1.md) | 2026-08-10 16:24:22 EDT |
