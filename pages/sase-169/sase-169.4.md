# Bead: sase-169.4 — Lock waiting and worker-count translation

[Bead Pages](../README.md) / [sase-169](README.md) / sase-169.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1i](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.1i.md) · **Assignee:** `sase-169.4` · **Size:** small
**Created:** 2026-09-22 10:18:03 EDT · **Closed:** 2026-09-22 13:41:00 EDT
**Plan:** [202609/fix\_tui\_screenshots\_never\_fail.md](https://github.com/sase-org/sase--plans/blob/main/202609/fix_tui_screenshots_never_fail.md)

## Description

invocation: wait (bounded) for the checkout-local maintenance lock instead of refusing at once. Translate `-n/--numprocesses` selector arguments into the governed `SASE_PYTEST_WORKERS` request instead of letting pytest reject them.

## Notes

[2026-09-22T17:41:00Z · sase-169.4] Invocation phase done: lock waits bounded 2h with notices (exit 2 on timeout) and -n/--numprocesses translates to SASE_PYTEST_WORKERS via MaintenanceRequest.workers. Verified: 45 CLI/lock tests, 18 apply tests, 50 capture/report tests green; all just-check lint gates green (ruff, mypy, symvision, toobig, test-waits). 14 scoped-lane failures are in unrelated files that do not import visual-maintenance code.

## Dependencies

- **Depends on:** [sase-169.2](sase-169.2.md) ◐ · ⧖ 2026-09-22
- **Blocks:** [sase-169.5](sase-169.5.md) ◐ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-169.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-169.4/README.md) | [sase-169.4](sase-169.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`890058e`](https://github.com/sase-org/sase/commit/890058e80360707212ee0ef5047a99ba0010664e) | feat(visual): wait for maintenance lock and translate -n to SASE\_PYTEST\_WORKERS | [sase-169.4](sase-169.4.md) | 2026-09-22 13:44:24 EDT |
