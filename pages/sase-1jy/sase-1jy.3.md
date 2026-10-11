# Bead: sase-1jy.3 — Shared scope keys and scoped row selection for named waits

[Bead Pages](../README.md) / [sase-1jy](README.md) / sase-1jy.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zo](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zo.md) · **Assignee:** `sase-1jy.3` · **Size:** medium
**Created:** 2026-10-11 11:18:33 EDT · **Closed:** 2026-10-11 13:22:28 EDT
**Plan:** [202610/wait\_checks\_scoped\_view.md](https://github.com/sase-org/sase--plans/blob/main/202610/wait_checks_scoped_view.md)

## Description

scope-keys: factor the identity keys _add_prepared files a row under into one helper, add marker scope keys (None for unscopable shapes) and row selection, and prove scoped and full views give identical decisions for named waits.

## Notes

[2026-10-11T17:22:08Z · sase-1jy.3] Query audit: scoped named waits reach only the dependency-name entities in resolve_wait_release, confirmation, and terminal_blockers; latest_member_finished_at consumes only dependency_member_dirs output. The planner-alias membership path previously scanned all artifacts by timestamp, so planner candidates now retain their source artifact directory. Tribe, hood, identity, fork-source, and epic-follow shapes remain unscopable. Scoped/full parity covers retries, plan/code sessions, clan generations, workflows, submitted planner aliases, queued rows, failed and unknown outcomes, cross-project names, and shared sessions; focused pytest passed (24 tests).

[2026-10-11T17:22:28Z · sase-1jy.3] Focused scoped/full parity and planner alias tests passed (24 tests); query audit recorded; no epic symbols remain.

## Dependencies

- **Depends on:** [sase-1jy.2](sase-1jy.2.md) ✓ · ⧖ 2026-10-11
- **Blocks:** [sase-1jy.4](sase-1jy.4.md) ✓ · ⧖ 2026-10-11
- **Blocks:** [sase-1jy.5](sase-1jy.5.md) ✓ · ⧖ 2026-10-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jy.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jy.3.md) | [sase-1jy.3](sase-1jy.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fe77e92`](https://github.com/sase-org/sase/commit/fe77e92d564bbc7a71ef7406bcca913cc6fc2212) | feat(wait): add scoped row selection for named waits | [sase-1jy.3](sase-1jy.3.md) | 2026-10-11 16:28:20 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jy.3--4][1] | Compare first pytest failure with this phase scope | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jy.3.md

<!-- sase:referenced-by:end -->
