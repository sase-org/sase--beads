# Bead: sase-1id — Truthful %auto: P0 autonomy safety tales

[Bead Pages](../README.md) / sase-1id

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0yg](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0yg.md) · **Assignee:** `sase-1id.land`
**Created:** 2026-10-08 13:39:28 EDT · **Closed:** 2026-10-09 04:38:45 EDT
**Plan:** [202610/auto\_p0\_safety\_tales.md](https://github.com/sase-org/sase--plans/blob/main/202610/auto_p0_safety_tales.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/auto_p0_safety_tales.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | [bead:sase-1iq][2] | drift was introduced by sase-1id phase 6 commit c58ae7491a; landing deferred the fix because memory writes are out of scope for the land tale |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/auto_p0_safety_tales.md
[2]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1iq/README.md

<!-- sase:links:end -->

## Description

No %auto spelling silently grants more than it says, pressing A to turn auto off really turns it off, epic phase and land workers park nested epic plans for a human instead of launching them, and the docs, the macros.md memory row, and /sase_questions describe the behavior that actually ships. The three P0 task beads (sase-1hg, sase-15s, sase-1hh) are closed when the epic lands.

## Notes

[2026-10-09T07:25:38Z · sase-1id.land] LAND TRIAGE (sase-1id.land, master bfe1d9c361): PROPOSED FOLLOW-UP outcomes. (1) sase-1id.1 #1 + sase-1id.3 #1 test_shared_host_executor_handles_feedback_rejection_and_races: DECLINED, passes on master (fixed by 1914591ab4, which stopped storing _gate_source/_gate_caller in option_results). (2) sase-1id.1 #2 mypy import-not-found sase_core_rs at catalog_build.py:71: DECLINED, mypy on that file is clean on master (stale-venv artifact). (3) sase-1id.1 #3 sase-core bead_read_parity event_store_supports_read_queries_without_legacy_projection: DECLINED, fixed by sase-core e411a392 (sase-1i5.9.1.1). (4) sase-1id.2 #1 63 KNOWN check failures: DECLINED as non-specific; both sampled tests (test_default_list_includes_claimed_with_shared_glyph, test_checked_in_snapshot_has_no_drift) pass on master. (5) sase-1id.3 #2 17 base-identical failures: the 'directive completion' one (tests/ace/tui/widgets/test_directive_completion_candidates.py::test_directive_completion_includes_representative_descriptions) is CAUSED BY THIS EPIC (grammar phase rewrote the core %auto metadata in sase-core e8606a56) and is epic remaining work; the rest are DECLINED as a non-specific aggregate (sampled ones pass on master). (6) sase-1id.4 #1 symvision BeadBoardSnapshot/BeadStoreFingerprint: DECLINED, already privatized on master (_BeadBoardSnapshot/_BeadStoreFingerprint in src/sase/core/bead_read_facade.py). (7) sase-1id.6 #1 _lint-test-waits on tests/ace/tui/test_plan_decision_ace_stale.py:183,310: ROUTED as DISCOVERED ISSUE to active causal epic sase-1hi.10.7.6 (loops added by 1820636212 / sase-1hi.10.7.6.1). Land-review extra: stale %auto wording in docs/blog/posts/* DECLINED (dated blog narratives, not reference docs).

[2026-10-09T07:25:43Z · sase-1id.land] LAND deploy_skill (sase-1id.land): deployed generated skills from the landed clean tree bfe1d9c361 (ancestor of origin/master; prior manifest source f92bde8a is an ancestor) with '.venv/bin/sase skill init --yes' (the global sase is an editable install of the lagging primary checkout, so it could not see c58ae7491a). 14 files written (sase_questions x7 with 'Recommended Option First', sase_monitor x7 from 6f240b3c96); chezmoi commit a8d1a2fe pushed and applied; manifest source_commit now bfe1d9c361. No --allow-dirty or --force used.

[2026-10-09T07:27:44Z · sase-1id.land] LAND REVIEW (sase-1id.land, master bfe1d9c361): epic-caused gaps found and planned as a lander tale that also closes the epic: (1) run_agent_runner_refresh._live_auto_prompt_mode widens %auto:plan (and legacy off/foo) to bare %auto on post-wait re-exec; (2) run_agent_markers/run_agent_wait_markers pass disk_meta={} on read failure, stripping live auto keys; (3) service._normalize_cross_tier_plan_spec parks invalid auto arguments instead of raising; (4) sase-core AgentMetaWire never carries auto_approve_argument, so a parked %auto:plan epic gate is hidden from pending in agent list/TUI; (5) %a:foo / backtick colon spellings give different error text in Python vs Rust/LSP; (6) stale test_directive_completion_includes_representative_descriptions after the core metadata rewrite; (7) prompt-bar duplicate message with %dispatch + bad %auto; (8) missing live_meta write-back-site and A-toggle end-to-end tests; (9) stale propose comment, two docs/macros.md nits, undocumented 'does not cover' propose line, child-epic prompt wording in default_config.yml. Verified done: all 6 phases' core deliverables, task beads sase-1hg/sase-15s/sase-1hh closed, sase-11g note present, core pin 5c4033f6 contains e8606a56, no drift commit bypasses the cross-tier normalization, epic-symbols empty.

[2026-10-09T07:52:18Z · sase-1h8.13.1.9.land] DISCOVERED ISSUE (found by the sase-1h8.13.1.9 land agent, clean master bd830064ca, 2026-10-09): sase validation 'init memory --check' fails, and tests/main/test_init_memory_committed_drift.py::test_repo_project_memory_notes_match_generator_output fails deterministically when run alone. The generator wants sase/memory/README.md macros.md 'Approx. tokens' 3033->3694 and the total 21237->21898; that is ceil(14774 chars/4) for the current macros.md. c58ae7491a (SASE_BEAD sase-1id.6) edited sase/memory/macros.md and hand-set the README counts to 3033/21237, which do not match the committed note. Fix: regenerate with 'sase init memory' (memory-write path) and commit the README. Evidence: sase tool run check run 7d658c634fd39565484d98edcae94afa (SASE validation UNKNOWN, test FLAKY-classified but deterministic).

[2026-10-09T08:38:45Z · sase-1id.land--1] LAND CLOSEOUT (finish_auto_p0_landing, items 1-9): all six phases verified against source (grammar/live_meta/tier_mismatch/epic_workers/prompt_bar/docs_truth). Task beads sase-1hg, sase-15s, sase-1hh CLOSED (verified). sase-11g inherit_mode note present. /sase_questions deployed in chezmoi a8d1a2fe. Follow-up triage recorded in land notes (stale-venv/mardytooltip declinations, _lint-test-waits routed to sase-1hi.10.7.6, blog wording declined). Fixes: (1) post-wait re-exec derives directive from auto_launch_prefix via set_prompt_directive, _live_auto_prompt_mode deleted; tests in test_plan_auto_live_meta.py. (2) disk-read failure passes disk_meta=None, in-memory stale auto keys dropped; tests added. (3) cross-tier normalize only valid-but-uncovered args via new public predicate, invalid raises invalid_auto_argument; create_gate tests. (4) sase-core AgentMetaWire carries trailing auto_approve_argument (skip_serializing_if None for byte-stability), scanner fills via coerce_str; scanner unit test + 12/12 python_wire_parity; sase integration test through real scanner shows pending review. (5) core builds colon spellings as canonical %auto:<value>; parity tests assert identical message text. (6) stale completion-candidate assertions updated to core metadata text. (7) prompt-bar duplicate auto message suppressed + %a precheck simplified; widget test. (8) live_meta write-back toggle-preserved coverage + A-toggle end-to-end manual-gate test. (9) propose comment/docs-macros/cli/sdd wording fixed, child-epic approval clauses in default_config.yml. CHECKS: sase sase-tool-run a4a747647b24923f494aa883af7f33c9 — fmt/ruff/mypy/keep-sorted/feature-flags/pyscripts/model-policy pass, targeted suites 78+164+38+14 pass; sole failure lint(test-waits) test_plan_decision_ace_stale.py:183,310 is the plan-attributed sase-1hi.10.7.6 issue, untouched by this diff. sase-core: agent_scan/auto_directive suites pass, parity 12/12, scanner test passes; full check 4730 lib pass with 1 timing-flaky replay golden (lock_wait_ms 0v2, bead-mutation domain, passes solo retry). just symvision: only 3 unused-public findings, all from HEAD 3b3d876911 (sase-1ig plugin work), none from this diff. epic-symbols empty.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1id.1](sase-1id.1.md) | Fail-closed %auto grammar in sase-core and Python | ✓ closed | medium | 2026-10-08 | 1 | 2 |
| [sase-1id.2](sase-1id.2.md) | Live agent meta is the only %auto source | ✓ closed | medium | 2026-10-08 | 1 | 1 |
| [sase-1id.3](sase-1id.3.md) | A plan-tier mismatch asks instead of erroring | ✓ closed | medium | 2026-10-08 | 1 | 1 |
| [sase-1id.4](sase-1id.4.md) | Epic phase and land workers run under %auto:tale | ✓ closed | medium | 2026-10-08 | 1 | 1 |
| [sase-1id.5](sase-1id.5.md) | Prompt bar shows %auto grammar errors | ✓ closed | small | 2026-10-08 | 1 | 1 |
| [sase-1id.6](sase-1id.6.md) | Docs, memory, and /sase\_questions describe shipped behavior | ✓ closed | medium | 2026-10-08 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1id: Truthful %auto: P0 autonomy safety tales [closed]"]
    n1["sase-1id.1: Fail-closed %auto grammar in sase-core and Python [closed]"]
    n2["sase-1id.2: Live agent meta is the only %auto source [closed]"]
    n3["sase-1id.3: A plan-tier mismatch asks instead of erroring [closed]"]
    n4["sase-1id.4: Epic phase and land workers run under %auto:tale [closed]"]
    n5["sase-1id.5: Prompt bar shows %auto grammar errors [closed]"]
    n6["sase-1id.6: Docs, memory, and /sase_questions describe shipped behavior [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n1 -.-> n5
    n1 -.-> n6
    n2 -.-> n3
    n2 -.-> n6
    n3 -.-> n4
    n3 -.-> n6
    n4 -.-> n6
    n5 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1id.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1id.1.md) | [sase-1id.1](sase-1id.1.md) | 2 |
