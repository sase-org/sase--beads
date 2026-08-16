# Bead: sase-m6.6.1.3 — Generalize the Python reference evaluator

[Bead Pages](../README.md) / [sase-m6.6.1](sase-m6.6.1.md) / sase-m6.6.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m6.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.6.md) · **Assignee:** `sase-m6.6.1.3` · **Size:** medium
**Created:** 2026-08-15 06:17:51 EDT · **Closed:** 2026-08-15 07:49:22 EDT
**Plan:** [202608/unified\_artifacts\_query\_1.md](https://github.com/sase-org/sase--plans/blob/main/202608/unified_artifacts_query_1.md)

## Description

python_reference: make query_facade's Python-owned per-row evaluator consume the same compiled profile and typed/coerced Artifact fields as Rust, implement the shared field, sigil, predicate, macro, searchable-text and boolean semantics, and expand cross-language fixtures so the Python reference evaluator and Rust batch evaluator return identical matches and errors for every pane profile.

## Notes

[2026-08-15T11:20:44Z · sase-m6.6.1.3] PROPOSED FOLLOW-UP: Extend ArtifactQuerySchema with field match/control semantics — current compiled profiles encode type/searchability/repeatability but not exact-vs-substring matching or non-row controls such as stitches limit, so flat-pane migration must preserve those explicitly.

[2026-08-15T11:48:59Z · sase-m6.6.1.3] PROPOSED FOLLOW-UP: Fix proc-shell Rust binding drift - just check escalates to the full suite when Justfile changes, and the full run currently fails procs/bindings tests because sase_core_rs still returns proc schema v2 and lacks begin_proc_settlement/claim_proc_supervisor/finish_proc/request_proc_stop/reserve_proc.

[2026-08-15T11:49:22Z · sase-m6.6.1.3] Implemented profile-driven Python Artifacts query parsing/evaluation through query_facade with typed/coerced Artifact rows, boolean sigil/macro/predicate semantics, flat repeatable/negated fields, provider string-list/date/bool/int coercion, Patch parity tests against the current Rust batch path, and focused profile/facade coverage. Verified with just install, focused ruff/mypy/pytest, adjacent query/profile/facade/golden tests, symvision/toobig, and just check through lint/SASE validation; just check's full-suite test lane failed only existing proc-shell Rust binding drift recorded as a PROPOSED FOLLOW-UP.

[2026-08-15T11:50:45Z · sase-m6.6.1.3] Verified just install, focused Ruff/mypy/pytest, adjacent query/profile/facade tests, Symvision/Toobig, and just check through lint/SASE validation; full-suite lane failed only proc-shell Rust binding drift recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-m6.6.1.1](sase-m6.6.1.1.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-m6.6.1.5](sase-m6.6.1.5.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-m6.6.1.6](sase-m6.6.1.6.md) ✓ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m6.6.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m6.6.1.3/README.md) | [sase-m6.6.1.3](sase-m6.6.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`682cc31`](https://github.com/sase-org/sase/commit/682cc31b37dae72dea9183c5b28d386dbb5898cf) | feat(query): add profile-driven artifact query reference | [sase-m6.6.1.3](sase-m6.6.1.3.md) | 2026-08-15 07:51:35 EDT |
