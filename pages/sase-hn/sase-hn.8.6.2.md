# Bead: sase-hn.8.6.2 — Clear the ACE TUI test surface

[Bead Pages](../README.md) / [sase-hn.8.6](sase-hn.8.6.md) / sase-hn.8.6.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-hn.8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hn.8.land/README.md) · **Assignee:** `sase-hn.8.6.2` · **Size:** large
**Created:** 2026-08-09 04:14:59 EDT · **Closed:** 2026-08-09 06:42:26 EDT
**Plan:** [202608/patch\_audit\_gate\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202608/patch_audit_gate_repair.md)

## Description

test-tui-sweep: retire ChangeSpec vocabulary from the 2709 defects under tests/ace/tui by switching canonical call sites to the existing Patch helpers, fixing prose, and annotating genuine retained contracts, keeping the PNG goldens pixel-inert.

## Notes

[2026-08-09T10:42:26Z · sase-hn.8.6.2] Implemented the ACE TUI test terminology sweep. Final strict audit reports 0 defects under tests/ace/tui. Verified with just check (lint plus full non-visual suite via scoped escalation) and just test-visual (570 passed, 1 skipped). PNG goldens were left unchanged.

[2026-08-09T10:44:09Z · sase-hn.8.6.2] Implemented ACE TUI test Patch terminology sweep. Verified strict audit reported 0 defects under tests/ace/tui, git diff --check passed, just check passed, and just test-visual passed with 570 passed, 1 skipped.

## Dependencies

- **Depends on:** [sase-hn.8.6.1](sase-hn.8.6.1.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-hn.8.6.4](sase-hn.8.6.4.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-hn.8.6.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-hn.8.6.2.md) | [sase-hn.8.6.2](sase-hn.8.6.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7feb0b8`](https://github.com/sase-org/sase/commit/7feb0b84b69a0b3a197db2aab5e5ac37c986081c) | test(ace): rename TUI tests to Patch terminology | [sase-hn.8.6.2](sase-hn.8.6.2.md) | 2026-08-09 06:45:04 EDT |
