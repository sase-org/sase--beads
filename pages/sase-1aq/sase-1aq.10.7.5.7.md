# Bead: sase-1aq.10.7.5.7 — Deploy the settled-receipt contract to both hosts and prove it live

[Bead Pages](../README.md) / [sase-1aq.10.7.5](sase-1aq.10.7.5.md) / sase-1aq.10.7.5.7

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1aq.10.7.5.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1aq.10.7.5.land.md) · **Assignee:** `sase-1aq.10.7.5.7.land`
**Created:** 2026-09-27 02:20:32 EDT
**Plan:** [202609/1aq\_receipts\_matched\_live\_proof.md](https://github.com/sase-org/sase--plans/blob/main/202609/1aq_receipts_matched_live_proof.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/1aq_receipts_matched_live_proof.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | file:explicit:b02a5484229526d3fdf7cb20 | attached via sase artifact create --bead |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/1aq_receipts_matched_live_proof.md

<!-- sase:links:end -->

## Description

Apollo and Athena run the same sase and sase-core build, one that contains the exact_ops_receipts contract. From Athena, a live exact stop and retry against Apollo settle certainly, a fresh dispatch can be stopped before the owner snapshot rebuilds, and a killed row keeps its retry context.

## Notes

[2026-09-27T09:02:54Z · sase-1aq.10.7.5.7.land] LAND AUDIT (interrupted, resumes after child plan): phases .1-.3 verified. .1: 48c3e0ddc5 matches plan (acceptance_window before request, timeout_seconds passed, TypeError fallback gone, fakes take retain_for_retry). .2/.3 notes + evidence file:explicit:1b071b131efc527dce16b7a1 reviewed. REMAINING EPIC WORK: .3 left a sase-core host_liveness.rs claims-cache fix UNCOMMITTED in Apollo's primary sase-core checkout and deployed only to Apollo's .so, so hosts no longer run the same build (violates epic goal) and Apollo's dirty sase-core checkout will block sase update. Diff backed up as file:explicit:b02a5484229526d3fdf7cb20; child epic plan lands it and reconverges both hosts. Integration: post-epic commits 90d6138504/06265d377e/8b877f99f9/faaf69757b are docs/TUI refactors; none duplicate or conflict. FOLLOW-UP ROUTING: .1#1 clean-base reds declined (already owned by sase-19i.7.3.3.3.3, sase-1ab, sase-1ay per plan); .2#2 index version-ahead crash -> new task sase-1az; .2#3 Athena artifact_links_aggregate stale -> +1 sase-ua (same defect); .3#1 land claims-cache fix -> epic work, child plan; .3#2 precondition refusals surface uncertain -> +1 sase-zz (same defect); .3#3 index row at launch-accept -> new task sase-1b0. epic-symbols: none.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1aq.10.7.5.7.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1aq.10.7.5.7.land.md) | [sase-1aq.10.7.5.7](sase-1aq.10.7.5.7.md) | 0 |
