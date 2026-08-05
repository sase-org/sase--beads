# Bead: sase-fa — Revert async sidecar publication so \`sase commit\` publishes sidecars inline again

[Bead Pages](../README.md) / sase-fa

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.t4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.t4/README.md) · **Assignee:** `sase-fa.land`
**Created:** 2026-08-05 14:26:21 EDT · **Closed:** 2026-08-05 18:29:15 EDT
**Plan:** [202608/revert\_async\_sidecar\_publication.md](https://github.com/sase-org/sase--plans/blob/main/202608/revert_async_sidecar_publication.md)

## Description

`sase commit` once again publishes to every appropriate sidecar repo (agents, beads, plans) before it returns, so the `SASE_AGENT` footer URL resolves as soon as the commit lands. The `sidecar_publication` chop and the `publications` lumberjack are removed, the durable outbox is narrowed back to agent-hood retries, the agents sidecar corruption that is currently blocking all publication is repaired, and this project's agents repo is fully synced.

## Notes

[2026-08-05T22:29:15Z · sase-fa.land] LAND VERIFICATION for epic sase-fa (revert async sidecar publication).

VERIFY (step 1). Read the plan (plans:202608/revert_async_sidecar_publication.md), all five phase beads, and every phase note. All five phases closed resolution=done. Cross-phase proposals traced to completion in code, not taken on report: sase-fa.1's 'chop must delete drain_bead_pages_publication / drain_plan_header_publication / drain_sidecar_push_publication' -> done by sase-fa.2 (all three symbols absent from src/ and tests/); sase-fa.2's 'doctor _publication_drain_issue + publication_outbox_diagnostics still name the removed lane' -> done by sase-fa.3 (checks_agent_publication.py and publication_outbox_diagnostics.py contain no lumberjack/axe/lane/chop/drain references); sase-fa.2's docs prose sweep -> done by sase-fa.5 (grep over docs/ for sidecar_publication / publications lane / -L publications is clean, as is sase/memory/*.md).

Code read against the plan, not just the phase notes: workflow_publication.py::run_agent_publication_step publishes bead pages -> resolves the revision -> prompt archive -> plan header -> agent hood inline, with the pre-epic loud-failure contract restored (RunResult FAILED plus a 'sase commit --resume' hint on an unresolvable/absent revision, on an exception out of publish_committed_agent_hood, and on error-without-queued-or-skip); _commit_store.push_sdd_store_after_commit no longer short-circuits sidecar stores; the chop script, its test, its console script and the publications lane are gone (default_config.yml has exactly the five pre-epic lanes; 'sase axe chop list' has no sidecar_publication); PUBLICATION_OUTBOX_SCHEMA_VERSION is 5 with PublicationKind, the rank ordering, and every kind-specific field removed - the only surviving bead_pages/plan_header/sidecar_push strings in the tree are inside the v4-drop acceptance test; publication_repair.py, 'sase agent sync --repair-digests' and doctor check state.agent_publication_digest all exist (commit 2a9627bc0).

Live re-verification: 'sase doctor' shows 0 digest drift and 0 quarantined/retired requests for the sase project (both remaining WARNs are bob-cli only); the agents sidecar has families/bbugyi200.athena.t2.md at origin/main - the 404 that motivated the revert - and origin/main has advanced past 49bdd7996 to b4b9641ed. Static gates: ruff clean, mypy clean over 2749 files; 24 targeted tests pass (tests/test_commit_publication_inline.py, tests/agents_sync/test_publication_outbox.py, tests/doctor/test_checks_agent_publication.py). 'just lint' does fail one symvision node, progress_fingerprint, which comes from unrelated master commit 840cdff10 and is filed as sase-fj.

RESIDUE FIXED HERE. sase-fa.2's proposal to delete the dead axe state was addressed to phase repair (sase-fa.4), which had already closed 45 minutes earlier, so no phase executed it. Confirmed still present and still live-failing: ~/.sase/axe/lumberjacks/publications/ held sidecar_publication_backoff.json plus chop runs whose last records (through 17:57) are all status=missing_script, 'Chop script not found: sase_chop_sidecar_publication'. Retired to ~/.sase/trash/axe-lumberjack-publications-20260805T182204; ~/.sase/axe now has no publications lane and no sidecar_publication state.

INTEGRATE (step 2). Reviewed all 15 non-epic commits from the epic's first commit (2a9627bc0) to current master (256da2887), including the two that landed while this land phase ran. No conflict and no duplication with the restored inline path: the concurrent epics sase-fb (bead-store publication safety: 99eedf749, d1b6f01a9, 980bdd337) and sase-fc (bead creation time) were all authored on top of the restored path, and sase-fb's ensure_bead_mutation_published / workspace-eviction guard are verification layers over the git push rather than reimplementations of sidecar publication. Nothing anywhere in src/, tests/, docs/ or sase/memory/ still describes commit-time publication as queued or lane-owned.

FOLLOW-UPS (step 3). Every PROPOSED FOLLOW-UP from the five phases was collected and dispositioned: (a) the three cross-phase proposals above were already satisfied inside the epic; (b) the axe residue was completed here; (c) flaky-test proposals corroborated on the existing tasks rather than duplicated - +1 sase-e2 (test_concurrent_bead_mutations_wait_past_the_old_lock_timeout, with the 3.6s-isolated vs 38-68s-under-load timings from three phases) and +1 sase-ct (ACE artifacts_files_detail order dependence and the agents-slow-tools PNG snapshot); the one node with no bead of its own, tests/notification_store/test_mute_snooze.py::TestMarkMuted::test_unmute_clears_snooze, was recorded as a note on active epic sase-fd, which owns that flake class; (d) new ready tasks created - sase-fh (agents_sync/git_sync.py::_publication_request_materialized only probes agents/<name>/README.md so every family-lane publication is falsely reported as not materialized and accrues attempts toward quarantine; predates the epic, introduced by 447d96e09, and still reproducing in the bob-cli outbox), sase-fi (prompt-archive publication has no durable retry; re-verified independently - the agents sidecar has prompt archives for sase-fa.1/.2/.3 but none for sase-fa.4 or sase-fa.5, and the task records the tension with this epic's deliberate narrowing of the outbox), sase-fk (bob-cli digest drift plus its 9 quarantined / 2 retired requests, left untouched by scope decision 4, with the sase-f6 full-sync caveat spelled out), and sase-fj (the unrelated symvision failure above). (e) DECLINED: doctor's project.bead_pages ERROR - 5 misattributed commit links on the sase-b5 and sase-b7 pages - is real and still reproducing, but it predates this epic (pages written 2026-07-30, check added the same day by f62e8cd01) and is already tracked by task sase-ed, which the owner closed as canceled in today's backlog triage after re-verifying these exact five links; a +1 would auto-reopen a bead the owner deliberately deprioritized hours ago, so it was left alone rather than reopened by this land phase.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-fa.1](sase-fa.1.md) | Restore synchronous sidecar publication on the commit path | ✓ closed | medium | 2026-08-05 | 1 | 1 |
| [sase-fa.2](sase-fa.2.md) | Remove the sidecar\_publication chop and publications lumberjack | ✓ closed | medium | 2026-08-05 | 1 | 1 |
| [sase-fa.3](sase-fa.3.md) | Narrow the durable outbox back to agent-hood retries | ✓ closed | medium | 2026-08-05 | 1 | 1 |
| [sase-fa.4](sase-fa.4.md) | Repair the agents sidecar digest corruption blocking all publication | ✓ closed | medium | 2026-08-05 | 1 | 1 |
| [sase-fa.5](sase-fa.5.md) | Docs, end-to-end verification, agents-repo sync, and bead bookkeeping | ✓ closed | small | 2026-08-05 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-fa: Revert async sidecar publication so `sase commit` publishes sidecars inline again [closed]"]
    n1["sase-fa.1: Restore synchronous sidecar publication on the commit path [closed]"]
    n2["sase-fa.2: Remove the sidecar_publication chop and publications lumberjack [closed]"]
    n3["sase-fa.3: Narrow the durable outbox back to agent-hood retries [closed]"]
    n4["sase-fa.4: Repair the agents sidecar digest corruption blocking all publication [closed]"]
    n5["sase-fa.5: Docs, end-to-end verification, agents-repo sync, and bead bookkeeping [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n1 -.-> n2
    n1 -.-> n5
    n2 -.-> n3
    n2 -.-> n5
    n3 -.-> n5
    n4 -.-> n5
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fa.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fa.1/README.md) | [sase-fa.1](sase-fa.1.md) | 1 |
| [bbugyi200.athena.sase-fa.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fa.2/README.md) | [sase-fa.2](sase-fa.2.md) | 1 |
| [bbugyi200.athena.sase-fa.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fa.3/README.md) | [sase-fa.3](sase-fa.3.md) | 1 |
| [bbugyi200.athena.sase-fa.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fa.4/README.md) | [sase-fa.4](sase-fa.4.md) | 1 |
| [bbugyi200.athena.sase-fa.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fa.5/README.md) | [sase-fa.5](sase-fa.5.md) | 1 |
| [bbugyi200.athena.sase-fa.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fa.land/README.md) | [sase-fa](README.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2a9627b`](https://github.com/sase-org/sase/commit/2a9627bc0814c495b8b5a99145eb7c17c72059ee) | fix(agents-sync): repair stale hood-snapshot digests and add drift check | [sase-fa.4](sase-fa.4.md) | 2026-08-05 15:20:33 EDT |
| sase | [`de78052`](https://github.com/sase-org/sase/commit/de7805278926e3a9abd97b475afca158363d7ffc) | fix: publish sidecar work inline on the commit path | [sase-fa.1](sase-fa.1.md) | 2026-08-05 15:51:02 EDT |
| sase | [`e99f501`](https://github.com/sase-org/sase/commit/e99f5017d39fc15f6a8f5082fbd82ed2d768a2db) | feat!: remove the sidecar\_publication chop and publications lumberjack | [sase-fa.2](sase-fa.2.md) | 2026-08-05 16:17:49 EDT |
| sase | [`ccf4d77`](https://github.com/sase-org/sase/commit/ccf4d77a9b1ffe83936e81c082040d61d2b8af60) | feat!: narrow the durable publication outbox back to agent-hood retries | [sase-fa.3](sase-fa.3.md) | 2026-08-05 17:10:00 EDT |
| sase | [`02dcea6`](https://github.com/sase-org/sase/commit/02dcea68b016131e31f6d79bde7d9511a51385c2) | docs: describe restored inline sidecar publication | [sase-fa.5](sase-fa.5.md) | 2026-08-05 17:59:47 EDT |
| sase--plans | [`sase--plans@15bb224`](https://github.com/sase-org/sase--plans/commit/15bb22427ae089ef9944ab0cf9622895daac0bcb) | docs(plans): mark the async sidecar publication revert plan done | [sase-fa](README.md) | 2026-08-05 18:32:01 EDT |
