# Bead: sase-ud.12 — Retire the --q asker suffix

[Bead Pages](../README.md) / [sase-ud](README.md) / sase-ud.12

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0eg](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0eg.md) · **Assignee:** `sase-ud.12` · **Size:** large
**Created:** 2026-08-26 14:02:58 EDT · **Closed:** 2026-08-27 08:30:32 EDT
**Plan:** [202608/gate\_shells.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_shells.md)

## Description

q-suffix-cleanup: delete PLAN_CHAIN_QUESTION_SUFFIX and the root/phase-question suffix taxonomy now that the gate shell owns the question, leaving the asker as an ordinary agent shell.

## Notes

[2026-08-27T12:30:32Z · sase-ud.12] Implemented retire_q_asker_suffix: removed the live q/question suffix taxonomy, kept canonical --q readable only as an ordinary historical custom token, moved question continuations onto ordinary --@ allocation with inherited roles, allowed q as a pipe --name token, and updated status/display/docs/tests. Verification: focused q/attach/status suites passed (141 passed), finalize-plan continuation checks passed (4 passed), exact stale-symbol scans were clean, and sase bead epic-symbols sase-ud.12 reported no entries. just check passed all formatting, lint, SASE validation, and committed-plan gates; its scoped pytest lane failed only the two unrelated Artifacts relation-panel tests recorded on active epic sase-ug.

## Dependencies

- **Depends on:** [sase-ud.11](sase-ud.11.md) ✓ · ⧖ 2026-08-26
- **Blocks:** [sase-ud.13](sase-ud.13.md) ✓ · ⧖ 2026-08-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ud.12](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ud.12.md) | [sase-ud.12](sase-ud.12.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`777e51e`](https://github.com/sase-org/sase/commit/777e51e734a6770e232e039ecfa159a199247295) | feat(agents): retire q asker suffix | [sase-ud.12](sase-ud.12.md) | 2026-08-27 08:31:56 EDT |
