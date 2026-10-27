# Bead: sase-1oj.3 — Consolidate sase-core integration-test binaries

[Bead Pages](../README.md) / [sase-1oj](README.md) / sase-1oj.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.ae](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.ae.md) · **Assignee:** `sase-1oj.3` · **Size:** medium
**Created:** 2026-10-26 16:07:28 EDT · **Closed:** 2026-10-26 18:49:44 EDT
**Plan:** [202610/athena\_disk\_write\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202610/athena_disk_write_diet.md)

## Description

core-test-binaries: merge sase_core's 23 and sase_macro_lsp's 10 integration-test files into one binary per crate. Isolate tests that mutate process-global state, update every --test reference, and record the before/after link bytes.

## Notes

[2026-10-26T22:49:09Z · sase-1oj.3] core-test-binaries done in sase-core@651d1933+worktree: tests/integration/main.rs per crate (21 sase_core mods incl. notification_store_parity/ as submodule; 8 sase_macro_lsp mods). 4 isolation keep-outs stay standalone: tests/artifact_ref_commit_budget.rs (process-global SASE_ budget env, single-test-by-design), tests/hermetic_test_env.rs (canary asserts no SASE_* set; sharing a process with env-mutating tests would make it flaky), tests/jsonrpc_stdio_model_shortcut.rs + tests/jsonrpc_stdio_model_alias_shortcut.rs (both race on SASE_MACRO_MODEL_CATALOG). Evidence: integration-test executables 34 -> 6 binaries, 3377461552 -> 606486112 bytes (3.377 -> 0.606 GB, ~2.77 GB / ~82% less per test build); integration test count 433 -> 433 (sase_core 407 -> 405+1+1, lsp 26 -> 24+1+1). No --test <name> references exist in either repo (grepped scripts/check.sh, justfile, .github/workflows, docs, sase tools/); updated tests/notification_store_parity/main.rs doc comment and 2 stale paths in docs/contribute/rust-backend.md. Verify: sase tool run check passed exit-zero (~15 min, run 81e7a9fb), warm check.sh test re-run 361s green.

[2026-10-26T22:49:44Z · sase-1oj.3] Merged into one integration binary per crate (4 documented isolation keep-outs stay standalone). Verified: sase tool run check exit-zero; 34->6 test binaries, 3.377->0.606 GB, 433->433 tests; no --epic-symbol entries remain.

## Dependencies

- **Depends on:** [sase-1oj.1](sase-1oj.1.md) ✓ · ⧖ 2026-10-26
- **Depends on:** [sase-1oj.2](sase-1oj.2.md) ✓ · ⧖ 2026-10-26
- **Blocks:** [sase-1oj.6](sase-1oj.6.md) ✓ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1oj.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1oj.3/README.md) | [sase-1oj.3](sase-1oj.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@b12e581`](https://github.com/sase-org/sase-core/commit/b12e5815289b1a83c244ab2bc7d620fa3eb662be) | test(core): merge integration tests into one binary per crate | [sase-1oj.3](sase-1oj.3.md) | 2026-10-26 18:52:13 EDT |
| sase | [`60498dc`](https://github.com/sase-org/sase/commit/60498dcb5ec08bd945a8e89055c74e182065fbab) | docs(rust-backend): point test paths at consolidated integration targets | [sase-1oj.3](sase-1oj.3.md) | 2026-10-26 18:56:43 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1oj.3][1] | check full description and notes | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1oj.3/README.md

<!-- sase:referenced-by:end -->
