# Bead: sase-rr.2 — Make pluggable finalizers unconditional and delete the old path

[Bead Pages](../README.md) / [sase-rr](README.md) / sase-rr.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.096](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.096.md) · **Assignee:** `sase-rr.2` · **Size:** medium
**Created:** 2026-08-21 13:05:42 UTC · **Closed:** 2026-08-21 16:15:07 UTC
**Plan:** [202608/retire\_pluggable\_finalizers.md](https://github.com/sase-org/sase--plans/blob/main/202608/retire_pluggable_finalizers.md)

## Description

retire-legacy: delete the pluggable_finalizers flag and Off branch, extract any still-needed reconciliation helpers from the deprecated controller, remove beta-only config, environment, baseline, metric, and artifact writers, and preserve only deliberate historical readers.

## Notes

[2026-08-21T16:13:41Z · sase-rr.2] PROPOSED FOLLOW-UP: just check feature-flag lint remains red on pre-existing closed_survives (sase-qq/plugin_catalog_scoped_latest, sase-qf/prettier_enabled) and orphan sase-rc (artifact_links); this phase adds only a grace warning for live flag bead sase-ro until land closes it after the combined tree is green.

[2026-08-21T16:14:06Z · sase-rr.2] PROPOSED FOLLOW-UP: just check test-scoped escalates to the full suite (core-identity-changed, rename-or-delete, src-data-asset) because this phase deleted commit_finalizer.py and edited default_config.yml/sase.schema.json; land should run just check-full through a monitor.

[2026-08-21T16:14:23Z · sase-rr.2] PROPOSED FOLLOW-UP: master Symvision still flags private cross-file imports in declaration.py; toobig still flags declaration.py at 1027 lines. Not introduced by this phase.

[2026-08-21T16:15:07Z · sase-rr.2] Pluggable finalizers are unconditional: invoke always resolves the sealed plan, appends /sase_final, mints the turn nonce, and runs the generic controller; FeatureFlag.pluggable_finalizers is gone from the registry and schema; run_commit_finalizer and SASE_DISABLE_COMMIT_STOP_HOOK / commit.finalizer.{enabled,max_passes} adapters are deleted; new runs write only finalizer_baseline.json / finalizer_result.json with historical read fallbacks. Verified: workspace sase flag show pluggable_finalizers is unknown; tools/check_feature_flags --static is green; just validate is green; fmt/ruff/mypy are green; 225 focused finalizer/invocation/baseline/telemetry tests passed. epic-symbols: no leftovers. Remaining just check red is pre-existing flag lint (sase-qq/sase-qf/sase-rc) plus a grace warning for sase-ro.

[2026-08-21T16:16:15Z · sase-rr.2] Pluggable finalizers are unconditional: invoke always resolves the sealed plan, appends /sase_final, mints the turn nonce, and runs the generic controller; FeatureFlag.pluggable_finalizers is gone from the registry and schema; run_commit_finalizer and SASE_DISABLE_COMMIT_STOP_HOOK / commit.finalizer.{enabled,max_passes} adapters are deleted; new runs write only finalizer_baseline.json / finalizer_result.json with historical read fallbacks. Verified: workspace sase flag show pluggable_finalizers is unknown; tools/check_feature_flags --static is green; just validate is green; fmt/ruff/mypy are green; 225 focused finalizer/invocation/baseline/telemetry tests passed. epic-symbols: no leftovers. Remaining just check red is pre-existing flag lint (sase-qq/sase-qf/sase-rc) plus a grace warning for sase-ro.

## Dependencies

- **Depends on:** [sase-rr.1](sase-rr.1.md) ✓ · ⧖ 2026-08-21
- **Blocks:** [sase-rr.3](sase-rr.3.md) ✓ · ⧖ 2026-08-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rr.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rr.2/README.md) | [sase-rr.2](sase-rr.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2f9c4ae`](https://github.com/sase-org/sase/commit/2f9c4ae2955e680f5da2249e20cccca15e0b972c) | feat(finalizers)!: make pluggable finalizers the only completion path | [sase-rr.2](sase-rr.2.md) | 2026-08-21 16:19:53 UTC |
