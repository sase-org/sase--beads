# Bead: sase-ib.7 — Lock in the win with a cost regression gate

[Bead Pages](../README.md) / [sase-ib](README.md) / sase-ib.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wk](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wk/README.md) · **Assignee:** `sase-ib.7` · **Size:** small
**Created:** 2026-08-09 10:32:38 EDT · **Closed:** 2026-08-10 07:51:07 EDT
**Plan:** [202608/fast\_test\_suite\_1.md](https://github.com/sase-org/sase--plans/blob/main/202608/fast_test_suite_1.md)

## Description

guard: turn the harness into a standing regression gate with committed budgets, and document the new cost model for future contributors.

## Notes

[2026-08-09T19:04:38Z · sase-ib.7] PROPOSED FOLLOW-UP: tests/ace/tui/modals/test_revive_agent_modal.py::test_ctrl_k_loads_more_without_clearing_filter_or_marks fails deterministically on current master (44bf25f84), reproduced in isolation with no contention and unrelated to this phase (verified by git stash of all sase-ib.7 changes). ctrl+k loads page 2 but modal.agents only retains page 1 (assert [alpha] == [alpha, beta]). Blocks a fully green just test/just check-full baseline for anyone landing right now.

[2026-08-09T19:05:19Z · sase-ib.7] PROPOSED FOLLOW-UP: sase/memory/build_and_run.md fails `just fmt-md-check` (and thus `just check`/`just check-full`) on current master with a pre-existing prettier line-wrap drift, unrelated to this phase. It is a generated memory/instruction file I cannot edit without explicit user permission; someone needs to either regenerate it correctly or repair the generator so `sase memory init` output matches prettier formatting.

[2026-08-10T11:38:30Z · sase-ib.7] PROPOSED FOLLOW-UP: Regenerate memory README drift — `just check` currently fails at `sase validate` because `init memory --check` wants to update `~/.local/share/chezmoi/home/sase/memory/README.md` (+2/-3); this is outside the guard diff and requires explicit memory-file update permission.

[2026-08-10T11:50:18Z · sase-ib.7] PROPOSED FOLLOW-UP: Refresh contract manifest for probe core floor contract test — full-lane verification shows `tests/test_contract_manifest.py` fails because marker selection now includes `tests/test_probe_core_floor_tool.py` but `tests/contract_manifest.txt` and the 36-entry budget were not updated; unrelated to the cost gate diff.

[2026-08-10T11:50:31Z · sase-ib.7] PROPOSED FOLLOW-UP: Full pytest lane still has ACE shared-state failures and teardown hang — `just test-scoped` escalated to the full lane, reached 24 failures including agents/changespecs onboarding, footer visibility, artifacts navigation, and then required KeyboardInterrupt during pytest teardown after 516s; this corroborates the active epic note about order-dependent ACE failures/hangs rather than this guard change.

[2026-08-10T11:51:07Z · sase-ib.7] Implemented committed suite-cost budget gate and docs. Verified focused cost/runner/CI/Justfile tests (43 passed), ruff/prettier/script checks, old starting baseline fails the new budget checker as an artificial regression, and just check passes through all lint gates before the unrelated memory README validation drift. Full lane remains blocked by separately noted contract-manifest/ACE failures and teardown hang.

[2026-08-10T11:51:58Z · sase-ib.7] Implemented and verified suite-cost regression budgets: focused cost/runner/CI/Justfile tests passed, old baseline fails the new budget checker as artificial-regression proof, ruff/prettier/script checks passed, and just check reached only the existing memory README validation drift.

## Dependencies

- **Depends on:** [sase-ib.2](sase-ib.2.md) ✓ · ⧖ 2026-08-09
- **Depends on:** [sase-ib.3](sase-ib.3.md) ✓ · ⧖ 2026-08-09
- **Depends on:** [sase-ib.4](sase-ib.4.md) ✓ · ⧖ 2026-08-09
- **Depends on:** [sase-ib.5](sase-ib.5.md) ✓ · ⧖ 2026-08-09
- **Depends on:** [sase-ib.6](sase-ib.6.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ib.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ib.7/README.md) | [sase-ib.7](sase-ib.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ee9603d`](https://github.com/sase-org/sase/commit/ee9603d31e67a10f54b3a13fbf88e7cd55158572) | test: add suite cost regression budgets | [sase-ib.7](sase-ib.7.md) | 2026-08-10 07:52:38 EDT |
