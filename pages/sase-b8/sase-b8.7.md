# Bead: sase-b8.7 — Remaining SASE\_AGENT tag readers and back-compat

[Bead Pages](../README.md) / [sase-b8](README.md) / sase-b8.7

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b8.7` · **Size:** small
**Created:** 2026-07-30 14:32:55 UTC · **Closed:** 2026-07-30 15:47:58 UTC
**Plan:** [202607/family\_scoped\_agent\_provenance.md](https://github.com/sase-org/sase--plans/blob/main/202607/family_scoped_agent_provenance.md)

## Description

consumers: make image-attachment scanning, revert discovery, and the PR body footer lane-aware, and lock in that every reader still accepts legacy member-name tags.

## Notes

[2026-07-30T15:47:58Z · sase-b8.7] consumers phase: image-attachment scanning now matches the AGENT tag by lane (both sides projected through lane_ref_for_agent, with the literal exact/hood/member comparisons kept for legacy tags) with the identity snapshot resolved once per scan; build_pr_body's agent_meta name fallback projected through lane_name; revert discovery verified unchanged via new lane-tag and bulk dedupe-by-sha tests; vcs_log AGENT chip rendering pinned for a lane label; added tests/test_legacy_agent_tag_back_compat.py asserting the legacy SASE_AGENT=[bbugyi200.athena.pc--code][2] footer with #member-code anchor is still read correctly by footer parsing, attachment matching, revert matching, PR body rendering, and vcs-log chips. just install + just check pass except pre-existing failures unrelated to this phase (plan-links validation missing prompt links for 3 plans, and 2 artifact tests failing on a clean tree); full just test otherwise green.

## Dependencies

- **Depends on:** [sase-b8.2](sase-b8.2.md) ✓
- **Blocks:** [sase-b8.8](sase-b8.8.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b8.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b8.7/README.md) | [sase-b8.7](sase-b8.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`c407b3f`](https://github.com/sase-org/sase/commit/c407b3f39e21af5c906eac128752474087d601e8) | fix(agents): match SASE\_AGENT commit tags by lane | [sase-b8.7](sase-b8.7.md) | 2026-07-30 15:49:56 |
