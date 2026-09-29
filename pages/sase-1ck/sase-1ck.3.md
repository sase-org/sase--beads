# Bead: sase-1ck.3 — Attachment wire, reducer, mutation APIs, and policy (sase-core)

[Bead Pages](../README.md) / [sase-1ck](README.md) / sase-1ck.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tv](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tv.md) · **Assignee:** `sase-1ck.3` · **Size:** medium
**Created:** 2026-09-29 08:13:39 EDT · **Closed:** 2026-09-29 11:33:03 EDT
**Plan:** [202609/bead\_note\_attachments.md](https://github.com/sase-org/sase--plans/blob/main/202609/bead_note_attachments.md)

## Description

core_wire: add the optional attachments manifest on note events and BeadNoteWire, token/manifest validation, reducer and mutation API support (append, edit, close, +1), roster and reference queries, placement/fetch/sensitive-path policy, and tombstone wire, with bindings and the pin bump.

## Notes

[2026-09-29T15:32:41Z · sase-1ck.3] PROPOSED FOLLOW-UP: fix test_cli_work_cleanup_confirm fake launch_agent_from_cwd lambda for the new origin kwarg (7 tests fail; agent-session refactor skew, unrelated to attachments) -r recording pre-existing check failure found during core_wire verification

[2026-09-29T15:33:03Z · sase-1ck.3] core_wire done: attachment manifest on note events/BeadNoteWire with token/manifest validation, reducer (append sets, edit Some replaces incl Some([]) detach, None keeps), mutation APIs (append/edit/close/+1 kwargs), roster+reference queries, placement/auto-fetch/sensitive-path policy, tombstone wire, 7 bindings. Verified: sase-core sase tool run check green (fmt, clippy, 3942 lib + integration + 236 py-binding tests), legacy events byte-identical, forward-compat fixture passes, pin bumped to pushed 43f744b with check_sase_core_rs_bindings green, sase bead suites 1002 passed on new core. One pre-existing unrelated failure noted as follow-up. sase-core-revision.txt left uncommitted for the land agent.

## Dependencies

- **Depends on:** [sase-1ck.1](sase-1ck.1.md) ✓ · ⧖ 2026-09-29
- **Blocks:** [sase-1ck.4](sase-1ck.4.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ck.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ck.3/README.md) | [sase-1ck.3](sase-1ck.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@43f744b`](https://github.com/sase-org/sase-core/commit/43f744be33e516aad80059b33e64056c7d156741) | feat(note-attachment): add attachment wire, reducer, mutation APIs, and policy | [sase-1ck.3](sase-1ck.3.md) | 2026-09-29 10:59:26 EDT |
| sase | [`b63e793`](https://github.com/sase-org/sase/commit/b63e79319966538fd8bb497ec08ac75cc7ba8df3) | chore(core-pin): ratchet sase-core-revision.txt to 43f744b for bead note attachments core\_wire | [sase-1ck.3](sase-1ck.3.md) | 2026-09-29 11:35:25 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.n.cld][1] | Check progress of attachment wire and shared-store phases to judge whether a visibility field can be added early | 1 |
| read-by | [agent:sase-1ck.3][2] | check phase status | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.n.cld/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ck.3/README.md

<!-- sase:referenced-by:end -->
