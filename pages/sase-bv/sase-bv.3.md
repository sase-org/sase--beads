# Bead: sase-bv.3 — Record the creator on every bead creation path

[Bead Pages](../README.md) / [sase-bv](README.md) / sase-bv.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-bv.3` · **Size:** medium
**Created:** 2026-07-31 13:12:40 UTC · **Closed:** 2026-07-31 14:40:32 UTC
**Plan:** [202607/bead\_created\_by\_attribution.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_created_by_attribution.md)

## Description

wiring: stamp `proposed_by` into plan frontmatter at `sase plan propose`, and pass a resolved creator from `sase bead create` and from deterministic epic-from-plan creation so epics, phases, and tasks are attributed correctly.

## Notes

[2026-07-31T14:40:32Z · sase-bv.3] Implemented proposal stamping and creator resolution across direct bead creation and deterministic epic creation; verified phase inheritance and proposer/agent/owner fallbacks with 52 focused tests, exact Symvision lint, and full just check.

[2026-07-31T14:41:12Z · sase-bv.3] Verified 52 focused attribution tests, just _lint-symvision, and full just check all pass.

## Dependencies

- **Depends on:** [sase-bv.2](sase-bv.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-bv.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-bv.3/README.md) | [sase-bv.3](sase-bv.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`b2b1e73`](https://github.com/sase-org/sase/commit/b2b1e73d9210383f11b4e61a5ef08fd8bc3a63fc) | feat(beads): attribute creation to the responsible agent | [sase-bv.3](sase-bv.3.md) | 2026-07-31 14:41:56 |
