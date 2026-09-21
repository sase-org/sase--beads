# Bead: sase-14n.4 — Land the TUI import count strictly under its budget

[Bead Pages](../README.md) / [sase-14n](README.md) / sase-14n.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oe](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oe.md) · **Assignee:** `sase-14n.4` · **Size:** small
**Created:** 2026-09-20 17:14:11 EDT · **Closed:** 2026-09-21 11:55:31 EDT
**Plan:** [202609/fix\_triaged\_bug\_and\_ci\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202609/fix_triaged_bug_and_ci_beads.md)

## Description

import_budget: the app import now sits exactly at the 3290 module cap against a strict comparison, so cut at least one startup import or change the boundary semantics with a recorded rationale.

## Dependencies

- **Blocks:** [sase-14n.7](sase-14n.7.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-14n.8](sase-14n.8.md) ◐ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14n.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14n.4/README.md) | [sase-14n.4](sase-14n.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5963c52`](https://github.com/sase-org/sase/commit/5963c52e8261f191531009b029ffa3ccf7afe97e) | fix(tui): defer heap and perf imports out of the app startup closure | [sase-14n.4](sase-14n.4.md) | 2026-09-20 17:46:40 EDT |
