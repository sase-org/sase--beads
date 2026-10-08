# Bead: sase-1h7 — %wait(..., for\_epic=): a wait that follows its agent into the epic it launches

[Bead Pages](../README.md) / sase-1h7

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3v.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3v.linker.w0.md) · **Assignee:** `sase-1h7.land`
**Created:** 2026-10-06 18:17:32 EDT · **Closed:** 2026-10-08 01:22:44 EDT
**Plan:** [202610/wait\_for\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202610/wait_for_epic.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/wait_for_epic.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | [bead:sase-1hw][2] | Epic that added the %wait for_epic follow semantics this CLI flag would mirror |

_Plus 5 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/wait_for_epic.md
[2]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1hw/README.md

<!-- sase:links:end -->

## Description

`%wait:planner` waits for the planner and then for every epic bead the planner (or any member of its session, clan, workflow, or bound tribe) launches, so users can submit follow-up prompts before the epic's ID exists. A per-occurrence `for_epic=true|false` keyword controls the behavior. It defaults to true for user-authored agent targets, and using it without an agent target is a hard error in the launcher and the editor. The hand-off is recorded reliably, never deadlocks the epic machinery, and is clearly visible in the TUI as a teal `↪` hand-off.

## Notes

[2026-10-07T13:25:40Z · sase-1h9.land] DISCOVERED ISSUE: Wait-arg completion now inserts for_epic= ahead of hood=, and three sase tests still expect the old keyword list. Reproduced 2026-10-07 on sase master 5230c3080e during sase-1h9 landing (not caused by that epic; its diff does not touch completion). Isolated pytest:

tests/ace/tui/widgets/test_directive_arg_completion.py::test_wait_arg_completion_excludes_selected_keywords_case_insensitively
tests/ace/tui/widgets/test_wait_directive_completion_interactions.py::test_wait_arg_completion_excludes_selected_agent_and_groups
tests/test_macro_directive_completion_parity.py::test_failure_degradation_retains_static_directive_rows

Each fails at index 2 with for_epic= != hood=. The actual rows are the expected list plus an inserted for_epic= (hood= is still present). Rows come from core_candidate_rows in src/sase/ace/tui/widgets/directive_completion.py. Proposed by sase-1h9.1 note #1 and sase-1h9.2 note #1 (the latter named KNOWN witness 477276a723e911ef2ce08d5f4e412d7f). No task filed; this vocabulary belongs to sase-1h7.

[2026-10-08T01:55:04Z · sase-1hf.land] DISCOVERED ISSUE (sase-1hf landing, master 3a4178b15a, 2026-10-07):

(1) tests/test_timezone_display_guard.py::test_no_system_clock_display_sites fails deterministically (AST scan). Two new violations come from 0a80039618 (SASE_BEAD sase-1h7.8): src/sase/ace/tui/models/agent.py:371 `moment = datetime.fromtimestamp(float(view.since))` and src/sase/ace/tui/widgets/prompt_panel/_agent_wait_section.py:137 `datetime.fromtimestamp(float(since)).strftime("%H:%M")`. Route both through sase.core.time. This is distinct from task sase-1bp, whose update-gear sites no longer appear.

(2) Symvision's private-symbol rule returns before the unused-public rule. Once the sase-1hf land agent deleted the dead `_list_bead_state_changes_silent`, `just symvision` reported these sase-1h7 unused public symbols, previously masked: CreatedEpic and coerce_created_epics (src/sase/core/created_epics.py, sase-1h7.1); EpicFollowInput, EpicFollowMemberFacts, EpicFollowTargetFacts (wait_dependency_resolution/_epic_follow.py, sase-1h7.4); EpicFollowProgress, followed_epic_ids, read_epic_follow_progress (ace/tui/models/agent_epic_follow_progress.py) and epic_follow_toast_messages (ace/tui/actions/agents/_epic_follow_toasts.py) from sase-1h7.8; is_follow_plan_row (core/wait_epic_follow_view.py, sase-1h7.9). Also initial_dependencies_resolved (src/sase/axe/run_agent_wait_deps.py): 333034a60a (sase-1h7.5) replaced its last src caller with resolve_initial_wait_release, so only tests (~45 refs in 6 files) still call it. Retarget them to resolve_initial_wait_release(...).releasable and delete the wrapper. Privatize, wire, or delete per the symvision memory, or add --epic-symbol rows keyed to sase-1h7.10 if it will consume them.

(3) FYI, sase-1h7.10 note #3: test_land_failure_entry_clears_when_waiter_releases was caused by sase-1hf.3's release-telemetry ready.json payload (released_by). The sase-1hf landing fixes it by updating the assertion, so no sase-1h7 work is needed.

[2026-10-08T02:00:53Z · sase-1hi.1.1.land] DISCOVERED ISSUE: Triaged sase-1hi.1.1 child proposals .1 note #1, .2 note #1, .3 note #1, and .4 note #1. They report the same two clean-base failures in sase-core: editor::directive::tests::contract_covers_the_audited_directive_matrix and editor_completion::tests::surfaces::directive_contract_and_completion_bindings_return_plain_json_shapes. At current core 9ea87c11, both assert wait keywords [agent, bead, hood, proc, time, unit], while metadata and candidate tests contain [agent, bead, for_epic, hood, proc, time, unit]. git show 21c539fd proves sase-1h7.3 added FOR_EPIC_SUGGESTIONS and the WAIT_KEYWORDS entry without updating these two expectations. The four decision phases independently reproduced this on clean bases, including c089cf17 and df735e42. No task duplicate found in CI-specific/all-type searches or last-week sweeps. This is causally owned by still-open sase-1h7, consistent with its existing completion-drift note; no task created. Correct the audited expectations while preserving the for_epic behavior.

[2026-10-08T05:22:44Z · sase-1h7.land] LANDED (sase-1h7.land, sase master 1964a5f01f + landing diff, sase-core def5ad5b + landing diff, 2026-10-08).

VERIFIED: all 10 phases closed. Read every child note, the plan contract, and all 10 epic commits (997b9e26ff d58a45a75f 313aa2c993 7c5fa40d11 333034a60a 6e2bc57726 7a3e3882c9 0a80039618 5a3f8ae574 c7190fb99a; sase-core 436dba6c f4be6cee 21c539fd 4b4a0527 d742e207 9ea87c11). The pin sase-core-revision.txt 9ea87c11 already contains every sase-core change sase calls. The epic's suites (about 390 tests) pass. Telegram parity is committed in sase-telegram (agent_format.py epic_follows).

EPIC-CAUSED FIXES IN THIS LANDING:
(1) Timezone guard (epic note #2.1): ↪EPIC milestones and the lane's since HH:MM now go through sase.core.time parse_local/to_local.
(2) Masked symvision unused-public symbols (epic note #2.2), all resolved:
    - privatized CreatedEpic/coerce_created_epics, EpicFollowMemberFacts/TargetFacts, EpicFollowProgress/followed_epic_ids/read_epic_follow_progress, epic_follow_toast_messages, is_follow_plan_row;
    - deleted the dead EpicFollowInput and the test-only initial_dependencies_resolved wrapper (23 test call sites moved to resolve_initial_wait_release(...).releasable, its 2 dead telemetry tests removed; startup releases intentionally carry no satisfied_at per the sase-1hf plan).
    No --epic-symbol rows existed.
(3) sase-core stale wait-keyword expectations (epic note #3, sase-1h7.5 #9, sase-1h7.10 #4): fixed editor::directive contract_covers_the_audited_directive_matrix and sase_core_py directive_contract_and_completion_bindings_return_plain_json_shapes. Also fixed sase_macro_lsp wait_completion_uses_kind_aware_agent_catalog, whose index-based assertions 21c539fd never shifted after inserting for_epic=.
(4) Flip (c7190fb99a) left 30 sase tests stale:
    - 21 wait-lane tests now expect the spec'd ' · agent only' tag for unarmed targets;
    - 9 bead work rendering tests now expect %w(<ids>, for_epic=false).
(5) TUI import budget: the epic added 4 startup modules. wait_dependency_resolution now exports _epic_follow_release lazily (PEP 562), which had been lost with sase-1h7.5's dropped commit, and created_epics / agent_epic_follow_progress are imported lazily: 3579 -> 3573. The remaining overrun is other commits' growth, corroborated on sase-13p.

INTEGRATION:
sase-1hf.4 (68a4e89ac4) made wait_checks skip dead waiters, which stranded the epic-follow blocker notifications from sase-1h7.7. A dead runner's follow entries are now reconciled at end of tick, using the follow stage already mirrored in agent_meta.json (no extra read). Added a regression test; docs/axe.md updated. Rebased over the sase-1hf landing (c3f9d2915c), keeping its renames and our wrapper deletion. Reviewed the other concurrent commits with no changes needed: 91e6c64572 supersession (land-failed check inherits it via terminal_blocking_artifacts_for_name), 4cbfe00d97 atomic ready.json, sase-1hf.5 routine split, the bead read model, and launch provenance.

CHECKS:
- sase just check (full-suite escalation): 53383 passed. 13 failures, none sase-1h7: 11 KNOWN owned elsewhere (sase-1h8 bead_fast_path/claimed_status; sase-1hi provenance tests and plan_validate; sase-1hr; sase-1hs; sase-13p) plus 2 NEW (sase-1g2 deterministic, sase-1hx flake).
- symvision: 51 KNOWN, none sase-1h7 (sase-1hp and others).
- sase-core: fmt-check and clippy clean, all crates pass except bead_read_parity (sase-1h8, noted) and the sase-15h ETXTBSY flake.

FOLLOW-UP TRIAGE:
- Created sase-1hu (memory, %wait row; 1h7.10 #1), sase-1hv (memory, uv run clobbers the local wheel; 1h7.4 #5), sase-1hw (feature, agent wait --for-epic; 1h7.10 #2), sase-1hx (flake, terminate_processes; 1h7.9 #3).
- +1: sase-13p (import budget; 1h7.5 #1/#4/#10, 1h7.9 #3), sase-1hs (discard guard; 1h7.5 #10, 1h7.9 #3), sase-1f0 (peak RSS; 1h7.3 #5), sase-1g2 (launch bar; 1h7.9 #3), sase-1a0 (persist_monitor; 1h7.3 #5), sase-1br (block_spread; 1h7.3 #6, 1h7.9 #3), sase-1e4 (shift_tab; 1h7.9 #3), sase-15h (gateway runner ETXTBSY).
- DISCOVERED ISSUE noted on sase-1h8 (sase-core bead_read_parity).

DECLINED:
- _runs symvision (1h7.1 #1, .2 #1, .3 #1, .5 #5, .6 #1, .7 #3, .9 #1): gone at HEAD, tracked by sase-1h6.
- sase-core rustfmt drift (1h7.2 #2, .4 #3, .5 #2/#6): fmt-check clean at def5ad5b.
- Wire trailing-field test (1h7.3 #4): fixed in sase-1h7.5.
- Stale completion rows (1h7.3 #3, epic note #1): fixed by 95806cf189.
- dismiss-launching test (1h7.7 #1): passes since sase-core d742e207.
- stale-membership test (1h7.4 #1): passes in the full suite.
- init-repo README drift (1h7.6 #2, .7 #2, .8 #1, .9 #2): validate is green.
- committed-plans em-dash panic (1h7.10 #5): green at sase-core def5ad5b.
- _list_bead_state_changes_silent (1h7.10 #6) and land-failure released_by (1h7.10 #3): fixed by the sase-1hf landing.
- bead_fast_path/claimed_status (1h7.5 #10, .9 #3): already on sase-1h8 (sase-1h8.11 proposal, epic note #2).
- launch-provenance test breakage: already on sase-1hi.
- Single-sighting load flakes with no node ID or no reproduction in two full-lane runs, too thin to file: 1h7.4 #2 muse_usage_probe/mutation_completion_after_unmount; 1h7.9 #3 panel_shell_history/prompt_key_perf/agy_usage_probe; 1h7.3 #5 zsh completion pty.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1h7.1](sase-1h7.1.md) | Record the epics a run launched | ✓ closed | medium | 2026-10-06 | 1 | 2 |
| [sase-1h7.10](sase-1h7.10.md) | Flip the default on and finish the docs | ✓ closed | medium | 2026-10-06 | 1 | 2 |
| [sase-1h7.2](sase-1h7.2.md) | Derive produced-by links from recorded epics | ✓ closed | small | 2026-10-06 | 1 | 2 |
| [sase-1h7.3](sase-1h7.3.md) | Grammar, diagnostics, and persisted policy | ✓ closed | medium | 2026-10-06 | 1 | 2 |
| [sase-1h7.4](sase-1h7.4.md) | Epic-follow reducer and fact collector | ✓ closed | medium | 2026-10-06 | 1 | 2 |
| [sase-1h7.5](sase-1h7.5.md) | Follow through in every release path | ✓ closed | large | 2026-10-06 | 1 | 2 |
| [sase-1h7.6](sase-1h7.6.md) | Follow state in the agent model and shared view | ✓ closed | medium | 2026-10-06 | 1 | 1 |
| [sase-1h7.7](sase-1h7.7.md) | Blocker notifications and the cycle guard | ✓ closed | medium | 2026-10-06 | 1 | 1 |
| [sase-1h7.8](sase-1h7.8.md) | The ↪ hand-off in rows, lanes, toasts, and timeline | ✓ closed | medium | 2026-10-06 | 1 | 1 |
| [sase-1h7.9](sase-1h7.9.md) | Wait modal toggle, CLI, Jinja, and Telegram parity | ✓ closed | medium | 2026-10-06 | 1 | 2 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1h7: %wait(..., for_epic=): a wait that follows its agent into the epic it launches [closed]"]
    n1["sase-1h7.1: Record the epics a run launched [closed]"]
    n2["sase-1h7.10: Flip the default on and finish the docs [closed]"]
    n3["sase-1h7.2: Derive produced-by links from recorded epics [closed]"]
    n4["sase-1h7.3: Grammar, diagnostics, and persisted policy [closed]"]
    n5["sase-1h7.4: Epic-follow reducer and fact collector [closed]"]
    n6["sase-1h7.5: Follow through in every release path [closed]"]
    n7["sase-1h7.6: Follow state in the agent model and shared view [closed]"]
    n8["sase-1h7.7: Blocker notifications and the cycle guard [closed]"]
    n9["sase-1h7.8: The ↪ hand-off in rows, lanes, toasts, and timeline [closed]"]
    n10["sase-1h7.9: Wait modal toggle, CLI, Jinja, and Telegram parity [closed]"]
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
    n1 -.-> n3
    n1 -.-> n4
    n1 -.-> n5
    n3 -.-> n2
    n4 -.-> n6
    n5 -.-> n6
    n6 -.-> n7
    n6 -.-> n8
    n7 -.-> n9
    n7 -.-> n10
    n8 -.-> n2
    n9 -.-> n2
    n10 -.-> n2
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h7.1/README.md) | [sase-1h7.1](sase-1h7.1.md) | 2 |
| [bbugyi200.athena.sase-1h7.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h7.10.md) | [sase-1h7.10](sase-1h7.10.md) | 2 |
| [bbugyi200.athena.sase-1h7.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h7.2/README.md) | [sase-1h7.2](sase-1h7.2.md) | 2 |
| [bbugyi200.athena.sase-1h7.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h7.3.md) | [sase-1h7.3](sase-1h7.3.md) | 2 |
| [bbugyi200.athena.sase-1h7.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h7.4.md) | [sase-1h7.4](sase-1h7.4.md) | 2 |
| [bbugyi200.athena.sase-1h7.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h7.5.md) | [sase-1h7.5](sase-1h7.5.md) | 2 |
| [bbugyi200.athena.sase-1h7.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h7.6/README.md) | [sase-1h7.6](sase-1h7.6.md) | 1 |
| [bbugyi200.athena.sase-1h7.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h7.7.md) | [sase-1h7.7](sase-1h7.7.md) | 1 |
| [bbugyi200.athena.sase-1h7.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h7.8/README.md) | [sase-1h7.8](sase-1h7.8.md) | 1 |
| [bbugyi200.athena.sase-1h7.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h7.9/README.md) | [sase-1h7.9](sase-1h7.9.md) | 2 |
| [bbugyi200.athena.sase-1h7.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h7.land/README.md) | [sase-1h7](README.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@436dba6`](https://github.com/sase-org/sase-core/commit/436dba6c65670ff6bf4a9bbf5255ce411da4df1e) | feat(wire): add CreatedEpicWire to agent-meta wire | [sase-1h7.1](sase-1h7.1.md) | 2026-10-06 20:05:44 EDT |
| sase | [`997b9e2`](https://github.com/sase-org/sase/commit/997b9e26ff9b1315e0ab0c386f4ecf8e7052f454) | feat(record): track created epics via locked agent-meta updates | [sase-1h7.1](sase-1h7.1.md) | 2026-10-06 21:05:13 EDT |
| sase-core | [`sase-core@f4be6ce`](https://github.com/sase-org/sase-core/commit/f4be6cee136df4258e54af1ede98ac82e5a776a1) | feat(artifact-link): widen produced-by guidance to bead sources | [sase-1h7.2](sase-1h7.2.md) | 2026-10-06 21:55:25 EDT |
| sase | [`d58a45a`](https://github.com/sase-org/sase/commit/d58a45a75f58bddb5662a20bff206006b6f26508) | feat(artifact-links): publish created\_epic\_ids and project agent-created-epic links | [sase-1h7.2](sase-1h7.2.md) | 2026-10-06 22:00:53 EDT |
| sase-core | [`sase-core@21c539f`](https://github.com/sase-org/sase-core/commit/21c539fd30aff96530611f56903c5026e70ce3c3) | feat(wait): mirror wait\_for\_epics\_of in scan wires and editor grammar (sase-1h7.3) | [sase-1h7.3](sase-1h7.3.md) | 2026-10-06 22:35:05 EDT |
| sase-core | [`sase-core@4b4a052`](https://github.com/sase-org/sase-core/commit/4b4a0527c3c604b09dea759d3f6e3b4a23300e9e) | feat(wait): add pure wait\_epic\_follow reducer with Python binding (sase-1h7.4) | [sase-1h7.4](sase-1h7.4.md) | 2026-10-06 22:57:12 EDT |
| sase | [`313aa2c`](https://github.com/sase-org/sase/commit/313aa2c9930455835f3c29dd50ff2e279ea6a1f8) | feat(wait): add epic-follow reducer and fact collector (sase-1h7.4) | [sase-1h7.4](sase-1h7.4.md) | 2026-10-06 23:29:44 EDT |
| sase | [`7c5fa40`](https://github.com/sase-org/sase/commit/7c5fa40d11f61c94b1dc34981a21232d2d56f143) | feat(wait): accept and validate for\_epic= on %wait with persisted wait\_for\_epics\_of (sase-1h7.3) | [sase-1h7.3](sase-1h7.3.md) | 2026-10-07 09:21:06 EDT |
| sase-core | [`sase-core@d742e20`](https://github.com/sase-org/sase-core/commit/d742e207c697249c75dd42fac669d338e4bbed0b) | feat(wait): wire wait\_epic\_follows scan fields and dismissed-member reducer fix (sase-1h7.5) | [sase-1h7.5](sase-1h7.5.md) | 2026-10-07 15:38:14 EDT |
| sase | [`333034a`](https://github.com/sase-org/sase/commit/333034a60aa09d6279d508b4d39f0ab9707da912) | feat(wait): route every release path through shared epic-follow release (sase-1h7.5) | [sase-1h7.5](sase-1h7.5.md) | 2026-10-07 16:26:49 EDT |
| sase | [`6e2bc57`](https://github.com/sase-org/sase/commit/6e2bc577260805ecec2695b93697cd5bfe3f66ac) | feat(wait): add epic follow view for wait\_for\_epics\_of targets | [sase-1h7.6](sase-1h7.6.md) | 2026-10-07 17:04:08 EDT |
| sase | [`7a3e388`](https://github.com/sase-org/sase/commit/7a3e3882c9c1115622e4512a0c6069518f70c47d) | feat(axe): add chop wait epic-follow safety phase with blocker notifications and cycle guard | [sase-1h7.7](sase-1h7.7.md) | 2026-10-07 17:25:41 EDT |
| sase | [`0a80039`](https://github.com/sase-org/sase/commit/0a80039618ee8f2ca8d9bce6ec9d21b8f4c1c3b7) | feat(ace-tui): render epic-follow hand-off across agents surfaces | [sase-1h7.8](sase-1h7.8.md) | 2026-10-07 17:46:25 EDT |
| sase | [`5a3f8ae`](https://github.com/sase-org/sase/commit/5a3f8ae57447ed8ced231dc82e170e0834c9df3c) | feat(wait): tri-state Follow epics toggle with split for\_epic occurrences | [sase-1h7.9](sase-1h7.9.md) | 2026-10-07 19:38:28 EDT |
| sase-telegram | [`sase-telegram@15ccce3`](https://github.com/sase-org/sase-telegram/commit/15ccce3857d6802b2fe9a57e4e4d4df846dd4bf1) | feat(telegram): render wait follow suffixes on agent tokens | [sase-1h7.9](sase-1h7.9.md) | 2026-10-07 20:08:33 EDT |
| sase-core | [`sase-core@9ea87c1`](https://github.com/sase-org/sase-core/commit/9ea87c1181128ff87d2a90e74b782ffa369e30c3) | feat(wait): support wait-for-epic flip in plan resolution and directive metadata | [sase-1h7.10](sase-1h7.10.md) | 2026-10-07 21:51:53 EDT |
| sase | [`c7190fb`](https://github.com/sase-org/sase/commit/c7190fb99a93a71e66dee4f0576e5e67760c5050) | feat(wait): default WAIT\_FOR\_EPIC to true with for\_epic=false phase sequencing | [sase-1h7.10](sase-1h7.10.md) | 2026-10-07 21:57:40 EDT |
| sase-core | [`sase-core@ec92ecc`](https://github.com/sase-org/sase-core/commit/ec92ecce1688f85f15c4f989ee82b0537a95d925) | test(wait): expect the for\_epic keyword in directive contract and LSP completion tests | [sase-1h7](README.md) | 2026-10-08 01:25:24 EDT |
| sase | [`0968044`](https://github.com/sase-org/sase/commit/0968044154fd76abdb1e9b40bd2f15c986ba7e8a) | fix(wait): land sase-1h7 epic-follow integration, symvision, and stale-test cleanup | [sase-1h7](README.md) | 2026-10-08 01:30:32 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.3z.final][1] | Verify bead title/status before citing it in consolidated reading-list report | 1 |
| read-by | [agent:sase-1h7.2][2] | links phase: sample epic created_by shape | 1 |
| read-by | [agent:sase-1h7.land][3] | Need the parent link after closing | 2 |
| read-by | [agent:sase-1h9.land][4] | Need existing notes before recording for_epic completion drift | 3 |
| read-by | [agent:sase-1hf.land][5] | Check whether sase-1h7 already knows about the timezone guard failure | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3z.final/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h7.2/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h7.land/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h9.land/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1hf.land/README.md

<!-- sase:referenced-by:end -->
