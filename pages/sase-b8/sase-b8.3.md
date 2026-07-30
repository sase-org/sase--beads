# Bead: sase-b8.3 — Lane-anchored sidecar publication requests

[Bead Pages](../README.md) / [sase-b8](README.md) / sase-b8.3

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b8.3` · **Size:** small
**Created:** 2026-07-30 14:32:41 UTC · **Closed:** 2026-07-30 15:37:19 UTC
**Plan:** [202607/family\_scoped\_agent\_provenance.md](https://github.com/sase-org/sase--plans/blob/main/202607/family_scoped_agent_provenance.md)

## Description

publish: record the lane as the publication identity in the outbox and make hood publication accept a lane name deliberately rather than by accidental fallback.

## Notes

[2026-07-30T15:37:19Z · sase-b8.3] publish_committed_agent_hood() now derives the lane via lane_ref_for_agent() and records lane local/global names on the outbox item (local_hood unchanged, so publication scope is identical); publish_agent_hood() accepts a lane deliberately via lane_ref_for_lane_name(), documenting that a family container never matches a run and preserving the load-bearing 'hood ... has no publishable runs' message that _prepare_publications() matches on; chat-catalog _publication_status() also probes lane projections so member-anchored chats find lane-anchored requests. Dropped 3 now-used symvision epic-symbol whitelist entries. Verified: 27 targeted tests pass (test_publication.py, test_commit_publication.py, test_chat_catalog_publication.py) incl. new coverage for member->family-lane enqueue, unchanged drained hood payload, byte-identical solo publication, family-container acceptance, and member-chat->lane-request lookup. Full 'just check' lint stages all green (ruff/mypy/symvision/toobig/keep-sorted/changelog/pyscripts). Full suite: 24267 passed, 3 pre-existing failures unrelated to this bead (stale sase_core_rs artifact-file query wire, 'expected 2, got 3', from the recent VCS-backed artifact capture commits); 'sase validate' plan-link errors are also pre-existing (clean plans sidecar tree, includes two plan files untouched here).

## Dependencies

- **Depends on:** [sase-b8.1](sase-b8.1.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b8.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b8.3/README.md) | [sase-b8.3](sase-b8.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`1cd59c3`](https://github.com/sase-org/sase/commit/1cd59c3b11e16835ab23dc030f8234e871bb194e) | feat(agents): anchor sidecar publication requests on the agent lane | [sase-b8.3](sase-b8.3.md) | 2026-07-30 15:40:37 |
