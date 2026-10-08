# Bead: sase-1h7.10 — Flip the default on and finish the docs

[Bead Pages](../README.md) / [sase-1h7](README.md) / sase-1h7.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3v.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3v.linker.w0.md) · **Assignee:** `sase-1h7.10` · **Size:** medium
**Created:** 2026-10-06 18:17:47 EDT · **Closed:** 2026-10-07 21:49:07 EDT
**Plan:** [202610/wait\_for\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202610/wait_for_epic.md)

## Description

flip: make `for_epic` default to true for user-authored agent targets (never `--plan` rows), have `sase bead work` emit `for_epic=false` for intra-epic sequencing waits, and prove with regression tests that epic phases and land agents still release. Update editor docs and user docs, and propose the memory follow-up.

## Notes

[2026-10-08T00:47:53Z · sase-1h7.10] PROPOSED FOLLOW-UP: Update the %wait row in sase/memory/macros.md with the flipped for_epic default (memory edits out of scope for this epic)

[2026-10-08T00:48:05Z · sase-1h7.10] PROPOSED FOLLOW-UP: Add sase agent wait --for-epic/--no-for-epic CLI (research Q2, out of scope for the flip)

[2026-10-08T00:48:14Z · sase-1h7.10] PROPOSED FOLLOW-UP: test_land_failure_entry_clears_when_waiter_releases fails identically on the clean base tree (ready.json gains unexpected released_by=wait_checks key); possibly related to task bead sase-1hc

[2026-10-08T00:48:23Z · sase-1h7.10] PROPOSED FOLLOW-UP: sase-core contract_covers_the_audited_directive_matrix fails on the clean sase-core checkout (wait keyword matrix never gained for_epic in the sase-1h7.3 mirror); needs a sase-core fix + pin move

[2026-10-08T01:48:13Z · sase-1h7.10--1] PROPOSED FOLLOW-UP: just check committed-plans stage panics identically on clean base (sase-core callout.rs:254 byte-index panic on em-dash in committed plan; validate_committed_plans PyO3 PanicException)

[2026-10-08T01:48:36Z · sase-1h7.10--1] PROPOSED FOLLOW-UP: just check lint-symvision KNOWN failure _list_bead_state_changes_silent dead private in src/sase/bead/_sync_git.py untouched by flip diff; triage witness d6b2e97555fba95917b24786df9ad735

[2026-10-08T01:49:07Z · sase-1h7.10--1] flip done: WAIT_FOR_EPIC_DEFAULT=true, bead work emits for_epic=false, docs updated; 78 flip-scoped pytest pass; just-check blockers reproduce on clean base (committed-plans sase-core em-dash panic, symvision KNOWN dead private) recorded as follow-ups

## Dependencies

- **Depends on:** [sase-1h7.2](sase-1h7.2.md) ✓ · ⧖ 2026-10-06
- **Depends on:** [sase-1h7.7](sase-1h7.7.md) ✓ · ⧖ 2026-10-06
- **Depends on:** [sase-1h7.8](sase-1h7.8.md) ✓ · ⧖ 2026-10-06
- **Depends on:** [sase-1h7.9](sase-1h7.9.md) ✓ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h7.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h7.10.md) | [sase-1h7.10](sase-1h7.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@9ea87c1`](https://github.com/sase-org/sase-core/commit/9ea87c1181128ff87d2a90e74b782ffa369e30c3) | feat(wait): support wait-for-epic flip in plan resolution and directive metadata | [sase-1h7.10](sase-1h7.10.md) | 2026-10-07 21:51:53 EDT |
