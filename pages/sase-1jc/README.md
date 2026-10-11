# Bead: sase-1jc — Retire every current feature flag while preserving enabled behavior

[Bead Pages](../README.md) / sase-1jc

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zb.md) · **Assignee:** `sase-1jc.land`
**Created:** 2026-10-09 22:28:23 EDT · **Closed:** 2026-10-10 20:22:50 EDT
**Plan:** [202610/retire\_all\_feature\_flags.md](https://github.com/sase-org/sase--plans/blob/main/202610/retire_all_feature_flags.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/retire_all_feature_flags.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | [bead:sase-1jq][2] | Proposed by every sase-1jc phase (sase-1jc.1 through sase-1jc.12 PROPOSED FOLLOW-UP notes); the epic's auto memory decision skipped this edit |
| related | [bead:sase-1jr][3] | Proposed by every sase-1jc phase (sase-1jc.1 through sase-1jc.12 PROPOSED FOLLOW-UP notes); the epic's auto memory decision skipped this edit |

_Plus 9 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/retire_all_feature_flags.md
[2]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1jq/README.md
[3]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1jr/README.md

<!-- sase:links:end -->

## Description

Remove all 23 registered feature flags and their disabled implementations across sase and sase-core, preserve today's all-enabled behavior, and leave an empty, usable flag registry through strictly sequential implementation phases.

## Notes

[2026-10-10T11:36:52Z · sase-1ip.land] DISCOVERED ISSUE: During the approved %auto E1 closeout,  run ae9a4f90ef6f8edac0a850be51a99ae9 passed fmt, model policy, keep-sorted, Ruff, and mypy, then stopped at lint (feature flags): rule 7 reports closed beads sase-18l and sase-1ar still have definitions legacy_agent_family_syntax and legacy_sase_shell_syntax. No E1 diff touches feature-flag files. The closed bead IDs are the exact flags retired in sase-1jc.5; active phase sase-1jc.12 owns the empty-registry and residual-definition audit. This appears to be workspace-tree/shared-bead-state skew, but this checkout cannot pass the gate until the cleanup tree is reconciled. Routed here because the active retirement epic owns it; no standalone task filed.

[2026-10-10T11:51:24Z · sase-1ip.land] Follow-up verification in SASE ToolRun 426d8fbda51a877454bf690b8ff72495 reproduced the already-owned rule 7 failures: closed flag beads sase-18l and sase-1ar still have legacy_agent_family_syntax and legacy_sase_shell_syntax definitions. fmt, model policy, keep-sorted, Ruff, and mypy passed; lint (feature flags) stopped the guarded check. The surviving definitions remain in the scope of this active retirement epic; no duplicate task filed.

[2026-10-10T13:25:13Z · sase-1io.7.6.land] DISCOVERED ISSUE: flag-retirement lint is still red on current master and blocks the v0.18.0 gates. Full CI 38029274494 lint failed rule 7: closed flag bead sase-s7 still has a surviving typed_launch_units definition (sase-1jc.2 retired it; sase-1jc.12 owns the empty-registry cleanup). This is the same rule 7 class already noted here for sase-18l and sase-1ar, with a new bead. Master Gate 38053026930 lint also failed on unused public ArtifactIndexProjection in src/sase/agents/catalog/_sources.py, which sase-1jc.6 already recorded as a proposed follow-up. Epic sase-1io.7.6 will not edit the flag registry or the agents-query removal while this epic is open. No duplicate task filed.

[2026-10-10T14:49:37Z · 0ze--code] DISCOVERED ISSUE: preserve_monitor_settlement_outcomes check 2905cfc582040e913bbe004cd73ee84b passed fmt, model policy, keep-sorted, Ruff, and mypy, then stopped at lint (feature flags) rule 7: closed beads sase-wr, sase-rx, sase-qu, and sase-105 still have surviving definitions ace_refresh_tokens, admin_center_flags, ref_sync_gesture, and refresh_panel. No settlement-outcome diff touches feature-flag files. Those closed bead IDs are the exact flags retired in sase-1jc.7; active phase sase-1jc.12 owns the empty-registry and residual-definition audit. Same workspace-tree/shared-bead-state skew already noted here. No duplicate task filed.

[2026-10-10T17:17:00Z · 69] DISCOVERED ISSUE: During implementation of the adaptive update failure dialog, SASE ToolRun 2fe97e8d72a2bb54b2d9167aea5e11a6 passed fmt, model policy, keep-sorted, Ruff, and mypy, then stopped at lint (feature flags) rule 7: closed flag beads sase-1ft, sase-11f, sase-13w, and sase-11p still have definitions agents_session_manifest_compat, axe_routine_job_contract, bgcmd_legacy_slots, and slim_agents_manifest. The modal change touches no feature-flag files. This independently reproduces the same stale-definition class already recorded here; phase sase-1jc.12 owns the empty-registry and residual-definition audit. No separate task filed.

[2026-10-10T17:42:48Z · sase-1j6.10.land] DISCOVERED ISSUE: tests/ace/tui/test_node_finder_snapshot.py:34 still re-exports test_query_hidden_on_both_flag_branches, but b46ecb0a94 (agents_unified_query retirement) renamed it to test_query_hidden_marks_nonmatching_rows in tests/ace/tui/test_node_finder_snapshot_hidden.py. Collection fails with ImportError on master e5e58ac3d5 (reproduced 2026-10-10). That also breaks tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection (pytest -m contract --collect-only exits 2), and Master Gate 38067967749 test(4)/test(7) are red. Proposed by sase-1j6.10.7 note #6 and routed here by the sase-1j6.10 landing because this retirement epic caused it. No separate task filed.

[2026-10-10T20:19:29Z · 6h--1] DISCOVERED ISSUE: live_handoff_premature_done verification ToolRun e844e6d52f750bd33bda0a2559aee803 passed fmt, model policy, keep-sorted, Ruff, and mypy, then stopped at lint (feature flags) rule 7: closed flag beads sase-1gw, sase-1gv, sase-1h4, and sase-178 still have surviving definitions claude_helper_channel, grok_rules_delivery, instruction_shadow_render, and muse_synchronous_shell. The live-handoff diff does not touch feature-flag files. Those beads were closed at 2026-10-10T19:17Z by phase sase-1jc.10 claiming the registry entries were removed, but this origin/master checkout still defines them. Same workspace-tree/shared-bead-state skew already noted here; sase-1jc.10 is still in_progress and sase-1jc.12 owns the empty-registry residual-definition audit. No duplicate task filed.

[2026-10-11T00:22:50Z · sase-1jc.land] LANDED (sase-1jc.land, master 77ad508a6c + landing diff). VERIFIED: all 12 phases closed and every phase note reviewed; production FeatureFlag enum and definitions are empty, `sase flag list --json` returns flags:[] (checkout and global install), all 23 dossiers closed, sase-core pin 6a12a4f6 == sase-core tip with only inert compat constants and test fixtures left there; epic DECISIONS honored (macros.md and tui_perf.md untouched). git grep for all 23 keys leaves only CHANGELOG history, retirement regressions, doctor check ids, live alias-reader module names, the visual fixture's synthetic key, and the declined memory note.
LANDING FIXES (epic leftovers): removed the ignored internal `accept_legacy` switch (config loading/macro sources, content_layout, plugin discovery, plugin input types, macro LSP binary lookup; binding payloads still send accept_legacy_xprompt_names=True), the ignored `persisted` switch plus normalize_persisted_* wrappers and the redundant gate-turn fork_normalizer split, and routine_job_contract_enabled() plus dead routine_job_contract kwargs; fixed phase-12 doc/doctor text claiming retired macro definition dirs and the retired entry-point group are never loaded (they always load), the stale typed-launch sentence in docs/axe.md, the provider_drain 'beta flag' schema description, stale flag-off comments, and retired-key test fixtures. Fixed fakey test_usage_limit_e2e, which phase 11's unconditional drain broke (passes at 5235b17274~1, fails after): it now asserts the drain submission that owns the notification.
INTEGRATION: 99fed4110c (toobig split of autonomy landing-gap tests) re-introduced pre-phase-11 override_flags(autonomy_record_only) parametrizations; restored phase 11's unconditional bodies and test_apply_removes_stale_keys. sase-telegram: /xprompts alias unconditional, dead legacy_xprompt_alias_enabled removed, stale override_flags(agent_sudo_requests) dropped, docs updated (sase tool run check 2dab6e6bfe70cd9ea685b2f561fa19af green, 776 passed). sase-nvim: 68 'remove with legacy_xprompt_syntax' markers and 4 README passages now say the retired aliases stay accepted. Other post-start commits reviewed; none duplicate or conflict.
VERIFICATION: sase tool run check fd37d6031a304d036e1fe400b9123d50: fmt/ruff/mypy/other lint green; symvision 17 KNOWN (not epic); 6 test failures all reproduce on clean origin/master and are tracked below. Focused suites 345+898+68 passed.
FOLLOW-UP TRIAGE: macros.md beta wording (all 12 phases) -> new memory task sase-1jq; tui_perf.md rule 14 (all 12 phases) -> new memory task sase-1jr; update_failure_geometry symvision (.9 #1, .11 #3, .12 #4) -> new task sase-1js; project_for_done symvision (.12 #4) -> +1 sase-1jp; agent_archive_corpus_cache symvision and cli_spec 'agent search' drift (.12 #4/#5) -> DISCOVERED ISSUE on active epic sase-1jm.2.1 (caused by its .5/.6 commits); marker path-passing audit (.7 #4) -> +1 sase-1by; TUI import budget (.4 #1, .10 #3, .12 #5) -> +1 sase-1ic; bob digest test (.10 #3, .12 #5) -> +1 sase-1jj; plugin_latest editable-install test failure (found by this landing) -> new task sase-1jt. DECLINED: node_finder ImportError (.7 #3; fixed by 77ad508a6c), monitor proc facade crash test (.9 #2; passes now), ArtifactIndexProjection (.6 #1; no longer flagged), other early-phase pre-existing failures (.1 #3, .2 #3-6, .3 #3, .4 #1, .5 #3: config schema, mutex groups, help sort, pypi flow, timezone guard, wire/marker audits; all pass now), 1h full-check timeout (.8 #3; informational, the check finishes in about 21m), global install refresh (.12 #3; global sase already reports an empty registry). Single loaded-lane failure of test_supervisor_sigterm_records_stop_intent_worker_settles_stop passed 3/3 in isolation and did not recur; not filed.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1jc.1](sase-1jc.1.md) | Make flag infrastructure tests independent of production flags | ✓ closed | medium | 2026-10-09 | 1 | 1 |
| [sase-1jc.10](sase-1jc.10.md) | Stabilize provider instruction and execution channels | ✓ closed | medium | 2026-10-09 | 1 | 1 |
| [sase-1jc.11](sase-1jc.11.md) | Stabilize sudo requests, provider drains, and autonomy records | ✓ closed | medium | 2026-10-09 | 1 | 1 |
| [sase-1jc.12](sase-1jc.12.md) | Verify the empty registry and complete retirement cleanup | ✓ closed | medium | 2026-10-09 | 1 | 2 |
| [sase-1jc.2](sase-1jc.2.md) | Make typed Agent and Proc launches unconditional | ✓ closed | medium | 2026-10-09 | 1 | 2 |
| [sase-1jc.3](sase-1jc.3.md) | Make queue capacity budgets unconditional | ✓ closed | medium | 2026-10-09 | 1 | 2 |
| [sase-1jc.4](sase-1jc.4.md) | Stabilize macro aliases and strict input types | ✓ closed | medium | 2026-10-09 | 1 | 2 |
| [sase-1jc.5](sase-1jc.5.md) | Stabilize agent-session and turn compatibility aliases | ✓ closed | medium | 2026-10-09 | 1 | 1 |
| [sase-1jc.6](sase-1jc.6.md) | Remove the legacy live Agents query implementation | ✓ closed | medium | 2026-10-09 | 1 | 1 |
| [sase-1jc.7](sase-1jc.7.md) | Stabilize refresh tokens, refresh gestures, and the Flags pane | ✓ closed | medium | 2026-10-09 | 1 | 1 |
| [sase-1jc.8](sase-1jc.8.md) | Stabilize publication formats and service contracts | ✓ closed | medium | 2026-10-09 | 1 | 3 |
| [sase-1jc.9](sase-1jc.9.md) | Remove legacy monitor-start rollout paths | ✓ closed | medium | 2026-10-09 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1jc: Retire every current feature flag while preserving enabled behavior [closed]"]
    n1["sase-1jc.1: Make flag infrastructure tests independent of production flags [closed]"]
    n2["sase-1jc.10: Stabilize provider instruction and execution channels [closed]"]
    n3["sase-1jc.11: Stabilize sudo requests, provider drains, and autonomy records [closed]"]
    n4["sase-1jc.12: Verify the empty registry and complete retirement cleanup [closed]"]
    n5["sase-1jc.2: Make typed Agent and Proc launches unconditional [closed]"]
    n6["sase-1jc.3: Make queue capacity budgets unconditional [closed]"]
    n7["sase-1jc.4: Stabilize macro aliases and strict input types [closed]"]
    n8["sase-1jc.5: Stabilize agent-session and turn compatibility aliases [closed]"]
    n9["sase-1jc.6: Remove the legacy live Agents query implementation [closed]"]
    n10["sase-1jc.7: Stabilize refresh tokens, refresh gestures, and the Flags pane [closed]"]
    n11["sase-1jc.8: Stabilize publication formats and service contracts [closed]"]
    n12["sase-1jc.9: Remove legacy monitor-start rollout paths [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n0 --> n9
    n0 --> n10
    n0 --> n11
    n0 --> n12
    n1 -.-> n5
    n2 -.-> n3
    n3 -.-> n4
    n5 -.-> n6
    n6 -.-> n7
    n7 -.-> n8
    n8 -.-> n9
    n9 -.-> n10
    n10 -.-> n11
    n11 -.-> n12
    n12 -.-> n2
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jc.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jc.1.md) | [sase-1jc.1](sase-1jc.1.md) | 1 |
| [bbugyi200.athena.sase-1jc.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.10/README.md) | [sase-1jc.10](sase-1jc.10.md) | 1 |
| [bbugyi200.athena.sase-1jc.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.11/README.md) | [sase-1jc.11](sase-1jc.11.md) | 1 |
| [bbugyi200.athena.sase-1jc.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.12/README.md) | [sase-1jc.12](sase-1jc.12.md) | 2 |
| [bbugyi200.athena.sase-1jc.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jc.2.md) | [sase-1jc.2](sase-1jc.2.md) | 2 |
| [bbugyi200.athena.sase-1jc.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.3/README.md) | [sase-1jc.3](sase-1jc.3.md) | 2 |
| [bbugyi200.athena.sase-1jc.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.4/README.md) | [sase-1jc.4](sase-1jc.4.md) | 2 |
| [bbugyi200.athena.sase-1jc.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.5/README.md) | [sase-1jc.5](sase-1jc.5.md) | 1 |
| [bbugyi200.athena.sase-1jc.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.6/README.md) | [sase-1jc.6](sase-1jc.6.md) | 1 |
| [bbugyi200.athena.sase-1jc.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jc.7.md) | [sase-1jc.7](sase-1jc.7.md) | 1 |
| [bbugyi200.athena.sase-1jc.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jc.8.md) | [sase-1jc.8](sase-1jc.8.md) | 3 |
| [bbugyi200.athena.sase-1jc.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.9/README.md) | [sase-1jc.9](sase-1jc.9.md) | 1 |
| [bbugyi200.athena.sase-1jc.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.land/README.md) | [sase-1jc](README.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8519047`](https://github.com/sase-org/sase/commit/851904725dd6a0151c2457dd083a25e41f2e1880) | test(flags): make flag infrastructure tests independent of production flags | [sase-1jc.1](sase-1jc.1.md) | 2026-10-09 23:32:35 EDT |
| sase-core | [`sase-core@e42eb5c`](https://github.com/sase-org/sase-core/commit/e42eb5cab5442eaa36eb3850c06277ad90ba86ea) | feat(launch): retire typed launch-units opt-in; unconditional typed diagnostics | [sase-1jc.2](sase-1jc.2.md) | 2026-10-10 02:45:23 EDT |
| sase | [`7b01179`](https://github.com/sase-org/sase/commit/7b01179be9e56529a6440018581488e3752ceb62) | feat(flags): retire typed\_launch\_units; typed agent and proc launches unconditional | [sase-1jc.2](sase-1jc.2.md) | 2026-10-10 02:49:42 EDT |
| sase-core | [`sase-core@c24b650`](https://github.com/sase-org/sase-core/commit/c24b6500d5336de7a7b21b370f37cb85cdb315e1) | feat(launch): retire queue\_capacity\_budget opt-out; unconditional capacity budgets | [sase-1jc.3](sase-1jc.3.md) | 2026-10-10 04:20:58 EDT |
| sase | [`b816732`](https://github.com/sase-org/sase/commit/b81673283a8ff921652a2370f8a6d6f7b55865f8) | feat(flags): retire queue\_capacity\_budget; queue capacity budgets unconditional | [sase-1jc.3](sase-1jc.3.md) | 2026-10-10 04:25:18 EDT |
| sase-core | [`sase-core@e3b0907`](https://github.com/sase-org/sase-core/commit/e3b0907b8d3eafcd3d673b5af0c071d6a9f8370c) | feat(macros): retire legacy-xprompt opt-out; unconditional alias acceptance | [sase-1jc.4](sase-1jc.4.md) | 2026-10-10 06:23:12 EDT |
| sase | [`8a2f344`](https://github.com/sase-org/sase/commit/8a2f344626143a97b29d63d202d3537ac7860587) | feat(flags): retire legacy\_xprompt\_syntax and strict\_macro\_input\_types; macro aliases and strict input types unconditional | [sase-1jc.4](sase-1jc.4.md) | 2026-10-10 06:27:37 EDT |
| sase | [`2f5070d`](https://github.com/sase-org/sase/commit/2f5070d1291c8110b4d9b910cf353d1a47e4b2de) | feat(flags): retire legacy\_agent\_family\_syntax and legacy\_sase\_shell\_syntax; agent-session and turn aliases unconditional | [sase-1jc.5](sase-1jc.5.md) | 2026-10-10 07:32:01 EDT |
| sase | [`b46ecb0`](https://github.com/sase-org/sase/commit/b46ecb0a947539855d69034bd4d1300b999274af) | feat(agents): retire agents\_unified\_query flag, unify live query path | [sase-1jc.6](sase-1jc.6.md) | 2026-10-10 08:26:04 EDT |
| sase | [`3513d91`](https://github.com/sase-org/sase/commit/3513d91b1fbce9f216655ffb50d471bd62de1041) | feat(flags): retire refresh tokens, refresh gestures, and Flags pane flags | [sase-1jc.7](sase-1jc.7.md) | 2026-10-10 09:32:53 EDT |
| sase-core | [`sase-core@9573108`](https://github.com/sase-org/sase-core/commit/9573108dac5dbb5223c05d3c4c1c2f0613b8b2c9) | feat(config): retire legacy axe/config wires in sase-core for publication-services flags | [sase-1jc.8](sase-1jc.8.md) | 2026-10-10 12:09:40 EDT |
| sase | [`b144f62`](https://github.com/sase-org/sase/commit/b144f622cf49a261acece2045008f025bb194c52) | feat(flags): retire publication-services flags slim\_agents\_manifest, agents\_session\_manifest\_compat, bgcmd\_legacy\_slots, axe\_routine\_job\_contract | [sase-1jc.8](sase-1jc.8.md) | 2026-10-10 12:59:12 EDT |
| sase | [`8fdf12a`](https://github.com/sase-org/sase/commit/8fdf12a8a8d43fdbdc100018a881c473485c98e7) | fix(query\_profile): define \_\_dir\_\_ and PEP 562 hooks in profiles package init | [sase-1jc.8](sase-1jc.8.md) | 2026-10-10 14:02:44 EDT |
| sase | [`1136a35`](https://github.com/sase-org/sase/commit/1136a35db29be9ba397d3fe12e7ceed7c04f0f40) | feat(monitors): retire monitor\_continuation\_records flag | [sase-1jc.9](sase-1jc.9.md) | 2026-10-10 14:54:32 EDT |
| sase | [`2c9f761`](https://github.com/sase-org/sase/commit/2c9f76121008a07b7c8be248ebbddae983f45b1c) | feat(providers): retire provider-instructions sunset flags | [sase-1jc.10](sase-1jc.10.md) | 2026-10-10 16:17:29 EDT |
| sase | [`5235b17`](https://github.com/sase-org/sase/commit/5235b172744fdccc4a529945528f71a17ef89292) | feat(flags): retire runtime-controls flags agent\_sudo\_requests, provider\_drain, autonomy\_record\_only | [sase-1jc.11](sase-1jc.11.md) | 2026-10-10 17:00:43 EDT |
| sase-core | [`sase-core@6a12a4f`](https://github.com/sase-org/sase-core/commit/6a12a4f6bcbe432475c6e6bc97af940a930e2356) | docs(core): remove stale flag-removal leftover line | [sase-1jc.12](sase-1jc.12.md) | 2026-10-10 18:16:54 EDT |
| sase | [`77ad508`](https://github.com/sase-org/sase/commit/77ad508a6c815afa016e81f5c56f0e23228e8adf) | chore(flags): remove retired flag leftovers and verify empty registry | [sase-1jc.12](sase-1jc.12.md) | 2026-10-10 18:23:00 EDT |
| sase | [`9f1eb31`](https://github.com/sase-org/sase/commit/9f1eb315e30881052a9e29ca70f6da9af41189ba) | chore(flags): land sase-1jc retirement leftovers and integration fixes | [sase-1jc](README.md) | 2026-10-10 20:37:37 EDT |
| sase-nvim | [`sase-nvim@b0b48f4`](https://github.com/sase-org/sase-nvim/commit/b0b48f43e63c6be6c2d117d2c8cbe1f815176df9) | docs: describe retired xprompt aliases as permanently accepted | [sase-1jc](README.md) | 2026-10-10 20:42:20 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:0ze--code][1] | See if concurrent flag-retirement epic already owns the closed-flag lint failure | 1 |
| read-by | [agent:6h--1][2] | Concurrent epic closed flag beads that are failing this workspace just check | 1 |
| read-by | [agent:sase-1j6.10.7][3] | Need whether sase-1jc owns closed flag bead leftovers | 1 |
| read-by | [agent:sase-1j6.10.land--1][4] | check flag retirement epic status vs sase-102 close | 1 |
| read-by | [agent:sase-1jc.10][5] | need epic context and decisions for phase 10 | 1 |
| read-by | [agent:sase-1jc.12][6] | Need epic status and ledger context for clean-slate phase | 2 |
| read-by | [agent:sase-1jc.4][7] | epic context for phase | 1 |
| read-by | [agent:sase-1jc.6][8] | epic context for phase sase-1jc.6 | 1 |
| read-by | [agent:sase-1jc.land][9] | Confirm the closed epic has no parent_bead before finishing | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ze.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.6h.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.10.7/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1j6.10.land.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.10/README.md
[6]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.12/README.md
[7]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.4/README.md
[8]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.6/README.md
[9]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.land/README.md

<!-- sase:referenced-by:end -->
