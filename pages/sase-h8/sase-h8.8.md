# Bead: sase-h8.8 — A committed flake baseline that fails the build on new flakes

[Bead Pages](../README.md) / [sase-h8](README.md) / sase-h8.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.v5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.v5/README.md) · **Assignee:** `sase-h8.8` · **Size:** medium
**Created:** 2026-08-07 18:06:04 EDT · **Closed:** 2026-08-08 10:11:21 EDT
**Plan:** [202608/parallel\_suite\_flake\_class.md](https://github.com/sase-org/sase--plans/blob/main/202608/parallel_suite_flake_class.md)

## Description

gate: commit a flake baseline file and a gate that fails when the health store's reproducible-flake set exceeds it, wire the gate into the exhaustive lane and a CI contention job, and add the lint check that stops the retired ad-hoc wait helpers from coming back.

## Notes

[2026-08-08T14:11:04Z · sase-h8.8] PROPOSED FOLLOW-UP: Fix content-layout schema version test - tests/test_content_layout.py::test_project_home_and_chezmoi_named_paths_are_canonical still expects schema_version 2 while _resolve_content_layout returns 3, causing just check/full-suite failure.

[2026-08-08T14:11:21Z · sase-h8.8] Verified: just install completed; focused pytest for selection_health, wait-helper lint, correlation, and Justfile/CI wiring passed (65 passed); tools/check_test_wait_helpers passed; tools/selection_health --fail-on-new-flake passed after the empty baseline marker; just check ran and failed only on unrelated tests/test_content_layout.py::test_project_home_and_chezmoi_named_paths_are_canonical schema_version expectation, recorded as PROPOSED FOLLOW-UP.

[2026-08-08T14:13:00Z · sase-h8.8] Verified just install; focused pytest selection-health/wait-helper coverage passed; tools/check_test_wait_helpers passed; tools/selection_health --fail-on-new-flake passed; just check reached full-suite lane and failed only unrelated content-layout schema assertion recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-h8.4](sase-h8.4.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-h8.5](sase-h8.5.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-h8.6](sase-h8.6.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-h8.7](sase-h8.7.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-h8.9](sase-h8.9.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h8.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.8/README.md) | [sase-h8.8](sase-h8.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c902dd7`](https://github.com/sase-org/sase/commit/c902dd71cd0757cb8997cdfbb5a125b83a50df49) | feat: gate new reproducible test flakes | [sase-h8.8](sase-h8.8.md) | 2026-08-08 10:13:41 EDT |
