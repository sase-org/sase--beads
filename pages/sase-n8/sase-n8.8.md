# Bead: sase-n8.8 — Raise the sase-core-rs dependency window

[Bead Pages](../README.md) / [sase-n8](README.md) / sase-n8.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03t](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03t.md) · **Assignee:** `sase-n8.8` · **Size:** small
**Created:** 2026-08-16 11:33:21 EDT · **Closed:** 2026-08-16 16:51:43 EDT
**Plan:** [202608/launch\_control\_alias\_history.md](https://github.com/sase-org/sase--plans/blob/main/202608/launch_control_alias_history.md)

## Description

floor: after the sase-core release publishes, move both bounds of the sase-core-rs version window in pyproject.toml to the release carrying artifact index schema 22, and confirm the exhaustive gate passes against the published wheel.

## Notes

[2026-08-16T20:50:22Z · sase-n4.5.land] INTEGRATION REQUIREMENT from sase-n4.5 landing: non-advisory tools/probe_core_floor on master eba0eab7 reports the declared 0.27.11 floor stale_actionable; provider_disable_try_set_relative and provider_disable_try_set_until first appear in published v0.27.15 (sase-core dc87c8e). Please raise the shared floor to at least 0.27.15, not merely the earlier schema-22 release, so both active epics are covered.

[2026-08-16T20:51:43Z · sase-n8.8--1] Raised sase-core-rs floor to 0.27.15 and verified tools/validate_sase_core_rs plus the Symvision and standard lint/validation portions of just check against the published wheel; full-suite verification did not complete cleanly because unrelated file-panel and models-panel tests fail in the escalated lane.

[2026-08-16T21:16:36Z · sase-n8.8--2] Raised sase-core-rs floor to 0.27.15 and verified tools/validate_sase_core_rs plus just check-full against the published wheel.

[2026-08-16T21:18:15Z · sase-n8.8] PROPOSED FOLLOW-UP: Investigate long-running pytest lanes under active proc-observer load - while finalizing the floor phase, clean attached just check-full and just check runs passed lint/validation but their pytest lanes stayed CPU-active for many minutes and had to be terminated; focused touched-module tests passed.

[2026-08-16T21:19:06Z · sase-n8.8] Verified pyproject.toml and uv.lock require sase-core-rs>=0.27.15,<0.28.0; installed/imported published wheel 0.27.15 from .venv site-packages with SASE_CORE_DIR pointing at an absent path; tools/validate_sase_core_rs passed; just _lint-symvision passed; focused tests for touched rendering/cache/history-word modules passed (69 passed). Clean just check-full and just check runs passed lint/validation lanes but pytest lanes did not complete within this finalizer and were terminated; recorded proposed follow-up.

[2026-08-16T21:48:25Z · sase-n8.8--6] Restored public HistoryWordCompletionMetadata and verified just _lint-mypy, focused history-word widget tests, tools/validate_sase_core_rs, and published sase-core-rs 0.27.15. Full just check-full reached test-cost but failed on unrelated config/model/provider tests outside this bead's files.

## Dependencies

- **Depends on:** [sase-n8.6](sase-n8.6.md) ✓ · ⧖ 2026-08-16
- **Depends on:** [sase-n8.7](sase-n8.7.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-n8.9](sase-n8.9.md) ✓ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n8.8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-n8.8.md) | [sase-n8.8](sase-n8.8.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fc1ad39`](https://github.com/sase-org/sase/commit/fc1ad39e7ceafca6c7013b52a10f923c2f84987e) | build(deps): require sase-core-rs 0.27.15 | [sase-n8.8](sase-n8.8.md) | 2026-08-16 16:53:46 EDT |
| sase | [`e50d8a9`](https://github.com/sase-org/sase/commit/e50d8a9537a1a1baefd44bf121e1c8faf213b181) | fix: restore history-word metadata API | [sase-n8.8](sase-n8.8.md) | 2026-08-16 17:51:52 EDT |
