# Bead: sase-vs.6 — Wait field in the ACE approval modal

[Bead Pages](../README.md) / [sase-vs](README.md) / sase-vs.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ga](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ga.md) · **Assignee:** `sase-vs.6` · **Size:** medium
**Created:** 2026-08-30 07:22:02 EDT · **Closed:** 2026-08-30 09:45:31 EDT
**Plan:** [202608/approval\_wait\_argument.md](https://github.com/sase-org/sase--plans/blob/main/202608/approval_wait_argument.md)

## Description

ace_approval_wait: add an editable wait row to the ACE custom-approval modal and forward the spec through both the neutral and legacy ACE approval paths.

## Notes

[2026-08-30T13:45:31Z · sase-vs.6] Implemented ACE custom approval wait row using a plain validated text editor; forwarded canonical wait specs through neutral approval execution, legacy plan responses, and legacy epic launch; verified with focused tests, just symvision, just check, and no epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-vs.4](sase-vs.4.md) ✓ · ⧖ 2026-08-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-vs.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vs.6/README.md) | [sase-vs.6](sase-vs.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`18fa499`](https://github.com/sase-org/sase/commit/18fa499a3af9c4d941123f51aa0827c6ab0a68d6) | feat(ace): add approval wait editor | [sase-vs.6](sase-vs.6.md) | 2026-08-30 09:46:42 EDT |
