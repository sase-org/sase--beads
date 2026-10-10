# Bead: sase-1j6.5 — The healer, at-most-once ledger, and auto-restart CLI

[Bead Pages](../README.md) / [sase-1j6](README.md) / sase-1j6.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.47.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.47.linker.w0.md) · **Assignee:** `sase-1j6.5` · **Size:** medium
**Created:** 2026-10-09 15:02:06 EDT · **Closed:** 2026-10-09 19:32:47 EDT
**Plan:** [202610/update\_skew\_agent\_auto\_restart.md](https://github.com/sase-org/sase--plans/blob/main/202610/update_skew_agent_auto_restart.md)

## Description

healer: implement `sase agent auto-restart run`, which claims the ledger, classifies the failure, checks quiescence, runs the fresh-interpreter probe, applies the skip rules and storm breaker, preserves evidence, and relaunches headlessly through plan/execute_agent_restart with provenance. Also adds the config block, the beta flag, and the list/show/resume commands.

## Notes

[2026-10-09T23:32:29Z · sase-1j6.5--1] PROPOSED FOLLOW-UP: Add a decisions-web record for the update-skew auto-restart design (at-most-once per lineage, pre-provider only); skipped per epic DECISIONS (decision_record=no), no memory note edited

[2026-10-09T23:32:47Z · sase-1j6.5--1] Healer phase done. Fixed check failure cb84aa1c199678076bea258449aad98b (lint feature-flags): regenerated stale feature_flags schema block via tools/sync_feature_flags_schema --write; check_feature_flags now exits 0. Verified: 18/18 healer tests, 66 passed healer+scan+core suites, 46 passed restart plan+execute+cli suites, ruff check+format and mypy clean on touched files. CLI smoke via .venv/bin/sase: auto-restart --help/list/run/resume/show/scan, bare delegates to list, beta-off run gates exit 3. epic-symbols clean. Flag bead sase-1jb intentionally left open for land phase.

[2026-10-09T23:49:32Z · sase-1j6.5--1] PROPOSED FOLLOW-UP: just _lint-symvision is red on the clean base too, proven via git stash -u experiment. 12 findings reproduce identically without this phase changes: 6 wire classes in core/agent_auto_restart_wire.py plus 6 facade seams in core/agent_auto_restart_facade.py. This phase already consumed 4 of the facade ones. Pre-existing debt, not caused by sase-1j6.5.

[2026-10-09T23:49:41Z · sase-1j6.5--1] PROPOSED FOLLOW-UP: 18 residual symvision unused-public findings live in this phase new auto_restart files. 14 are consumed via ledger_mod/storm_mod attribute imports in healer.py and will clear once the tree is committed, since symvision resolves module aliases from git-tracked files only. True future API with no current consumer: resolve_pending_targets for bead sase-1j6.6 and episode_dedup_key for bead sase-1j6.7 need --epic-symbol rows keyed to those beads, to be added by those phase workers. Do not privatize in-file types under the concurrent sibling phases.

[2026-10-09T23:49:49Z · sase-1j6.5--1] Post-close fix, same turn: full check exposed 4 symvision private-import findings caused by this phase new files. Fixed by making the shared helpers public per symvision guidance: pending_handoff and pending_question in auto_restart/inputs.py, project_for_done in auto_restart/history.py, code_swap_lock_path in dev_update/code_swap_lock.py, with healer.py and quiescence.py imports updated. Verified: symvision private-import errors 0, focused suites 66 plus 64 passed, ruff check plus format and mypy clean.

## Dependencies

- **Depends on:** [sase-1j6.4](sase-1j6.4.md) ✓ · ⧖ 2026-10-09
- **Blocks:** [sase-1j6.6](sase-1j6.6.md) ◐ · ⧖ 2026-10-09
- **Blocks:** [sase-1j6.7](sase-1j6.7.md) ✓ · ⧖ 2026-10-09
- **Blocks:** [sase-1j6.8](sase-1j6.8.md) ◐ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1j6.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1j6.5.md) | [sase-1j6.5](sase-1j6.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e9f73fb`](https://github.com/sase-org/sase/commit/e9f73fb19a65cd261c082e6a38c223bd73ab9762) | feat(auto-restart): healer, at-most-once ledger, and auto-restart CLI | [sase-1j6.5](sase-1j6.5.md) | 2026-10-09 19:51:33 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1j6.5--1][1] | Declaration recovery: check bead status for bead_action | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1j6.5.md

<!-- sase:referenced-by:end -->
