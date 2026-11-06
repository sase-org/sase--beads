# Bead: sase-1qz.7 — Start-over and leave recovery (Restart, Edit backend, Dismiss)

[Bead Pages](../README.md) / [sase-1qz](README.md) / sase-1qz.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.research.33.linker.w0` · **Assignee:** `sase-1qz.7` · **Size:** medium
**Created:** 2026-11-02 17:42:16 EST · **Closed:** 2026-11-06 15:11:07 EST
**Plan:** [202611/agent\_hijack.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack.md)

## Description

recover_release: add snapshot-verified restart and dismiss resolutions, restart with a replacement prompt for Edit, `sase agent restart` and `sase agent kill` awareness of HIJACKED targets, and preview availability reasons for those actions.

## Notes

[2026-11-06T20:04:12Z · sase-1qz.7] PROPOSED FOLLOW-UP: tests/test_pytest_isolation_guards.py::test_no_undo_on_shared_monkeypatch_fixture and ::test_session_sandbox_seal_is_not_first_test fail on this tree from committed tests/ace/tui/test_log_panel_keymap.py:331 calling monkeypatch.undo(); the offender is at HEAD and untouched by this phase (already tracked via sase-1rg.2 notes and the sase-1ra.5 false-red batch)

[2026-11-06T20:11:07Z · sase-1qz.7] Closed by explicit `sase stitch create -B close` after create_commit landed f4ca45edf8 ("feat(hijack-recovery): add snapshot-verified restart and dismiss resolutions"). The commit author requested bead completion after verifying the bead scope. Reopen with `sase bead open sase-1qz.7` if more work remains.

## Dependencies

- **Depends on:** [sase-1qz.6](sase-1qz.6.md) ✓ · ⧖ 2026-11-02
- **Blocks:** [sase-1qz.9](sase-1qz.9.md) ✓ · ⧖ 2026-11-02
- **Blocks:** [sase-1ra.11.1.1](../sase-1ra/sase-1ra.11.1.1.md) ◐ · ⧖ 2026-11-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1qz.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.7/README.md) | [sase-1qz.7](sase-1qz.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f4ca45e`](https://github.com/sase-org/sase/commit/f4ca45edf82f5561bfeb5fecc8aa410c6df5c82b) | feat(hijack-recovery): add snapshot-verified restart and dismiss resolutions | [sase-1qz.7](sase-1qz.7.md) | 2026-11-06 15:09:55 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:18n][1] | Check in-progress hijack phase notes for deviations from the plan, for a user-facing report | 1 |
| read-by | [agent:research.3a.final][2] | Check active epic phase scopes for conflict screening of task bead recommendations | 1 |
| read-by | [agent:sase-1qz.7][3] | Check closure status after host landing window | 7 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.18n/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.final/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.7/README.md

<!-- sase:referenced-by:end -->
