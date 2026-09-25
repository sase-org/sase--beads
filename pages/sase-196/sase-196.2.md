# Bead: sase-196.2 — Report unpublished and dangling archive objects

[Bead Pages](../README.md) / [sase-196](README.md) / sase-196.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ry.f0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ry.f0.md) · **Assignee:** `sase-196.2` · **Size:** medium
**Created:** 2026-09-25 09:05:35 EDT · **Closed:** 2026-09-25 11:02:58 EDT
**Plan:** [202609/agents\_sidecar\_orphan\_objects.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_sidecar_orphan_objects.md)

## Description

archive-validation: teach `sase agent prompts validate` about files/objects links (missing, untracked, digest, orphan) and add a bounded `sase doctor` check that reports dirt in agents sidecar clones.

## Notes

[2026-09-25T15:01:51Z · sase-196.2] PROPOSED FOLLOW-UP: Publish or restore the four pre-existing prompt-archive objects identified by the sase-196 design (three untracked and one missing) through an authorized agents-sidecar workflow; the new validator correctly reports them as errors until then.

[2026-09-25T15:02:58Z · sase-196.2] Implemented content-addressed prompt-object validation and the bounded agents-sidecar dirt doctor check; just fix and 21 focused tests passed. Recorded tool run 651f1eece3649c1fd1372a6ecc52659a reached the intended validator and failed only on the known protected live-sidecar state (three untracked linked objects and one missing object), recorded as a proposed follow-up.

## Dependencies

- **Depends on:** [sase-196.1](sase-196.1.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-196.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-196.2/README.md) | [sase-196.2](sase-196.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4214ccc`](https://github.com/sase-org/sase/commit/4214ccc650b63c2efb7839af46ddb966d788ca1d) | feat(agents): validate archive objects | [sase-196.2](sase-196.2.md) | 2026-09-25 11:04:42 EDT |
