# Bead: sase-il.7.2 — Adopt the completed contract in sase

[Bead Pages](../README.md) / [sase-il.7](sase-il.7.md) / sase-il.7.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-il.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-il.land/README.md) · **Assignee:** `sase-il.7.2` · **Size:** medium
**Created:** 2026-08-10 10:55:08 EDT · **Closed:** 2026-08-10 12:54:27 EDT
**Plan:** [202608/finish\_tale\_size\_semantics.md](https://github.com/sase-org/sase--plans/blob/main/202608/finish_tale_size_semantics.md)

## Description

sase-adopt-contract: raise the sase-core-rs floor to the new release, delete the Python launch-compatibility shim now that core owns it, migrate the 21 committed tale plans the sase-il backfill over-sized to `large`, and cover the completed contract with tests.

## Notes

[2026-08-10T16:53:28Z · sase-il.7.2] PROPOSED FOLLOW-UP: investigate full-suite-only agent group revival flakes — just check full-lane runs intermittently failed test_saved_group_revive_restores_deleted_artifacts_and_tribe_real_loader and test_mark_save_preview_and_revive_saved_agent_group, while direct reruns passed.

[2026-08-10T16:54:27Z · sase-il.7.2] Verified sase-core-rs floor/lock raised to 0.24.0, Python tale launch shim removed, launch/authoring tests cover missing and over-sized tale normalization, contract manifest refreshed, and plans sidecar committed a91c3138 changing the 21 over-sized 202608 tale plans to medium. Verified just install; targeted pytest for plan validation/gates/follow-up routing/plan display passed (88 passed); contract manifest tests passed (3 passed); refreshed contract set passed (429 passed); sase plan validate --explain --json reports tale-size-invalid with xsmall | small | medium schema; just validate-committed-plans passed (3572 files, 0 errors, 0 warnings); just check non-test gates passed through committed plans. just check full pytest lane still hit an unrelated full-suite-only agent group revival flake that passed direct reruns, and a PROPOSED FOLLOW-UP note was recorded.

[2026-08-10T16:56:24Z · sase-il.7.2] Verified targeted pytest, contract manifest tests, refreshed contract set, CLI plan validate JSON, committed-plan validation, and just check non-test gates; full-lane just check still shows unrelated revival E2E flake that passes direct reruns and has a PROPOSED FOLLOW-UP note.

## Dependencies

- **Depends on:** [sase-il.7.1](sase-il.7.1.md) ✓ · ⧖ 2026-08-10
- **Blocks:** [sase-il.7.3](sase-il.7.3.md) ◐ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-il.7.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-il.7.2/README.md) | [sase-il.7.2](sase-il.7.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@a91c313`](https://github.com/sase-org/sase--plans/commit/a91c3138f39ab772c092fac5029c010d15aee942) | chore(plans): correct over-sized tale backfill | [sase-il.7.2](sase-il.7.2.md) | 2026-08-10 12:37:18 EDT |
| sase | [`dcb243b`](https://github.com/sase-org/sase/commit/dcb243b753b1cbc61d5a4b136063792e888d87ff) | feat!: adopt core tale size contract | [sase-il.7.2](sase-il.7.2.md) | 2026-08-10 12:57:22 EDT |
