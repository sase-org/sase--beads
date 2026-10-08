# Bead: sase-1id.2 — Live agent meta is the only %auto source

[Bead Pages](../README.md) / [sase-1id](README.md) / sase-1id.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0yg](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0yg.md) · **Assignee:** `sase-1id.2` · **Size:** medium
**Created:** 2026-10-08 13:39:30 EDT · **Closed:** 2026-10-08 14:37:15 EDT
**Plan:** [202610/auto\_p0\_safety\_tales.md](https://github.com/sase-org/sase--plans/blob/main/202610/auto_p0_safety_tales.md)

## Description

live_meta: make the plan and question auto readers consult only the live agent_meta.json, never the SASE_AGENT_AUTO_* env snapshot, and stop runner write-backs of stale in-memory meta from undoing an A toggle. Update the env rows in docs/configuration.md. Close task bead sase-15s when done.

## Notes

[2026-10-08T18:36:57Z · sase-1id.2--1] PROPOSED FOLLOW-UP: just check (tool run d415d1459f61dafffb62b448ff225207) reports no_new_failures with 63 KNOWN and 0 flaky; sampled KNOWN tests test_default_list_includes_claimed_with_shared_glyph and test_checked_in_snapshot_has_no_drift fail identically on the clean base tree (verified via git stash), so the red lane is pre-existing and unrelated to the live_meta files

[2026-10-08T18:37:15Z · sase-1id.2--1] live_meta done: plan/question auto readers consult only live agent_meta.json (env snapshot ignored), runner write-backs overlay live auto keys, post-wait re-exec reconciles prompt from live meta, docs/configuration.md env rows updated. Verified: 16 passed in tests/test_plan_auto_live_meta.py, 17 passed neighbors, epic-symbols clean, check run d415d1459f61dafffb62b448ff225207 triaged no_new_failures with 63 KNOWN pre-existing (2 sampled failures reproduce identically on clean base tree; recorded as PROPOSED FOLLOW-UP).

## Dependencies

- **Blocks:** [sase-1id.3](sase-1id.3.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1id.6](sase-1id.6.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1id.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1id.2.md) | [sase-1id.2](sase-1id.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c70ee9a`](https://github.com/sase-org/sase/commit/c70ee9af3d4812a23777c11ef77b2ac75dea4fa9) | feat(auto): live agent meta is the only %auto source | [sase-1id.2](sase-1id.2.md) | 2026-10-08 14:38:50 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1id.2--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1id.2.md

<!-- sase:referenced-by:end -->
