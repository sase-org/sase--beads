# Bead: sase-1ph.4 — Restore bob-cli's manual-heading-number predicate fix

[Bead Pages](../README.md) / [sase-1ph](README.md) / sase-1ph.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5f.final.f0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5f.final.f0.md) · **Assignee:** `sase-1ph.4` · **Size:** small
**Created:** 2026-10-28 20:03:00 EDT · **Closed:** 2026-10-28 20:19:10 EDT
**Plan:** [202610/recover\_handoff\_lost\_edits.md](https://github.com/sase-org/sase--plans/blob/main/202610/recover_handoff_lost_edits.md)

## Description

heading-predicate: apply the recovered bob-cli-d7.land--code patch to bob-cli src/native/highlights_ref/create.rs (has_manual_number plus pandoc-backed regressions) and verify it.

## Notes

[2026-10-29T00:19:10Z · sase-1ph.4] Applied the recovered has_manual_number predicate and Pandoc-backed regressions to src/native/highlights_ref/create.rs on current bob-cli master. Verified with sase tool run check ToolRun f544eca67bbc89bca1a9a06e237ede21 (pass; 3,874 tests), including all three section_numbering regressions with Pandoc 3.1.11.1 installed; git diff --check clean. epic-symbol scan returned no entries.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ph.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ph.4/README.md) | [sase-1ph.4](sase-1ph.4.md) | 0 |
