# Bead: sase-tw.7 — Derive at creation, on sidecar commit, and in the hourly sweep

[Bead Pages](../README.md) / [sase-tw](README.md) / sase-tw.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-tj.land.w3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-tj.land.w3.md) · **Assignee:** `sase-tw.7` · **Size:** medium
**Created:** 2026-08-25 15:34:40 EDT · **Closed:** 2026-08-25 19:34:58 EDT
**Plan:** [202608/artifact\_link\_durability\_and\_derivation.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_link_durability_and_derivation.md)

## Description

derivation-hooks: call the derivation module from `sase plan propose` and `sase artifact create`, from the sidecar commit path for artifacts that land another way, and from a new `sase_chop_artifact_link_backfill` chop in the hourly housekeeping bucket that runs the retroactive sweep.

## Notes

[2026-08-25T23:34:58Z · sase-tw.7] Auto-closed by `sase stitch create` after create_commit landed 960694738 ("feat(artifact-links): derive links from commits and backfill existing artifacts"). No verification is implied by this note. Reopen with `sase bead open sase-tw.7`, or pass `-B|--do-not-close-bead` on mid-flight commits.

## Dependencies

- **Depends on:** [sase-tw.2](sase-tw.2.md) ✓ · ⧖ 2026-08-25
- **Depends on:** [sase-tw.4](sase-tw.4.md) ✓ · ⧖ 2026-08-25
- **Depends on:** [sase-tw.6](sase-tw.6.md) ✓ · ⧖ 2026-08-25
- **Blocks:** [sase-tw.8](sase-tw.8.md) ◐ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tw.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.7/README.md) | [sase-tw.7](sase-tw.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9606947`](https://github.com/sase-org/sase/commit/960694738960861c480229edcbd7087767d6f827) | feat(artifact-links): derive links from commits and backfill existing artifacts | [sase-tw.7](sase-tw.7.md) | 2026-08-25 19:33:07 EDT |
