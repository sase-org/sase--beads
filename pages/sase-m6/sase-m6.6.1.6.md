# Bead: sase-m6.6.1.6 — Cut Patch over to the shared inline filter bar

[Bead Pages](../README.md) / [sase-m6.6.1](sase-m6.6.1.md) / sase-m6.6.1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m6.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.6.md) · **Assignee:** `sase-m6.6.1.6` · **Size:** large
**Created:** 2026-08-15 06:18:16 EDT · **Closed:** 2026-08-16 00:50:18 EDT
**Plan:** [202608/unified\_artifacts\_query\_1.md](https://github.com/sase-org/sase--plans/blob/main/202608/unified_artifacts_query_1.md)

## Description

patch_bar: configure the Patch contract with boolean=true and migrate its boolean grammar, sigils, status macros and Rust corpus to the shared engine; replace QueryEditModal with a persistent inline FilterBar providing completion, live match count, coverage and Escape rollback; move #N saves into submit handling, make f open the bar, make p rewrite only project scope, and verify slots, history and stable selection restoration never affect a hidden pane.

## Notes

[2026-08-16T04:50:18Z · sase-m6.6.1.6] Implemented approved Patch inline filter bar. Verified focused nonvisual suite (206 passed), Patch/help/onboarding visual snapshots (13 passed), artifact j/k benchmark with Patch p95 under 9 ms, and git diff --check. Required just check passed fmt, Ruff, mypy, and project lint gates before stopping on known unrelated Symvision unused-public findings.

## Dependencies

- **Depends on:** [sase-m6.6.1.2](sase-m6.6.1.2.md) ✓ · ⧖ 2026-08-15
- **Depends on:** [sase-m6.6.1.3](sase-m6.6.1.3.md) ✓ · ⧖ 2026-08-15
- **Depends on:** [sase-m6.6.1.4](sase-m6.6.1.4.md) ✓ · ⧖ 2026-08-15
- **Depends on:** [sase-m6.6.1.5](sase-m6.6.1.5.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-m6.6.1.7](sase-m6.6.1.7.md) ◐ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m6.6.1.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.6.1.6.md) | [sase-m6.6.1.6](sase-m6.6.1.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3c3909c`](https://github.com/sase-org/sase/commit/3c3909c314d2c501ba58fe14ebf1765f70195460) | feat(tui): add inline Patch filter bar | [sase-m6.6.1.6](sase-m6.6.1.6.md) | 2026-08-16 00:54:18 EDT |
