# Bead: sase-dh.1 — Rust prompt-artifact contract and cross-repo header links

[Bead Pages](../README.md) / [sase-dh](README.md) / sase-dh.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rh/README.md) · **Assignee:** `sase-dh.1` · **Size:** medium
**Created:** 2026-08-01 15:06:13 UTC · **Closed:** 2026-08-01 15:43:47 UTC
**Plan:** [202608/artifact\_persistence\_sidecars.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_persistence_sidecars.md)

## Description

core: add the Rust-owned staging manifest, pool naming, prompt link rewriting, ARTIFACTS header section, and absolute PLAN/PROMPT targets, plus their pyo3 bindings.

## Notes

[2026-08-01T15:43:00Z · sase-dh.1] PROPOSED FOLLOW-UP: Repair the historical uppercase_active_subtabs plan/prompt link pair — `sase plan links validate` reports a missing reverse link and a discontiguous/nested header in the clean plans sidecar, which blocks `just check` before its test stage.

[2026-08-01T15:43:09Z · sase-dh.1] PROPOSED FOLLOW-UP: Reconcile the current ACE test baseline with the Files-first Artifacts navigation and onboarding copy — the full `just test` run produced 307 unrelated failures (24,986 passed), dominated by tests expecting the prior PRs-first state/older copy and cascading visual timeouts, plus one bead lock-contention regression.

[2026-08-01T15:43:21Z · sase-dh.1] PROPOSED FOLLOW-UP: Reconcile the current ACE test baseline with the Files-first Artifacts navigation and onboarding copy — the full `just test` run produced 307 unrelated failures (24,986 passed), dominated by tests expecting the prior PRs-first state/older copy and cascading visual timeouts, plus one bead lock-contention regression.

[2026-08-01T15:43:47Z · sase-dh.1] Implemented the Rust prompt-artifact manifest/naming/selection/rewrite contract, header schema v3 with ARTIFACTS and absolute PLAN/PROMPT targets, all six PyO3 bindings, and the Python header adapter/smoke coverage. Verified cargo fmt --check, cargo clippy --workspace --all-targets -D warnings, and cargo test --workspace all pass; focused Python header tests pass (6/6), and main formatting plus all lint gates pass. The remaining plan-link validation and broad ACE baseline failures were unrelated and recorded as PROPOSED FOLLOW-UP notes. Cargo versions remain release-plz-owned; the published Python dependency floor should advance after this core release lands.

## Dependencies

- **Blocks:** [sase-dh.2](sase-dh.2.md) ✓
- **Blocks:** [sase-dh.3](sase-dh.3.md) ✓
- **Blocks:** [sase-dh.4](sase-dh.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-dh.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dh.1/README.md) | [sase-dh.1](sase-dh.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase-core | [`sase-core@f97c7f1`](https://github.com/sase-org/sase-core/commit/f97c7f141750f0080a72653db5d5470f2fd904d6) | feat: add prompt artifact contract | [sase-dh.1](sase-dh.1.md) | 2026-08-01 15:45:40 |
| sase | [`20f6735`](https://github.com/sase-org/sase/commit/20f673572dcf86d36c3ba4e460cf7e6f32137c84) | feat: support artifacts in plan headers | [sase-dh.1](sase-dh.1.md) | 2026-08-01 15:46:24 |
