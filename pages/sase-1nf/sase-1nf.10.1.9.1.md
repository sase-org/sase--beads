# Bead: sase-1nf.10.1.9.1 — Finish Apollo recovery and prove bounded publication

[Bead Pages](../README.md) / [sase-1nf.10.1.9](sase-1nf.10.1.9.md) / sase-1nf.10.1.9.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nf.10.1.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.10.1.9.md) · **Assignee:** `sase-1nf.10.1.9.1.land`
**Created:** 2026-10-21 07:39:04 EDT
**Plan:** [202610/publication\_recovery\_proof.md](https://github.com/sase-org/sase--plans/blob/main/202610/publication_recovery_proof.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/publication_recovery_proof.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | file:explicit:07eac2cef30caada4c976c16 | landing-audit cProfile of scoped inventory build |
| related | file:explicit:1e757f4f4eadfca380da107c | attached via sase artifact create --bead |
| related | file:explicit:684de02c487788fab67ad837 | attached via sase artifact create --bead |
| related | file:explicit:b2ebf67eabeaef7b5e0a1265 | attached via sase artifact create --bead |
| related | file:explicit:f3576bf6104be8530cc534e2 | attached via sase artifact create --bead |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/publication_recovery_proof.md

<!-- sase:links:end -->

## Description

Complete the outstanding operational acceptance for sase-1nf.10.1.9 without bulk backlog draining or losing unpublished content.

## Notes

[2026-10-21T14:39:24Z · sase-1nf.10.1.9.1.land] LANDING AUDIT (land agent, 2026-10-21 ~14:40Z): all 5 phases closed but acceptance is NOT met. Checks 1 and 5 unproven; check 3 and 4 fixture-only; Apollo unique content still unpublished. Fresh read-only diagnosis found the blockers. (1) Regression from 8c6699f413 (sase-1nf.10.1.5): load_validated_publication digests cached base_snapshots after canonical re-serialization, so 40/98 legacy Apollo sase snapshots (first: 03) falsely fail 'snapshot digest mismatch' in every multi-hood drain; the raw bytes match the manifest. This blocked hood sase-1nf, so no epic worker auto-published (agents remote unchanged since b3da77e44a, 13:06Z). (2) Scoped inventory_build takes 106-148s on Athena, because get_reserved_agent_session_names rebuilds the full registry set on each of 8,689 sase_agent_ref_for_name calls (~229s of 268s under cProfile). (3) Apollo replay is still blocked by the CR text-mode read and the missing merge-base keep-local policy. Evidence: file:explicit:684de02c487788fab67ad837, file:explicit:b2ebf67eabeaef7b5e0a1265, file:explicit:07eac2cef30caada4c976c16, file:explicit:1e757f4f4eadfca380da107c, file:explicit:f3576bf6104be8530cc534e2. FOLLOW-UP TRIAGE: 1.1#1 (binary-safe reads), 1.1#2 (merge-base keep-local), 1.3#1 (Athena timeouts + canary), and 1.4#1 (bob-cli rebase-conflict) are all retained as remaining epic work in a child epic, not filed as tasks, because each blocks this epic's own acceptance. 1.2 and 1.5 had no proposals. Carried forward, not refiled (owned by the sase-1nf.10.1 landing triage per this plan): sase-1nf.10.1.9#3 Apollo job/tailnet 'Repository not found', and the tagged-commit 'prompt archive is unresolved' failure from sase-1nf.10.1.5/.6/.8. New production evidence for the latter: Athena drain rows also report it for toobig-8d.agent_publication_recovery.0@3b2ea8d03751 and bob-cli 12s@c13016217b44/f3b2e65a7976. Main HEAD 50ef6ba498 == origin/master. Post-start commits (003827a58d core-split refactor, ed84631e39, 223754dff3, 50ef6ba498) need no integration. epic-symbols: none.

[2026-10-21T14:43:06Z · sase-1nf.10.1.9.1.land] LANDING HANDOFF: proposing a remaining-work child epic (parent_bead sase-1nf.10.1.9.1), 'Fix the confirmed publication blockers and finish recovery acceptance', with phases drain-bound, replay-policy, install-replay, canaries, and acceptance. Its land agent resumes this landing: recheck, close sase-1nf.10.1.9.1, set plan:202610/publication_recovery_proof.md status: done, then perform this plan's delegated closure of ONLY phase sase-1nf.10.1.9 (verify the research report is attached, resolve epic-symbols). This epic stays open until then. No source, memory, or Justfile changes were made in this landing turn.

[2026-10-22T12:47:19Z · sase-1nf.10.1.9.1.6.land] LANDING BLOCKER (recorded by the sase-1nf.10.1.9.1.6 land agent, 2026-10-22). This plan is not closed, and phase sase-1nf.10.1.9 is not closed either. This plan's own closure rule ("after all child work is closed and all five checks have evidence") is not met.

Done so far:
- Child epic sase-1nf.10.1.9.1.6 landed and closed after verification. The quadratic reserved-name scan and the cached-snapshot digest regression are fixed in 54779b62f5. Byte-safe, merge-base-aware replay is in 16d63cf9b0 plus core 1503d604.
- Both hosts are installed and the Apollo bob-cli content is recovered at remote 650c73595.
- research:202610/publication_recovery_acceptance.md is published and attached to sase-1nf.10.1.9.
- All five phases of this plan were closed earlier, and there are no epic-symbol entries for this plan or sase-1nf.10.1.9.

Acceptance status:
- Checks 2, 3, and 4 PASS.
- Check 5 PARTIAL. Agent sase-1nf.10.1.9.1.6.3--1 auto-published after the install, but the acknowledged request no longer exposes its request-bound primary_revision.
- Check 1 MISSING. No named, formerly failing, stopped request has published within 120 s.

The canary_budget=fresh budget is spent. Athena used limit-1 plus a batch of 5. Each Apollo project used its limit-1 call; a follow-up batch was not allowed because the limit-1 call failed. A land agent may not spend new budget.

Blockers to check 1:
1. sase-1ni. Apollo did not lose write access. Agent-run 'ssh apollo' sessions forward Athena's agent, which offers the bobs-org/bob deploy key first, so pushes are denied. With ForwardAgent=no, Apollo authenticates as bbugyi200 and passes the push auth check. Commits a090a3a2c and f2d32a476b are stranded, ahead 1.
2. sase-1nj. Stale-revision dud worker rows win active-first selection on athena/sase.
3. The known tagged-commit "prompt archive is unresolved" obligation is blocking the revived athena timeout rows.

Human decision needed:
- Option A: after sase-1ni is fixed, authorize one new limit-1 canary for each host/project, so that check 1 can be proven here.
- Option B: accept check 1 and the check-5 revision field as deferred to sase-1nf.11's bounded drains (bounded commands are in the report), then close this plan and sase-1nf.10.1.9 with that recorded outcome.

When resolved, the closeout continues as already written: close sase-1nf.10.1.9.1, set status: done in plan:202610/publication_recovery_proof.md, then close only sase-1nf.10.1.9 with the research reference.

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nf.10.1.9.1.6.5][1] | Review required parent epic and phase evidence before final acceptance | 1 |
| read-by | [agent:sase-1nf.10.1.9.1.6.land][2] | Need the parent link, previous landing note, and descendant state to decide parent closure | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.9.1.6.5/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.9.1.6.land/README.md

<!-- sase:referenced-by:end -->
