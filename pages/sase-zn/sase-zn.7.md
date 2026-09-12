# Bead: sase-zn.7 — Attribute and fix the residual ACE heap growth

[Bead Pages](../README.md) / [sase-zn](README.md) / sase-zn.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.03` · **Assignee:** `sase-zn.7` · **Size:** medium
**Created:** 2026-09-11 12:20:23 EDT · **Closed:** 2026-09-12 12:07:38 EDT
**Plan:** [202609/ace\_typing\_lag\_athena.md](https://github.com/sase-org/sase--plans/blob/main/202609/ace_typing_lag_athena.md)

## Description

heap-attrib: add an opt-in heap sampler for the long-lived TUI, attribute whatever remains of the ~12.5 GB anonymous heap after the bounded-stream fix, and fix the retained-object sites it names.

## Notes

[2026-09-12T16:07:38Z · sase-zn.7] Implemented opt-in SASE_TUI_HEAP tracemalloc JSONL sampler, wired startup/shutdown and Statistics probe/help/docs, added heap sampler and session-proc bounded-heap coverage, and verified targeted heap/statistics/session tests plus just check passing.

## Dependencies

- **Depends on:** [sase-zn.1](sase-zn.1.md) ✓ · ⧖ 2026-09-11
- **Depends on:** [sase-zn.4](sase-zn.4.md) ✓ · ⧖ 2026-09-11
- **Blocks:** [sase-zn.8](sase-zn.8.md) ✓ · ⧖ 2026-09-11

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`10bc40e`](https://github.com/sase-org/sase/commit/10bc40e94e024999d6021a82fd483f0be54057a8) | feat: Attribute and fix the residual ACE heap growth (sase-zn.7) | [sase-zn.7](sase-zn.7.md) | 2026-09-12 12:24:51 EDT |
