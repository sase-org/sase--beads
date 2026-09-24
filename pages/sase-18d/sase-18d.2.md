# Bead: sase-18d.2 — Session removal tombstones honored at every roster publication

[Bead Pages](../README.md) / [sase-18d](README.md) / sase-18d.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ra](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ra.md) · **Assignee:** `sase-18d.2` · **Size:** medium
**Created:** 2026-09-24 16:28:31 EDT · **Closed:** 2026-09-24 16:47:20 EDT
**Plan:** [202609/x\_kill\_removal\_reliability.md](https://github.com/sase-org/sase--plans/blob/main/202609/x_kill_removal_reliability.md)

## Description

row-tombstones: record a session tombstone for every x-driven removal. Honor it in the load compute filter, the Tier-1 merge, apply time (removal-generation recheck), fleet reprojection, and refilter, ahead of runner_is_live. Keep the local roster copy in sync, fix the revive-modal repair that drops kill identities, and stop one failed signal from blocking the removal of every other row.

## Notes

[2026-09-24T20:46:56Z · sase-18d.2] PROPOSED FOLLOW-UP: Restore whole-repo mypy green — just check still reports 16 unrelated errors in agent-detail display/state, launch prompt inputs, and command-line input/screen modules after the row-tombstones changes type-check cleanly.

[2026-09-24T20:47:20Z · sase-18d.2] Implemented session removal tombstones across load, Tier-1 merge, apply, fleet/refilter, optimistic removal, and revive repair. Verified 72 focused affected tests plus 6 tombstone regressions and mypy for _kill_flow.py; just check passed fmt/keep-sorted/Ruff and now fails only on 16 pre-existing unrelated mypy errors recorded in this phase's follow-up note.

## Dependencies

- **Blocks:** [sase-18d.3](sase-18d.3.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-18d.4](sase-18d.4.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18d.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18d.2/README.md) | [sase-18d.2](sase-18d.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c88987e`](https://github.com/sase-org/sase/commit/c88987e7939f0e0e85ed2794bf3e0a5d16bdf037) | fix(ace): preserve session agent removals | [sase-18d.2](sase-18d.2.md) | 2026-09-24 16:48:59 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-18d.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18d.2/README.md

<!-- sase:referenced-by:end -->
