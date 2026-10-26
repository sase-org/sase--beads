# Bead: sase-1oj.3 — Consolidate sase-core integration-test binaries

[Bead Pages](../README.md) / [sase-1oj](README.md) / sase-1oj.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.ae](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.ae.md) · **Assignee:** `sase-1oj.3` · **Size:** medium
**Created:** 2026-10-26 16:07:28 EDT
**Plan:** [202610/athena\_disk\_write\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202610/athena_disk_write_diet.md)

## Description

core-test-binaries: merge sase_core's 23 and sase_macro_lsp's 10 integration-test files into one binary per crate. Isolate tests that mutate process-global state, update every --test reference, and record the before/after link bytes.

## Dependencies

- **Depends on:** [sase-1oj.1](sase-1oj.1.md) ✓ · ⧖ 2026-10-26
- **Depends on:** [sase-1oj.2](sase-1oj.2.md) ◐ · ⧖ 2026-10-26
- **Blocks:** [sase-1oj.6](sase-1oj.6.md) ◐ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1oj.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1oj.3/README.md) | [sase-1oj.3](sase-1oj.3.md) | 0 |
