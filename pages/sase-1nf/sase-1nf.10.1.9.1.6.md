# Bead: sase-1nf.10.1.9.1.6 — Fix the confirmed publication blockers and finish recovery acceptance

[Bead Pages](../README.md) / [sase-1nf.10.1.9.1](sase-1nf.10.1.9.1.md) / sase-1nf.10.1.9.1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nf.10.1.9.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.10.1.9.1.land.md) · **Assignee:** `sase-1nf.10.1.9.1.6.land`
**Created:** 2026-10-21 10:45:30 EDT · **Closed:** 2026-10-22 08:46:04 EDT
**Plan:** [202610/publication\_blockers\_acceptance.md](https://github.com/sase-org/sase--plans/blob/main/202610/publication_blockers_acceptance.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/publication_blockers_acceptance.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 3 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/publication_blockers_acceptance.md

<!-- sase:links:end -->

## Description

Remove the three confirmed publication blockers, install the fixes on both hosts, recover Apollo's unpublished bob-cli content, and prove all five recovery checks with bounded canaries and a natural automatic publication.

## Notes

[2026-10-22T12:46:04Z · sase-1nf.10.1.9.1.6.land] LANDING (sase-1nf.10.1.9.1.6.land, 2026-10-22). All 5 phases are closed, and their notes and source were reviewed.

VERIFIED CODE
- sase 54779b62f5 (drain-bound):
  - The reserved agent-session set is built once per historical_associations build and passed to sase_agent_ref_for_name.
  - load_validated_publication digests reused base snapshots from on-disk bytes; fresh overrides stay canonical.
  - _cached_previous_snapshot falls back to on-disk bytes.
  - Regressions cover the non-canonical foreign snapshot, a tampered cache that still fails, and a single reserved-set build where a registry change is still observed.
- sase 16d63cf9b0 plus sase-core 1503d604 (replay-policy):
  - GitBytesRunner/run_git_bytes replaces the text-mode _git_optional_bytes; no .stdout.encode() blob reads remain.
  - Optional serde-default base_hex adds the rules previous==base keeps current and current==base keeps previous, then falls back to identical/empty/prefix rules, then refuses.
  - The merge base is wired through report (refused_same_run_divergences) and apply (payloads plus state/metadata fields).
  - Rust and Python tests added. The pin moved to 1503d604, which is sase-core origin/master.
  - The docs runbook was updated.
- The DECISION canary_budget=fresh was honored: athena spent limit-1 plus a batch of 5; each Apollo project spent its limit-1 call; no batch was allowed after a failed limit-1.

PRODUCTION EVIDENCE
- Both hosts run SASE ba7ab4e96 and core 1503d604.
- The Apollo bob-cli replay published 3733feaf2. A repeat apply returned already_complete.
- Remote 650c73595 validates 3 manifests and 804 snapshots, with the unique content and all 6,426 upstream-only paths intact.
- Post-fix drains: inventory 23–27.5 s versus 106–148 s before the fix; no digest mismatch on any multi-hood drain; first successful pull --rebase past 2abeff3f9.

ACCEPTANCE (research:202610/publication_recovery_acceptance.md, attached to sase-1nf.10.1.9)
- Checks 2, 3, and 4 PASS.
- Check 5 PARTIAL: the request-bound primary_revision field is missing.
- Check 1 MISSING: no named stopped request has published.
- These gaps are not caused by this epic. All three code blockers are verified fixed, and the remaining blockers are environmental or pre-existing:
  - The "Apollo credential loss" was re-diagnosed at landing: Athena's forwarded ssh-agent offers the bobs-org/bob deploy key first, and Apollo lacks the id_sase_service IdentitiesOnly match. With ForwardAgent=no, Apollo authenticates as bbugyi200 and passes the push auth check. Commits a090a3a2c and f2d32a476b are stranded, ahead 1.
  - Stale-revision dud rows.
  - The known prompt-archive obligation.
- The budget is spent, so no further canaries were run.

INTEGRATION
- Commits since the epic started are ba7ab4e96b (release workflow) and 85f6e43b3c (docs refresh; hood-sync.md now links the updated stale-replay runbook). Neither conflicts with or duplicates this epic.
- sase-core has nothing after 1503d604.
- No code changes were needed.

FOLLOW-UP TRIAGE
- .6.1#1 and .6.2#1 (TUI import budget): +1 on sase-1ic, a duplicate.
- .6.3#1 (stale refusal metadata): root cause pinned. ensure_backup returns early on a verified backup without refreshing progress['refused'], and resume reads the stored list. Recorded as a DISCOVERED ISSUE on active epic sase-1nf.10.1, whose phase .8 built the helper; no task created.
- .6.4#1 (Apollo write access): re-diagnosed as an SSH identity problem and filed as sase-1ni (bug, small, ready), related to sase-167.
- .6.4#2 (apollo/sase manifest_mismatch retry): not a defect; it is bounded-drain work owned by sase-1nf.11. A handoff note with preconditions was recorded there; no task created.
- .6.4#3 (stale-revision dud rows): filed as sase-1nj (bug, large, ready), related to sase-1c0 and sase-1nf.11.
- Not filed: the check-5 primary_revision correlation gap. No phase proposed it, and it is an acceptance-evidence gap rather than a confirmed defect; it is recorded on parent sase-1nf.10.1.9.1.

epic-symbols: none.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.10.1.9.1.6.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.9.1.6.land/README.md) | [sase-1nf.10.1.9.1.6](sase-1nf.10.1.9.1.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@8ecd7e0`](https://github.com/sase-org/sase--plans/commit/8ecd7e09ff7c476a7a8126db2d7aa524dc6e0e43) | chore(plans): mark publication blockers acceptance plan done | [sase-1nf.10.1.9.1.6](sase-1nf.10.1.9.1.6.md) | 2026-10-22 08:48:02 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nf.10.1.9.1.6.1][1] | parent epic context for drain-bound | 1 |
| read-by | [agent:sase-1nf.10.1.9.1.6.5][2] | Review the parent epic, phase evidence, and remaining acceptance scope before doing acceptance work | 1 |
| read-by | [agent:sase-1nf.10.1.9.1.6.land][3] | Need the epic scope, children, and linked plan file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.9.1.6.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.9.1.6.5/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.9.1.6.land/README.md

<!-- sase:referenced-by:end -->
