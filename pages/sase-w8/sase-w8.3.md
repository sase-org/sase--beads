# Bead: sase-w8.3 — In-flight deferred kill

[Bead Pages](../README.md) / [sase-w8](README.md) / sase-w8.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.kellys\_mbp.l](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.kellys_mbp.l.md) · **Assignee:** `sase-w8.3` · **Size:** medium
**Created:** 2026-09-03 17:02:20 EDT · **Closed:** 2026-09-04 07:44:40 EDT
**Plan:** [202609/kill\_and\_edit\_last\_launch.md](https://github.com/sase-org/sase--plans/blob/main/202609/kill_and_edit_last_launch.md)

## Description

deferred-kill-inflight: make `,X` on an in-flight launch restore the prompt immediately and kill the launched agents from the completion callback, holding replacement launches until the kill settles, with typed-admission scoping, failure handling, and race tests.

## Notes

[2026-09-04T11:42:58Z · sase-w8.3] PROPOSED FOLLOW-UP: abort launch bundle — add a sase-core operation that aborts a gated typed-admission launch bundle whose coordinator outlives the launch proc, so ,X can stop remaining %if/%proc units instead of only killing already-returned results and toasting that gated units continue in the background.

[2026-09-04T11:44:40Z · sase-w8.3] In-flight ,X restores the prompt immediately, marks KILL_PENDING, and kills/dismisses launch results from the completion callback with no confirmation; replacement submits park until the pending-kill hold or T4 cleanup barrier settles (180s warn-and-release). Verified: placeholder-id race kills once; double ,X is idempotent; failed launch discards intent and stashes once; N results yield N kills; timeout abandons auto-kill and replays the hold; admission_complete=false kills returned units and warns; WAITING/QUEUED take the dismiss path; handler does no disk/proc-store work. just check lint/mypy/symvision/toobig passed; 204 related tests passed. sase bead epic-symbols sase-w8.3 is empty.

## Dependencies

- **Depends on:** [sase-w8.2](sase-w8.2.md) ◐ · ⧖ 2026-09-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.kellys\_mbp.sase-w8.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.kellys_mbp.sase-w8.3/README.md) | [sase-w8.3](sase-w8.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`51c3fbc`](https://github.com/sase-org/sase/commit/51c3fbcd5f487af273c0ff74871a3e7f990122fa) | feat(ace): defer in-flight ,X kill until launch completion | [sase-w8.3](sase-w8.3.md) | 2026-09-04 08:04:59 EDT |
