# Bead: sase-1d6.1 — Pass -B keep for revision-pinned sibling stitches

[Bead Pages](../README.md) / [sase-1d6](README.md) / sase-1d6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ua](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ua.md) · **Assignee:** `sase-1d6.1` · **Size:** small
**Created:** 2026-09-30 06:21:10 EDT · **Closed:** 2026-09-30 06:43:55 EDT
**Plan:** [202609/relaunch\_failed\_epics.md](https://github.com/sase-org/sase--plans/blob/main/202609/relaunch_failed_epics.md)

## Description

pinned-sibling-bead-action: stop commit_dispatch from dropping bead_action for revision-pinned siblings (downgrade to keep instead), fix the test that enshrined the bug, and prove keep passes the Rust bead-action policy.

## Notes

[2026-09-30T10:43:24Z · sase-1d6.1--1] PROPOSED FOLLOW-UP: just check lint (patch/stitch terminology) fails identically on clean base (14 defects in sase-core at_bearing_notes.jsonl fixture); fix belongs in unlanded sase-1ck land diff, do not fix here

[2026-09-30T10:43:55Z · sase-1d6.1--1] Pinned-sibling -B keep fix verified: 44 focused revision-pin tests pass (dispatch e2e asserts sibling keep/main close, sibling-only keep, no-bead None, downgrade matrix, resume downgrade, real Rust bead-action policy assertions); dispatch/resume/checkpoint-recovery all route through pinned_sibling_bead_action and fingerprint uses the passed value; just check fails only on pre-existing patch/stitch audit (14 sase-core fixture defects, reproduced identically on clean base via stash)

## Dependencies

- **Blocks:** [sase-1d6.3](sase-1d6.3.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d6.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d6.1.md) | [sase-1d6.1](sase-1d6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`63bde57`](https://github.com/sase-org/sase/commit/63bde575f07969a2a3e138516e52a91f0100a22c) | fix(finalizer): pass -B keep for revision-pinned sibling stitches | [sase-1d6.1](sase-1d6.1.md) | 2026-09-30 06:45:47 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1d6.1--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d6.1.md

<!-- sase:referenced-by:end -->
