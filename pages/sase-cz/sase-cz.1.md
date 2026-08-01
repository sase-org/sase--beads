# Bead: sase-cz.1 — Generic gate presentation panel and origin fields

[Bead Pages](../README.md) / [sase-cz](README.md) / sase-cz.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.qw](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.qw/README.md) · **Assignee:** `sase-cz.1` · **Size:** medium
**Created:** 2026-08-01 11:03:46 UTC · **Closed:** 2026-08-01 11:24:07 UTC
**Plan:** [202608/bead\_notification\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_notification_panel.md)

## Description

contract: add the `presentation.panel` and `presentation.origin_agent` gate request fields, their normalization and validation, their projection into notification `action_data`, the `GateAdapter.display_title` field, the matching `sase gate create` options, and the gate documentation and skill-source updates.

## Notes

[2026-08-01T11:17:56Z · sase-cz.1] PROPOSED FOLLOW-UP: Repair missing bead_notification_panel prompt-to-plan link — sase validate reports 202608/prompts/bead_notification_panel.md targets absent ../bead_notification_panel.md.

[2026-08-01T11:22:22Z · sase-cz.1] PROPOSED FOLLOW-UP: Update August-cutover SDD write fixtures with required plan metadata — two tests/test_sdd_file_writes.py cases now fail because generated 202608 tale plans omit title and goal.

[2026-08-01T11:22:30Z · sase-cz.1] PROPOSED FOLLOW-UP: Stabilize slow-tools PNG snapshot under full parallel suite — test_agents_slow_tool_calls_fold_levels_png_snapshots timed out waiting for the loaded tools footer while 25 workers ran.

[2026-08-01T11:24:07Z · sase-cz.1] Verified gate presentation normalization/projection, protected action_data keys, adapter display titles, CLI overrides/help, docs, and generated skill source with 94 focused tests passing; formatting, Ruff, mypy, pyscripts, changelog, Symvision, toobig, and committed-plan validation passed; full suite reached 25,024 passes with two unrelated August-cutover fixture failures and one contention-only visual timeout, and that visual test passed in isolation.

## Dependencies

- **Blocks:** [sase-cz.2](sase-cz.2.md) ◐
- **Blocks:** [sase-cz.3](sase-cz.3.md) ◐
- **Blocks:** [sase-cz.4](sase-cz.4.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-cz.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-cz.1/README.md) | [sase-cz.1](sase-cz.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`d02ab49`](https://github.com/sase-org/sase/commit/d02ab49e58e81a1860c2f11f83c5a61c76c94e2a) | feat(gates): add generic presentation metadata | [sase-cz.1](sase-cz.1.md) | 2026-08-01 11:25:51 |
