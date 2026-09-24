# Bead: sase-17y.1 — Published bead creations keep their ID in duplicate-ID merges

[Bead Pages](../README.md) / [sase-17y](README.md) / sase-17y.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qv](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qv.md) · **Assignee:** `sase-17y.1` · **Size:** small
**Created:** 2026-09-24 11:57:12 EDT · **Closed:** 2026-09-24 12:16:42 EDT
**Plan:** [202609/bead\_relocation\_safe\_epic\_launch.md](https://github.com/sase-org/sase--plans/blob/main/202609/bead_relocation_safe_epic_launch.md)

## Description

core-winner: in the linked sase-core repo, make the merge-base or published upstream creation win a duplicate issue_created collision so only the local, unpublished bead is ever relocated; replace the orientation-independence tests and update the docs.

## Notes

[2026-09-24T16:16:19Z · sase-17y.1] PROPOSED FOLLOW-UP: sase_gateway post_spawn_publish_failure_reaps_barred_worker hit the same empty worker.pid parse flake as sase-15e under full check load — consider widening sase-15e or filing a sibling flake bead

[2026-09-24T16:16:42Z · sase-17y.1] core-winner done in sase-core: losing_creation picks merge-base, else upstream (theirs), else oldest; docs updated; tests rewritten (upstream keeps ID both timestamp orders, child .1 stays upstream, relocated stream is local). sase tool run check green on rerun (first run hit known empty-worker.pid load flake in unrelated sudo_runner test, passes alone). Uncommitted: merge.rs + tests/merge.rs.

## Dependencies

- **Blocks:** [sase-17y.4](sase-17y.4.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17y.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17y.1/README.md) | [sase-17y.1](sase-17y.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@6d0d0e6`](https://github.com/sase-org/sase-core/commit/6d0d0e6d5c0e783e68650f908e8c9eb01ceea7dc) | fix(bead): keep published bead ids stable when relocating duplicate creations | [sase-17y.1](sase-17y.1.md) | 2026-09-24 12:17:56 EDT |
