# Bead: sase-18f — Return just check to green and remove its recurring failure causes

[Bead Pages](../README.md) / sase-18f

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0rh.md) · **Assignee:** `sase-18f.land`
**Created:** 2026-09-24 17:18:50 EDT · **Closed:** 2026-09-25 01:03:21 EDT
**Plan:** [202609/green\_just\_check.md](https://github.com/sase-org/sase--plans/blob/main/202609/green_just_check.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:f3e4b63c06d70e0a48574b14 | Wheel-cache source snapshot for the reproduced extensionless mypy failure |

_Plus 3 automatic references — see [Referenced By](#referenced-by)._

<!-- sase:links:end -->

## Description

A clean checkout of latest master passes `sase tool run check` and the full non-visual `just test` suite. The recurring causes found in the ToolRun ledger are removed: premature flag-bead closes, split-file agents that break symvision, stale `__pycache__`-only directories that fail pyscripts, and the uncached per-launch Rust LSP rebuild that pushes checks past agent command timeouts.

## Notes

[2026-09-24T21:40:34Z · sase-185.land] DISCOVERED ISSUE (from sase-185.1 PROPOSED FOLLOW-UP #1, re-verified by the sase-185 land agent at master c03c717da, clean tree): mypy 15 errors (10 attr-defined in ace/tui/widgets/_agent_detail_display.py/_agent_detail_state.py; 5 in ace/tui/command_line/input.py:159 and screen.py:1343-1362). test-waits: tests/ace/tui/command_line/test_completion_popup.py:181 fixed-sleep-missing-pragma. toobig: command_line/screen.py 1979 lines, widgets/decks/panel.py 1067 lines. symvision: once sase-185's own dead _dispatch_preview_source_summary is deleted (done in the sase-185 landing), it reports unused public command-line grammar/extras/signature/popup/restore/sources symbols, vim_search_controller helpers (invert_search_direction, offset_for_row, wrap_feedback_message), FileSourceLabel (file_panel/_file_list.py) and status_text (main/monitor_render.py, main/proc_render.py). Full just test lane: 41 deterministic clean-tree failures incl. tests/ace/tui/test_kill_and_edit_prompt_name.py x8 (TypeError: prepare_kill_and_edit_prompt() got an unexpected keyword argument 'family_name' - test not updated by 44ec3e62d sase-17m.4.1.3 rename; no task bead yet), test_config_schema, keymap help/defaults, LLM-calls panel, model completion panel titles, fakey test_cli help, test_launch_approval competing_family_successor, agent_jump_panel_visibility, test_prompt_file_completion ctrl_e, marker_mutation_audit, test_file_panel zoom cap, visual_fixture_host_paths, plus already-tracked sase-174/175/184/186/188/13p. ToolRun e9508bd2c3882f6b873a990f33deffcb.

[2026-09-25T01:20:35Z · sase-18i.land] DISCOVERED ISSUE (from sase-18i.2 PROPOSED FOLLOW-UP #1): On clean master 4858f20a2, sase tool run check 35b774a2ffcc7928d60f2561619d369f passes project mypy (4966 source files) then fails extensionless-tools mypy at unchanged tools/sase_core_wheel_cache:433 (_identity_lock annotated -> object, contextmanager requires Iterator) and :604 (acquired_lock needs type annotation). This reproduces the phase report on the current tree and is causally within sase-18f.9 final green-check scope; repair before claiming that phase passes. No separate task bead was created.

[2026-09-25T03:52:41Z · sase-17m.4.1.land] DISCOVERED ISSUE (from sase-17m.4.1.8 PROPOSED FOLLOW-UP #1, reverified by sase-17m.4.1.land at master bde335de5): sase tool run check 1e935a0fd75a9f458f284dad70cc5b40 passes source mypy (4967 files) but fails extensionless-tools mypy at tools/smoke_sase_core_rs_tool_runs:75, fingerprint lacking a type annotation [var-annotated]. This file was not changed by the agent-session epic. The still-open green-check epic owns the final clean-master gate. Phase sase-17m.4.1.8 also reported test_init_memory_committed_drift failure on clean HEAD; recheck that node after this mypy blocker is fixed. Earlier ACE mypy/symvision/toobig and clean-base test proposals from phases 1/2/3/4/5 were already included in this epic note #1 or covered by its child fixes.

[2026-09-25T03:54:49Z · sase-17m.4.1.land] CONFIRMED follow-up from sase-17m.4.1.8 note #1 at master bde335de5: targeted pytest tests/main/test_init_memory_committed_drift.py::test_repo_project_memory_notes_match_generator_output fails because plan_init_memory proposes 4 tools/*.md shim writes, with tools/CLAUDE.md first. The adjacent completion kind-coverage and cli_spec snapshot tests both pass. This is a clean-tree generator drift outside the session rename and remains in the green-check epic scope.

[2026-09-25T03:55:52Z · sase-17m.4.1.land] DISCOVERED ISSUE (from sase-17m.4.1.2 PROPOSED FOLLOW-UP #2): at clean master bde335de5, targeted tests/test_agent_restart_cli.py::test_wipe_failed_exits_1_and_prints_recovery_dir still fails. The recovery directory basename 20260818120000-02p is line-wrapped in stderr, so the contiguous substring assertion fails. The adjacent absent-store completion failure in that phase note is the exact duplicate of ready task sase-14o and was corroborated there. This restart test is outside the agent-session rename and belongs to the active green-check epic non-UI test scope.

[2026-09-25T05:03:21Z · sase-18f.land] LANDED by sase-18f.land at master ae34dba20 + landing diff. Final `sase tool run check` d6663eca1e6088a9ed6cea7c702c9829 SUCCEEDED (exit 0): fmt, every lint stage (ruff, mypy, feature flags, pyscripts, test waits, changelog, terminology, symvision), SASE validation, committed plans, and the test lane escalated to the full suite (Justfile rule) all green. The prior run 75a50498 on the same tree had 47233 passed / 2 load flakes (both pass 3/3 isolated, routed below).

VERIFIED (step 1): all 9 phases closed, every phase note reviewed, commits read: 4b3699f0d (.5 pyscripts cache-only dirs + regression test), fdc3e3caf (.6 flag-close guard), b2137e84c+c77912a38 (.7 split_file prompt, all required clauses; just _lint-toobig still exists after 951ff0a10), adebe400d (.8 LSP cache: lsp kind keyed by source identity/profile/triple/rustc -vV, per-identity flock with recheck and 15 min fallback, both wheel and LSP; 64 cache/Justfile tests pass), 114fbca89 (.1), b18f3d38f (.2), 55936f429 (.3), bf3aa6c8a (.4), 561e4b6dd (.9 stragglers). Epic-caused gap finished here: .6's guard used a regex, skipped the flag-type check, did not name the flag key/fix, and lacked docs and tests. It now parses the registry with ast, refuses only flag task beads, names each flag key plus the Off/On/registry fix, has unit tests (refusal, removal, other/closed/non-flag beads, comments ignored, missing registry) and a CLI handle_bead_close test (the finalizer -B close runs that CLI, and existing bead_hooks tests cover non-zero close as a failed close), and docs/beads.md documents it. LSP-cache timing: my five check runs spent 1.7-31.6s unattributed setup with no LSP rebuild. The multi-day ledger pass-rate comparison the plan asked for can only be measured after landing and was not done here.

INTEGRATED (step 2): fast-forwarded over a2ec65a1f/bde335de5/ae34dba20. Fixed sase-18j.5 (cdcbcdd9d) stragglers that kept master red: smoke tool mypy annotation; tools/tool_triage_backtest Rule 1 (new tests/test_tool_triage_backtest_tool.py); a comment line inside the continued _lint-symvision command that silently dropped every --epic-symbol argument (moved to the header); 5 symvision pragmas to the real tools/ consumer plus epic-symbol entries sase-18j(gather_owner_candidates|triage_knobs); regenerated tools/ provider shims (sase memory init). Recorded on sase-18j. Epic notes #3/#4 (17m.4.1.land) are fixed by this landing.

FOLLOW-UPS: .1#2 command_line keymaps inert -> declined, fixed upstream by bde335de5 (sase-17x.13.4). .1#3 env tests -> bead-store node +1 sase-14o; snippet add/delete path truncation (plus epic note #5 restart wrap) -> new sase-18v (ci, small). .2#1/.4#3 test_settlement.py 1048 lines -> declined: toobig left check in 951ff0a10 and the toobig_split routine owns splits. .2#2/.4#3 symvision survivors and stale 18i entries -> declined, fixed by 4fb83bb4f/561e4b6dd. .3#2/.4#4 dismissed-save audit -> declined, fixed by 1ea13da1b (sase-18d.5, additive add/remove APIs reviewed in the manifest; the audit passes). .3#3 provider_disable flake -> +1 sase-t7. .3#4 lifecycle_controls database-locked flake -> new sase-18t. .4#1/.4#2 wheel-cache mypy and test-wait pragma -> declined, fixed by 561e4b6dd. .4#5 production oracle flake -> +1 sase-10g; tmux socket File name too long (reproduced) -> new sase-18w (ci, small). .9#1 34 agent-session dialect failures -> declined: all pass after a2ec65a1f (sase-17m.4.1.8). New flakes: zsh sbd alias -> +1 sase-13a; config hub home digits WaitForScreenTimeout -> new sase-18u. Closed sase-180, sase-184, sase-186, sase-188 citing fixing commits. No --epic-symbol entries for sase-18f.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-18f.1](sase-18f.1.md) | Restore every lint gate except toobig on master | ✓ closed | medium | 2026-09-24 | 1 | 1 |
| [sase-18f.2](sase-18f.2.md) | Split the two oversized ACE modules | ✓ closed | medium | 2026-09-24 | 1 | 1 |
| [sase-18f.3](sase-18f.3.md) | Repair non-UI tests that fail on clean master | ✓ closed | medium | 2026-09-24 | 1 | 1 |
| [sase-18f.4](sase-18f.4.md) | Repair ACE TUI tests that fail on clean master | ✓ closed | medium | 2026-09-24 | 1 | 1 |
| [sase-18f.5](sase-18f.5.md) | Ignore cache-only script directories in the pyscripts lint | ✓ closed | xsmall | 2026-09-24 | 1 | 1 |
| [sase-18f.6](sase-18f.6.md) | Refuse closing a flag bead while its registry definition survives | ✓ closed | small | 2026-09-24 | 1 | 1 |
| [sase-18f.7](sase-18f.7.md) | Make the split\_file xprompt keep symvision and mypy green | ✓ closed | small | 2026-09-24 | 1 | 2 |
| [sase-18f.8](sase-18f.8.md) | Cache sase-xprompt-lsp builds and dedupe concurrent core builds | ✓ closed | medium | 2026-09-24 | 1 | 1 |
| [sase-18f.9](sase-18f.9.md) | Verify green check and full test suite on clean master | ✓ closed | small | 2026-09-24 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-18f: Return just check to green and remove its recurring failure causes [closed]"]
    n1["sase-18f.1: Restore every lint gate except toobig on master [closed]"]
    n2["sase-18f.2: Split the two oversized ACE modules [closed]"]
    n3["sase-18f.3: Repair non-UI tests that fail on clean master [closed]"]
    n4["sase-18f.4: Repair ACE TUI tests that fail on clean master [closed]"]
    n5["sase-18f.5: Ignore cache-only script directories in the pyscripts lint [closed]"]
    n6["sase-18f.6: Refuse closing a flag bead while its registry definition survives [closed]"]
    n7["sase-18f.7: Make the split_file xprompt keep symvision and mypy green [closed]"]
    n8["sase-18f.8: Cache sase-xprompt-lsp builds and dedupe concurrent core builds [closed]"]
    n9["sase-18f.9: Verify green check and full test suite on clean master [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n0 --> n9
    n1 -.-> n2
    n1 -.-> n3
    n1 -.-> n4
    n1 -.-> n9
    n2 -.-> n4
    n2 -.-> n9
    n3 -.-> n9
    n4 -.-> n9
    n5 -.-> n9
    n6 -.-> n9
    n7 -.-> n9
    n8 -.-> n9
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18f.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.1/README.md) | [sase-18f.1](sase-18f.1.md) | 1 |
| [bbugyi200.athena.sase-18f.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.2/README.md) | [sase-18f.2](sase-18f.2.md) | 1 |
| [bbugyi200.athena.sase-18f.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.3/README.md) | [sase-18f.3](sase-18f.3.md) | 1 |
| [bbugyi200.athena.sase-18f.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.4/README.md) | [sase-18f.4](sase-18f.4.md) | 1 |
| [bbugyi200.athena.sase-18f.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.5/README.md) | [sase-18f.5](sase-18f.5.md) | 1 |
| [bbugyi200.athena.sase-18f.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.6/README.md) | [sase-18f.6](sase-18f.6.md) | 1 |
| [bbugyi200.athena.sase-18f.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.7/README.md) | [sase-18f.7](sase-18f.7.md) | 2 |
| [bbugyi200.athena.sase-18f.8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-18f.8.md) | [sase-18f.8](sase-18f.8.md) | 1 |
| [bbugyi200.athena.sase-18f.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.9/README.md) | [sase-18f.9](sase-18f.9.md) | 1 |
| [bbugyi200.athena.sase-18f.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.land/README.md) | [sase-18f](README.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4b3699f`](https://github.com/sase-org/sase/commit/4b3699f0dc3242c723f498c654f643cec5f337d0) | fix: ignore cache-only script directories in pyscripts lint | [sase-18f.5](sase-18f.5.md) | 2026-09-24 18:03:38 EDT |
| sase | [`b2137e8`](https://github.com/sase-org/sase/commit/b2137e84c907c2c5bfe4a6055c64ba93abd216b1) | feat(xprompts): strengthen split-file constraints | [sase-18f.7](sase-18f.7.md) | 2026-09-24 18:13:01 EDT |
| sase | [`fdc3e3c`](https://github.com/sase-org/sase/commit/fdc3e3caf65d7d6a56ae0499dd11fac92efd8066) | feat(bead): refuse closing a flag bead while its registry definition survives | [sase-18f.6](sase-18f.6.md) | 2026-09-24 18:14:28 EDT |
| sase | [`114fbca`](https://github.com/sase-org/sase/commit/114fbca89a9430704d877982b4180a0425763e94) | fix(lint): restore every lint gate except toobig (sase-18f.1) | [sase-18f.1](sase-18f.1.md) | 2026-09-24 18:42:42 EDT |
| sase | [`c77912a`](https://github.com/sase-org/sase/commit/c77912a38cf508deb9dc75e1fd3864b0d738fe6f) | fix(tests): normalize whitespace in xprompt inline-code wrap assertions | [sase-18f.7](sase-18f.7.md) | 2026-09-24 19:04:43 EDT |
| sase | [`b18f3d3`](https://github.com/sase-org/sase/commit/b18f3d38f28a132de174cbf1e8ad3939e2b4372a) | refactor(ace): split oversized command and deck panels | [sase-18f.2](sase-18f.2.md) | 2026-09-24 19:45:37 EDT |
| sase | [`55936f4`](https://github.com/sase-org/sase/commit/55936f429e55d71d411a4c8cfffdb5e13fd64cab) | fix(sase-18f.3): resolve deterministic non-UI check failures | [sase-18f.3](sase-18f.3.md) | 2026-09-24 19:53:44 EDT |
| sase | [`adebe40`](https://github.com/sase-org/sase/commit/adebe400d76371385f420710df6608ec219e8aab) | feat(cache): cache xprompt lsp build artifacts | [sase-18f.8](sase-18f.8.md) | 2026-09-24 20:02:37 EDT |
| sase | [`bf3aa6c`](https://github.com/sase-org/sase/commit/bf3aa6c8a39da17fa12c29ef582194a117d9cb83) | fix(sase-18f.4): repair ACE TUI tests that fail on clean master | [sase-18f.4](sase-18f.4.md) | 2026-09-24 21:53:35 EDT |
| sase | [`561e4b6`](https://github.com/sase-org/sase/commit/561e4b6dd51549f0239dbe9a263d519974bb95b1) | fix(check): clear lint stragglers from concurrent landings | [sase-18f.9](sase-18f.9.md) | 2026-09-24 22:36:15 EDT |
| sase | [`c7a7890`](https://github.com/sase-org/sase/commit/c7a78904bbbb161391ecef6ba4f2eec85f604e95) | fix(check): land sase-18f green check and finish the flag-close guard | [sase-18f](README.md) | 2026-09-25 01:26:09 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.4.1.land][1] | Need active green-check epic scope before routing smoke mypy follow-up | 1 |
| read-by | [agent:sase-185.land][2] | Check whether the sase-185.1 master-red follow-up belongs to this epic | 1 |
| read-by | [agent:sase-18f.4][3] | Need epic notes listing the failing ACE UI tests | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.land/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-185.land/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.4/README.md

<!-- sase:referenced-by:end -->