| [bbugyi200.athena.sase-1id.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1id.2.md) | [sase-1id.2](sase-1id.2.md) | 1 |
| [bbugyi200.athena.sase-1id.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1id.3/README.md) | [sase-1id.3](sase-1id.3.md) | 1 |
| [bbugyi200.athena.sase-1id.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1id.4/README.md) | [sase-1id.4](sase-1id.4.md) | 1 |
| [bbugyi200.athena.sase-1id.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1id.5.md) | [sase-1id.5](sase-1id.5.md) | 1 |
| [bbugyi200.athena.sase-1id.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1id.6.md) | [sase-1id.6](sase-1id.6.md) | 1 |
| [bbugyi200.athena.sase-1id.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1id.land.md) | [sase-1id](README.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c70ee9a`](https://github.com/sase-org/sase/commit/c70ee9af3d4812a23777c11ef77b2ac75dea4fa9) | feat(auto): live agent meta is the only %auto source | [sase-1id.2](sase-1id.2.md) | 2026-10-08 14:38:50 EDT |
| sase-core | [`sase-core@e8606a5`](https://github.com/sase-org/sase-core/commit/e8606a564e4ddccbc4eb2369f4f32dd02ce8c3af) | feat(auto): fail-closed %auto grammar classifier in sase-core | [sase-1id.1](sase-1id.1.md) | 2026-10-08 14:59:54 EDT |
| sase | [`0ac86ad`](https://github.com/sase-org/sase/commit/0ac86ad40c5fb8a31ca2bed929200fb1534772d3) | feat(auto): fail-closed %auto grammar in Python extractor and metadata | [sase-1id.1](sase-1id.1.md) | 2026-10-08 15:04:17 EDT |
| sase | [`771127d`](https://github.com/sase-org/sase/commit/771127db29ec46f6679bf9880c06a1279b2bd6f6) | fix(plan-gates): park tier-mismatched gates instead of erroring | [sase-1id.3](sase-1id.3.md) | 2026-10-08 16:09:27 EDT |
| sase | [`e6adb11`](https://github.com/sase-org/sase/commit/e6adb110af9f6be222782977c8840e2d91cf7cdf) | feat(bead): run epic phase and land workers under %auto:tale so nested epics wait for review | [sase-1id.4](sase-1id.4.md) | 2026-10-08 16:33:43 EDT |
| sase | [`bd6c717`](https://github.com/sase-org/sase/commit/bd6c7173dd49894d8ec38a821320c7826634cf54) | fix(symvision): privatize newly-reported unused-public symbols to zero NEW | [sase-1id.5](sase-1id.5.md) | 2026-10-09 02:12:07 EDT |
| sase | [`c58ae74`](https://github.com/sase-org/sase/commit/c58ae7491ad6ed341dfc91743f989e8623d84eab) | docs(sase-1id.6): align %auto docs with tier-scoped auto-approved truth | [sase-1id.6](sase-1id.6.md) | 2026-10-09 02:37:13 EDT |
| sase-core | [`sase-core@6faaa65`](https://github.com/sase-org/sase-core/commit/6faaa65310d02be7e46704f876a8a718f16ed9eb) | fix(sase-1id): carry auto\_approve\_argument on AgentMetaWire; canonical %auto colon errors | [sase-1id](README.md) | 2026-10-09 05:38:31 EDT |
| sase | [`7e87589`](https://github.com/sase-org/sase/commit/7e87589fb5d89fcc5a981301fd96b32f639091a9) | fix(sase-1id): close truthful-%auto land-review gaps, items 1-9 with tests | [sase-1id](README.md) | 2026-10-09 06:02:54 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1id.4][1] | Need epic DECISIONS and status | 1 |
| read-by | [agent:sase-1id.land--3][2] | read full closeout note | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1id.4/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1id.land.md

<!-- sase:referenced-by:end -->
