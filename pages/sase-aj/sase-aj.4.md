# Bead: sase-aj.4 — Deterministic bead projection output

[Bead Pages](../README.md) / [sase-aj](README.md) / sase-aj.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-aj.4` · **Size:** medium
**Created:** 2026-07-28 20:21:43 UTC · **Closed:** 2026-07-28 20:47:01 UTC
**Plan:** [202607/beads\_commit\_consolidation.md](https://github.com/sase-org/sase--plans/blob/main/202607/beads_commit_consolidation.md)

## Description

detproj: make `issues.jsonl` and every other regenerated projection byte-stable across all writers so clones never dirty their worktree with pure reorders that later get swept into commits under recycled semantic messages.

## Notes

[2026-07-28T20:45:36Z · sase-aj.4] Implemented deterministic projection ordering in sase-core: reducer and JSONL exporter now share canonical ID ordering, eliminating the plan-first vs ID-order writer oscillation. Added a cross-writer byte-stability regression covering mutable saves, direct reducer serialization, explicit export/rebuild, reversed event-stream input, and manifest stability. Verified with cargo fmt --check, focused regression test, cargo test --workspace, cargo clippy --workspace --all-targets -- -D warnings, and git diff --check.

## Dependencies

- **Depends on:** [sase-aj.1](sase-aj.1.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-aj.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-aj.4/README.md) | [sase-aj.4](sase-aj.4.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@112a645`](https://github.com/sase-org/sase-core/commit/112a6450f45ee39893b2708dad49c1e137993196) | fix(beads): stabilize regenerated projection ordering | [sase-aj.4](sase-aj.4.md) | 2026-07-28 20:48:36 |
