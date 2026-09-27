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

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/1aq_receipts_matched_live_proof.md

<!-- sase:links:end -->

## Description

Apollo and Athena run the same sase and sase-core build, one that contains the exact_ops_receipts contract. From Athena, a live exact stop and retry against Apollo settle certainly, a fresh dispatch can be stopped before the owner snapshot rebuilds, and a killed row keeps its retry context.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1aq.10.7.5.7.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1aq.10.7.5.7.land/README.md) | [sase-1aq.10.7.5.7](sase-1aq.10.7.5.7.md) | 0 |
