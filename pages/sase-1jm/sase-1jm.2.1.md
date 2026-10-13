# Bead: sase-1jm.2.1 — Archive corpus, in:archive scope, and CLI parity

[Bead Pages](../README.md) / [sase-1jm.2](sase-1jm.2.md) / sase-1jm.2.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.2.md) · **Assignee:** `sase-1jm.2.1.land`
**Created:** 2026-10-10 07:31:47 EDT · **Closed:** 2026-10-10 20:09:52 EDT
**Plan:** [202610/archive\_corpus.md](https://github.com/sase-org/sase--plans/blob/main/202610/archive_corpus.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/archive_corpus.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 7 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/archive_corpus.md

<!-- sase:links:end -->

## Description

sase-core answers which hidden archived runs match a query, in what order, and grouped how, and sase agent search in:archive returns that same answer.

## Notes

[2026-10-10T20:33:07Z · sase-1jm.2.1.land] LAND TRIAGE (sase-1jm.2.1.land, master 2c9f761210): PROPOSED FOLLOW-UP outcomes. (1) sase-1jm.2.1.1 #1, sase-1jm.2.1.2 #2, sase-1jm.2.1.4 #1, sase-1jm.2.1.6 #2 (feature-flag rule-7 lint on closed flag beads) DECLINED: tools/check_feature_flags now exits 0 on current master; later sase-1jc retirements removed those definitions. (2) sase-1jm.2.1.4 #2 (test_agent_run_stops_on_generic_output) DECLINED: passes on current master. (3) sase-1jm.2.1.5 #1 split into its live parts: import budget 3515>3513 -> +1 sase-1ic (tui_import_closure shows 3518 at pre-epic 2f5070d129, so not this epic); bob dry-run digest test -> +1 sase-1jj; marker path-passing audit (session_root_tab moved to run_agent_directive_metadata_preserved.py) -> +1 sase-1by; contract-manifest failure is a knock-on of (4). (4) sase-1jm.2.1.5 #2 (test_node_finder_snapshot collection ImportError) already recorded as DISCOVERED ISSUE #6 on active epic sase-1jc (caused by sase-1jc.6 b46ecb0a94); no new task. (5) sase-1jm.2.1.6 #1 (bench budgets missed: build p95 1697ms vs 300, query+first window 2731ms vs 30) NOT a follow-up: caused by this epic (corpus round-trips through Python dicts on every call), so it is remaining epic work. Also discovered: sase-1jn (symvision dead private __getattr__ in profiles/__init__ from sase-1jm.2.1.4) already fixed by 8fdf12a8a8 -> closed; project_for_done symvision failure from closed epic sase-1j6 -> new task sase-1jp; update_failure_geometry symvision failures already a PROPOSED FOLLOW-UP on sase-1jc.9.

[2026-10-10T23:59:17Z · sase-1jc.land] DISCOVERED ISSUE (routed by the sase-1jc land agent; proposed by sase-1jc.12 notes #4/#5): two master reds trace to this epic's phases. (1) tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift and ::test_current_structural_view_matches_checked_in_snapshot fail deterministically at master 77ad508a6c and on a clean origin/master worktree: the only drift is sase/agent/search description_digest f75a3fcb2bbd4075 -> d0bf3fe5c8158622, from 5f47d11935 (sase-1jm.2.1.6, archive search CLI parity) which changed the parser help without regenerating tests/completion/snapshots/cli_spec.json. (2) just _lint-symvision lists five unused public symbols in src/sase/core/agent_archive_corpus_cache.py (AgentArchiveCorpusCacheKey, CachedAgentArchiveCorpus, archive_corpus_cache_key, invalidate_agent_archive_corpus_cache, link_facet_signature), added by f7026aa2f2 (sase-1jm.2.1.5). Evidence: ToolRun d149ccc8b78c563c53d20f299b833378. No separate task filed.

[2026-10-11T00:09:52Z · sase-1jm.2.1.land] Lander verified all six phases' work in code. Follow-up triage outcomes are in this epic's land-triage note. Archive corpus stays compiled in Rust behind a frozen AgentArchiveCorpusHandle (PreparedAgentArchiveCorpus). Bench p95: build 296.0ms (budget 300ms), query+first window 27.5ms (budget 30ms). Workflow-child names resolve to owner by archive key, else raw_suffix==parent_timestamp, else drop. Cache module privatized unused public symbols; just symvision has no agent_archive_corpus_cache.py entry and no --epic-symbol entries for sase-1jm.2.1. sase-core sase tool run check 6e69c142157dc7e0d009993a8a08f6bd succeeded. sase sase tool run check 13536c297273de867cec43aba76a1a79 verdict no_new_failures (14 KNOWN, 1 FLAKY): KNOWN test_tui_app_import_stays_under_startup_budget (sase-1ic) and test_node_finder_snapshot ImportError (sase-1jc note #6); FLAKY test_tracked_marker_path_passing_sites_are_reviewed (sase-1by). Remaining just symvision hits are update_failure_geometry.py (sase-1jc.9) and project_for_done (sase-1jp).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.2.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.2.1.land.md) | [sase-1jm.2.1](sase-1jm.2.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@cd2a72e`](https://github.com/sase-org/sase-core/commit/cd2a72eda5e92ee838f2567246db8b4f99e33ae9) | feat(archive): keep compiled corpus in Rust and resolve child owners | [sase-1jm.2.1](sase-1jm.2.1.md) | 2026-10-10 20:12:05 EDT |
| sase | [`04ed4b3`](https://github.com/sase-org/sase/commit/04ed4b33cbd426c34c8282aef702dc261e6bee45) | feat(archive): query the Rust-held corpus handle from the facade and CLI | [sase-1jm.2.1](sase-1jm.2.1.md) | 2026-10-10 21:12:36 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jc.land][1] | Check recorded notes on symvision and completion snapshot drift before routing sase-1jc follow-ups | 2 |
| read-by | [agent:sase-1jm.2.1.1][2] | parent epic decisions | 1 |
| read-by | [agent:sase-1jm.2.1.2][3] | Need the epic decisions and phase constraints | 1 |
| read-by | [agent:sase-1jm.2.1.4][4] | Need parent epic decisions and full phase list | 1 |
| read-by | [agent:sase-1jm.2.1.5][5] | Need parent epic scope DECISIONS and design | 1 |
| read-by | [agent:sase-1jm.2.1.6--1][6] | Need parent epic decisions and phase-specific landing constraints | 1 |
| read-by | [agent:sase-1jm.9.land][7] | Confirm every sase-1jm descendant is closed before parent close | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.land/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.2.1.1/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.2.1.2/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.2.1.4/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.2.1.5/README.md
[6]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.2.1.6.md
[7]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.9.land/README.md

<!-- sase:referenced-by:end -->
