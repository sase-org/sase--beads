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

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/publication_recovery_proof.md

<!-- sase:links:end -->

## Description

Complete the outstanding operational acceptance for sase-1nf.10.1.9 without bulk backlog draining or losing unpublished content.

## Notes

[2026-10-21T14:39:24Z · sase-1nf.10.1.9.1.land] LANDING AUDIT (land agent, 2026-10-21 ~14:40Z): all 5 phases closed but acceptance is NOT met. Checks 1 and 5 unproven; check 3 and 4 fixture-only; Apollo unique content still unpublished. Fresh read-only diagnosis found the blockers. (1) Regression from 8c6699f413 (sase-1nf.10.1.5): load_validated_publication digests cached base_snapshots after canonical re-serialization, so 40/98 legacy Apollo sase snapshots (first: 03) falsely fail 'snapshot digest mismatch' in every multi-hood drain; the raw bytes match the manifest. This blocked hood sase-1nf, so no epic worker auto-published (agents remote unchanged since b3da77e44a, 13:06Z). (2) Scoped inventory_build takes 106-148s on Athena, because get_reserved_agent_session_names rebuilds the full registry set on each of 8,689 sase_agent_ref_for_name calls (~229s of 268s under cProfile). (3) Apollo replay is still blocked by the CR text-mode read and the missing merge-base keep-local policy. Evidence: file:explicit:684de02c487788fab67ad837, file:explicit:b2ebf67eabeaef7b5e0a1265, file:explicit:07eac2cef30caada4c976c16, file:explicit:1e757f4f4eadfca380da107c, file:explicit:f3576bf6104be8530cc534e2. FOLLOW-UP TRIAGE: 1.1#1 (binary-safe reads), 1.1#2 (merge-base keep-local), 1.3#1 (Athena timeouts + canary), and 1.4#1 (bob-cli rebase-conflict) are all retained as remaining epic work in a child epic, not filed as tasks, because each blocks this epic's own acceptance. 1.2 and 1.5 had no proposals. Carried forward, not refiled (owned by the sase-1nf.10.1 landing triage per this plan): sase-1nf.10.1.9#3 Apollo job/tailnet 'Repository not found', and the tagged-commit 'prompt archive is unresolved' failure from sase-1nf.10.1.5/.6/.8. New production evidence for the latter: Athena drain rows also report it for toobig-8d.agent_publication_recovery.0@3b2ea8d03751 and bob-cli 12s@c13016217b44/f3b2e65a7976. Main HEAD 50ef6ba498 == origin/master. Post-start commits (003827a58d core-split refactor, ed84631e39, 223754dff3, 50ef6ba498) need no integration. epic-symbols: none.

[2026-10-21T14:43:06Z · sase-1nf.10.1.9.1.land] LANDING HANDOFF: proposing a remaining-work child epic (parent_bead sase-1nf.10.1.9.1), 'Fix the confirmed publication blockers and finish recovery acceptance', with phases drain-bound, replay-policy, install-replay, canaries, and acceptance. Its land agent resumes this landing: recheck, close sase-1nf.10.1.9.1, set plan:202610/publication_recovery_proof.md status: done, then perform this plan's delegated closure of ONLY phase sase-1nf.10.1.9 (verify the research report is attached, resolve epic-symbols). This epic stays open until then. No source, memory, or Justfile changes were made in this landing turn.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.10.1.9.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.10.1.9.1.land.md) | [sase-1nf.10.1.9.1](sase-1nf.10.1.9.1.md) | 0 |
