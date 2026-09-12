# Bead: sase-zt.4 — Documentation sweep and the xprompts memory correction

[Bead Pages](../README.md) / [sase-zt](README.md) / sase-zt.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.06.f0` · **Assignee:** `sase-zt.4` · **Size:** small
**Created:** 2026-09-12 10:33:31 EDT · **Closed:** 2026-09-12 18:41:57 EDT
**Plan:** [202609/queue\_capacity\_budget.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_capacity_budget.md)

## Description

docs: restate capacity as a per-launch budget across the xprompt, ACE, configuration, and runner-slot troubleshooting docs, and correct the stale capacity paragraph in the `sase/memory/xprompts.md` reference memory note.

## Notes

[2026-09-12T22:41:13Z · sase-zt.4] PROPOSED FOLLOW-UP: Investigate test-cost budget regression — `just check-full` functional tests passed (41069 passed, 15 skipped), but test-cost failed hard on `causes.ace_page_enter.cpu` 1064.219 > 1050.000 and `causes.ace_settle_pilot.count` 8718 > 8600.

[2026-09-12T22:41:57Z · sase-zt.4] Updated queue capacity budget docs and xprompts memory; ran sase memory init --no-commit; just check-full passed functional tests (41069 passed, 15 skipped) but failed final test-cost budgets, recorded PROPOSED FOLLOW-UP on sase-zt.4; epic-symbols reported no entries.

## Dependencies

- **Depends on:** [sase-zt.2](sase-zt.2.md) ✓ · ⧖ 2026-09-12
- **Depends on:** [sase-zt.3](sase-zt.3.md) ✓ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zt.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zt.4/README.md) | [sase-zt.4](sase-zt.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`dd1ed61`](https://github.com/sase-org/sase/commit/dd1ed61a4ab21d41d13b138b3c17b99e047746ba) | docs: describe queue capacity budgets | [sase-zt.4](sase-zt.4.md) | 2026-09-12 19:05:53 EDT |
