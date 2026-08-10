# Bead: sase-ij.6 — Stop conscripting feature agents into the floor bump

[Bead Pages](../README.md) / [sase-ij](README.md) / sase-ij.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wq](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wq/README.md) · **Assignee:** `sase-ij.6` · **Size:** small
**Created:** 2026-08-09 15:20:16 EDT · **Closed:** 2026-08-10 09:14:37 EDT
**Plan:** [202608/core\_window\_ratchet.md](https://github.com/sase-org/sase--plans/blob/main/202608/core_window_ratchet.md)

## Description

retire-conscription: remove published-core-minimum-smoke from feature PRs and master pushes now that the invariant is enforced at the release boundary, and rewrite the three Justfile warnings and the docs that currently tell agents to bump the window by hand.

## Notes

[2026-08-10T13:14:03Z · sase-ij.6] PROPOSED FOLLOW-UP: just check/just check-full fail at the "SASE validation" gate with `init memory --check failed` (wants to update ~/.local/share/chezmoi/home/sase/memory/README.md +2-3), reproducing even on clean master with no repo changes staged. This blocks every agent on this shared host from getting a clean check run until the chezmoi memory README is regenerated/synced (requires explicit owner permission per CLAUDE.md memory-file rules, so out of scope for this phase).

[2026-08-10T13:14:16Z · sase-ij.6] PROPOSED FOLLOW-UP: just validate-committed-plans fails on clean master with `202608/new_task_recent_task_sweep.md:1: error [tale-size-missing] required tale field size is missing`, unrelated to this phase (touches only ci.yml/Justfile/docs/tests). Likely a plan file that predates the tale-size requirement added in 46fbdc07a and needs a backfilled size field.

[2026-08-10T13:14:37Z · sase-ij.6] Removed published-core-minimum-smoke from .github/workflows/ci.yml (its 5 checks now live in release-core-floor-smoke, landed by release-lane). Rewrote the three Justfile floor-bump warnings (_setup:99, rust-install:784, rust-dev-install:844) to explain that the checkout running ahead of the published window is normal dev state now owned by the release-branch reconciler, not an action item; updated the two covering tests in tests/test_justfile_lint.py to match. Fixed a stale docstring reference to the removed job in tools/check_sase_core_rs_bindings. Documented window ownership in docs/rust_backend.md (who owns it, what to do for an unreleased core capability, how to run tools/ratchet_core_window by hand). Verified: YAML parses; no remaining references to published-core-minimum-smoke anywhere in the repo; all just check lint gates pass (fmt, ruff, mypy, pyscripts, test-waits, changelog, patch/stitch terminology, symvision, toobig); just docs-check passes; tests/test_justfile_lint.py passes 35/35 standalone. just check/check-full's SASE-validation and validate-committed-plans gates fail on this host, but reproduce identically on clean master with no changes staged (confirmed via git stash) — pre-existing, unrelated environmental drift, recorded as PROPOSED FOLLOW-UP notes. The full just test run did not finish in this heavily contended shared environment (multiple concurrent agent workspaces running full suites); it reached 99%+ with no failures attributable to this diff before being interrupted by resource contention.

[2026-08-10T13:15:17Z · sase-ij.6] Verified: just check lint gates pass, just docs-check passes, modified test file passes 35/35 standalone, no remaining references to removed CI job exist repo-wide.

## Dependencies

- **Depends on:** [sase-ij.5](sase-ij.5.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ij.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.6/README.md) | [sase-ij.6](sase-ij.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0968318`](https://github.com/sase-org/sase/commit/0968318b17a35e13e539758191cc4ff8f2511478) | ci: retire published-core-minimum-smoke now enforced at release boundary | [sase-ij.6](sase-ij.6.md) | 2026-08-10 09:17:02 EDT |
