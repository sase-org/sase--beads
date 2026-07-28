# Bead: sase-ab.3 — Resolve the ACE Plans tab's plans root through the store

[Bead Pages](../README.md) / [sase-ab](README.md) / sase-ab.3

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ab.3` · **Size:** medium
**Created:** 2026-07-28 11:36:43 UTC · **Closed:** 2026-07-28 12:23:52 UTC
**Plan:** [202607/land\_beads\_sidecar\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202607/land_beads_sidecar_epic.md)

## Description

plansroot: resolve each project's plans root through the SDD store instead of walking up from the bead directory, so linked plan documents, cache keys, and the archive search all target the real plans clone.

## Notes

[2026-07-28T12:23:25Z · sase-ab.3] Implemented ACE Plans root resolution through resolve_sdd_kind_dir using each project's workspace metadata. Added schema-3 split-sidecar and schema-2 plans-embedded linked-document regressions plus unresolved-root fallback coverage. Verified focused ACE Plans suite: 21 passed; full suite: 22,899 passed, 7 skipped; formatting, Ruff, mypy, pyscripts, Symvision, toobig, and committed-plan validation passed. Live migrated-project smoke check resolved the plans clone, loaded the capped 50-row archive preview, and opened sase-ab's linked design without errors. Full just check remains blocked only by the unrelated plans-sidecar baseline of 229 historical prompt-link validation errors.

## Dependencies

- **Depends on:** [sase-ab.2](sase-ab.2.md) ✓
- **Blocks:** [sase-ab.5](sase-ab.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ab.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ab.3/README.md) | [sase-ab.3](sase-ab.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`ac12273`](https://github.com/sase-org/sase/commit/ac12273f547df64aee8b59ab951ada5e440750da) | fix(ace): resolve plans roots through SDD store (sase-ab.3) | [sase-ab.3](sase-ab.3.md) | 2026-07-28 12:25:44 |
