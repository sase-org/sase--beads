# Bead: sase-dh.3 — Agents sidecar prompt and artifact archive written by sase commit

[Bead Pages](../README.md) / [sase-dh](README.md) / sase-dh.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rh/README.md) · **Assignee:** `sase-dh.3` · **Size:** medium
**Created:** 2026-08-01 15:07:01 UTC · **Closed:** 2026-08-01 17:08:43 UTC
**Plan:** [202608/artifact\_persistence\_sidecars.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_persistence_sidecars.md)

## Description

archive: write prompts/<YYYYMM>/ and artifacts/<YYYYMM>/ into the agents sidecar at commit time, with inline artifact links, month indexes, locking, and outbox retry.

## Notes

[2026-08-01T16:43:59Z · sase-dh.3] PROPOSED FOLLOW-UP: Fix pre-existing Symvision private import in bead plan links — src/sase/ace/tui/widgets/artifacts/bead_plan_links.py imports _hierarchical_id_key from another module, causing just check to fail at lint (symvision). Make the helper public or move the shared ordering API.

[2026-08-01T16:44:44Z · sase-dh.3] PROPOSED FOLLOW-UP: Repair pre-existing invalid plan/prompt reverse link — sase validate reports 202607/uppercase_active_subtabs.md has a missing valid prompt link and discontiguous or nested plan-header bullets; sase plan links repair --write may restore it.

[2026-08-01T17:05:18Z · sase-dh.3] PROPOSED FOLLOW-UP: Stabilize current full TUI/visual test baseline — just test passed 24,978 tests but 308 unrelated ACE/onboarding/golden tests failed, dominated by active-state subtab mismatches and broad PNG renderer/state drift; reproduce outside concurrent epic agents and refresh code/tests or pinned environment as appropriate.

[2026-08-01T17:08:43Z · sase-dh.3] Implemented the agents-sidecar prompt/artifact archive with Rust-backed inline rewriting, stable naming and month indexes, content-addressed collision checks, immutable VCS/non-file links, shared locking, Git publication, checkpoint ordering, and durable outbox regeneration. Verified formatting/ruff/mypy, git diff checks, file-size lint, committed-plan validation, 61 focused publication/workflow tests plus an actual idempotent sidecar Git publish; the aggregate check's unrelated Symvision, plan-link, and TUI/visual baseline failures were recorded as PROPOSED FOLLOW-UP notes.

[2026-08-01T17:10:39Z · sase-dh.3] Verified 62 publication-focused tests pass; Ruff, formatting, mypy, diff checks, size lint, and committed-plan validation pass. Aggregate baseline exceptions are recorded as PROPOSED FOLLOW-UP notes.

## Dependencies

- **Depends on:** [sase-dh.1](sase-dh.1.md) ✓
- **Depends on:** [sase-dh.2](sase-dh.2.md) ✓
- **Blocks:** [sase-dh.4](sase-dh.4.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-dh.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dh.3/README.md) | [sase-dh.3](sase-dh.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`149b57e`](https://github.com/sase-org/sase/commit/149b57e4f42fa70fa2bda7dde41a760cc3cc6c53) | feat: archive committed prompts and artifacts | [sase-dh.3](sase-dh.3.md) | 2026-08-01 17:11:23 |
