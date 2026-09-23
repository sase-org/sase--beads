# Bead: sase-16n.11.7.3 — sase follow-up prefix regression, non-blocking history filter, test isolation and gaps, docs nits

[Bead Pages](../README.md) / [sase-16n.11.7](sase-16n.11.7.md) / sase-16n.11.7.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-16n.11.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-16n.11.land.md) · **Assignee:** `sase-16n.11.7.3` · **Size:** medium
**Created:** 2026-09-23 14:10:55 EDT · **Closed:** 2026-09-23 14:58:52 EDT
**Plan:** [202609/project\_tags\_landing\_gaps\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202609/project_tags_landing_gaps_finish.md)

## Description

backend-regressions: ratchet the sase-core pin; frozen_intent_vcs_prefix counts only a real +tag token; the prompt-history project filter never builds the catalog on the event loop; the tag catalog cache resets between tests; add the missing assertions for completion order, fresh-process CLI output, alt fan-out and the MRU label; skip catalog loads for raw/json prompt show; add occupant_kind to doctor JSON; fix the docs nits.

## Notes

[2026-09-23T18:58:36Z · sase-16n.11.7.3] PROPOSED FOLLOW-UP: just check symvision gate fails on stale --epic-symbol sase-16y(MemberJumpSection) (bead closed) — fails identically on clean tree, needs Justfile cleanup

[2026-09-23T18:58:52Z · sase-16n.11.7.3] backend-regressions done: pin fb1ca29; prefix tag-token fix; peek-only history filter; conftest cache reset; completion/CLI/alt/MRU assertions; raw-json skip; occupant_kind; docs nits. 236+232 focused tests pass; ruff+mypy+fmt clean; symvision fails pre-existing on stale sase-16y symbol (clean tree too)

## Dependencies

- **Depends on:** [sase-16n.11.7.1](sase-16n.11.7.1.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-16n.11.7.4](sase-16n.11.7.4.md) ◐ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16n.11.7.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.11.7.3/README.md) | [sase-16n.11.7.3](sase-16n.11.7.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1230ed8`](https://github.com/sase-org/sase/commit/1230ed8da198e5952221819caf5e7962f9dec37c) | feat(scope): describe the completed work | [sase-16n.11.7.3](sase-16n.11.7.3.md) | 2026-09-23 15:00:32 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16y.land][1] | child scope for red-test triage | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16y.land/README.md

<!-- sase:referenced-by:end -->
