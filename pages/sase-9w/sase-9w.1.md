# Bead: sase-9w.1 — Rust core owns the description grammar

[Bead Pages](../README.md) / [sase-9w](README.md) / sase-9w.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9w.1` · **Size:** medium
**Created:** 2026-07-26 17:59:59 UTC · **Closed:** 2026-07-27 10:12:57 UTC
**Plan:** [202607/axe\_multiline\_descriptions.md](https://github.com/sase-org/sase--plans/blob/main/202607/axe_multiline_descriptions.md)

## Description

core_description_grammar: teach sase_core's AXE config authority the summary/body description grammar — add a `split_axe_description` binding that normalizes and splits one description, add flag-gated shape diagnostics for a blank summary, an over-long summary, a missing blank separator line, and an over-long description, and release the crate.

## Dependencies

- **Blocks:** [sase-9w.2](sase-9w.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9w.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9w.1/README.md) | [sase-9w.1](sase-9w.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@740aa4f`](https://github.com/sase-org/sase-core/commit/740aa4f06421f076f678a7768a9e9cec2415f81f) | feat(axe): add description summary-body grammar (sase-9w.1) | [sase-9w.1](sase-9w.1.md) | 2026-07-26 18:10:14 |
