# Bead: sase-5j.3 — Phase 3 - GitHub provider opt-in (sase-github, plus small sase-side integration)

[Bead Pages](../README.md) / [sase-5j](README.md) / sase-5j.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5j.3`
**Created:** 2026-07-08 03:25:18 UTC
**Plan:** [202607/sdd\_separate\_repo.md](https://github.com/sase-org/sase--plans/blob/main/202607/sdd_separate_repo.md)

## Notes

COMMIT: 67dbfd70e

[2026-07-27T21:38:58Z · sase-a1.land] [2026-07-08T04:32:02Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Implemented GitHub SDD separate_repo opt-in in sase-github, wired gh_setup materialization, added sdd.repo.name schema/default in sase, and covered parser/materialization/setup behavior with tests. Verification: sase-github just check passed; sase just test passed; sase just check is blocked by existing init skills drift outside this repo.

## Dependencies

- **Depends on:** [sase-5j.2](sase-5j.2.md) ✓
- **Blocks:** [sase-5j.4](sase-5j.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-5j.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-5j.3/README.md) | [sase-5j.3](sase-5j.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`5568489`](https://github.com/sase-org/sase/commit/556848902da6b636b3c46e55cc6377852350f894) | feat: add SDD companion repo config (sase-5j.3) | [sase-5j.3](sase-5j.3.md) | 2026-07-08 04:37:11 |
