# Bead: sase-nb.11 — Finish the feature-flag epic's landing

[Bead Pages](../README.md) / [sase-nb](README.md) / sase-nb.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-nb.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-nb.land.md) · **Assignee:** `sase-nb.11.land`
**Created:** 2026-08-16 21:04:24 EDT · **Closed:** 2026-08-16 22:13:21 EDT
**Plan:** [202608/feature\_flags\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/feature_flags_landing.md)

## Description

The feature-flag teaching notes are project-local hand-written files instead of generated ones shipped into every SASE project, `just check-full`'s blocking global-leak gate is green, the Artifacts Beads PNG goldens match the flag-bead chrome that shipped, the FlagTriage response translator is directly tested at its trust boundary, and `sase flag new` reports the bead id it actually committed.

## Notes

[2026-08-17T01:41:00Z · sase-ns.6.2] DISCOVERED ISSUE: During unrelated Config Center atomic-save deflake verification on 2026-08-16, just check failed at SASE validation before tests because .venv/bin/sase validate reports init memory --check wants ~/.local/share/chezmoi/home/sase/memory/README.md regenerated (+3/-2) to add sase/memory/sase_flags.md feature-flag guidance. On the same tree, global 'sase init memory --check --diff' disagrees and wants to remove the Feature Flags section from this project's generated sase/memory/sase.md plus AGENTS.md/CLAUDE.md/GEMINI.md/QWEN.md/OPENCODE.md. I did not run memory init because this task has no owner approval for memory-file edits. Corroborated closed duplicate task sase-n0 with verified-after-close evidence; recording here too because the active epic explicitly owns making feature-flag memory project-local.

[2026-08-17T02:13:21Z · sase-nb.11.land] LANDED. Verified all five phases against the source and the epic's five commits (8873e64c4, d5443be38, f4cbb138e, 0a5074df7, dd79cf142) on HEAD 6000a54a1.

PHASE VERIFICATION
- 11.1 memory: templates/memory-sase-flags.template.md is gone, root_rendering.py and project_deploy.py have no flags references, the Feature Flags block is out of memory-sase.template.md, docs/memory.md now says two generated long notes, and sase/memory/feature_flags.md is a hand-written type:short Tier 1 note. Verified: 89 init-memory tests pass; 'sase memory list' shows feature_flags.md loaded in Tier 1 and sase_flags.md referenced in Tier 2 with its hook; '.venv/bin/sase memory init --check' and global 'sase init memory --check --diff' both exit 0; '.venv/bin/sase validate' is green on all five gates.
- 11.2 leak: the autouse monkeypatch.syspath_prepend fixture is in tests/test_check_feature_flags_tool.py. Verified: pytest -p tests._global_state_leak_detector --sase-detect-global-leaks --sase-fail-on-global-leaks on that file now reports '0 poisoning change(s) across 0 test(s)' (was 25), 26 passed; '.venv/bin/python tools/check_feature_flags' still runs standalone, exit 0.
- 11.3 goldens: all three artifacts_beads PNGs (empty, populated, reopened_detail) were regenerated in 0a5074df7. Verified: the three visual snapshot tests pass (-n 0 -m visual, 3 passed).
- 11.4 translate: tests/test_bead/test_flag_gate_response.py drives translate_flag_triage_response directly through flag_triage_spec(), covering all four actions, trusted identity/current thresholds vs a contradicting response, non-flag bundles, malformed selections/results, feedback requirements, missing remove winner, missing extend thresholds, and malformed persisted payloads. Verified: 19 passed; coverage over src/sase/bead/_flag_gate_response.py is 96% (82 stmts, 2 missed) against the 22% the plan recorded.
- 11.5 newid: create_flag_bead now returns _committed_flag_issue(), which re-reads the flag bead by key after bead_store_mutation commits and raises FeatureFlagError if it vanished. Verified: tests/feature_flags/test_cli.py forces BeadProject.create to return a stale id and asserts the printed line, the scaffold bead= value and the returned Issue all name the committed id, plus a test that a missing re-read raises. The commit message still names the pre-remint allocation; that limitation is recorded on the bead and in the commit body rather than left silently wrong.

INTEGRATION (step 2): five non-epic commits landed after the epic's first commit 8873e64c4 (aabbd245b, 4d8d24eef, d9b2984a7, 0c8646263, 6000a54a1). Their changed-file set and the epic's are disjoint - zero overlap. Semantically nothing to rewire either: 0c8646263 touches the artifacts_files golden, not artifacts_beads; 6000a54a1's new '# fixed-at:' flake-baseline retirement has no epic node to retire (no test_check_feature_flags_tool node has ever been in the baseline); 4d8d24eef's bead work-claim cleanup and d9b2984a7's Config Center hook do not reach feature flags. Nothing to change.

FOLLOW-UP TRIAGE (every PROPOSED FOLLOW-UP on the children)
- 11.1 'retire leftover generated sase_flags.md copies': DECLINED, verified moot. Checked every registered project - actstat and bob-cli via 'sase repo open' (neither has sase/memory/sase_flags.md nor a Feature Flags section in AGENTS.md), ~/sase/memory/ (no sase_flags.md), and this repo. Global 'sase init memory --check --diff' exits 0. The generated form only existed between 14d61561f and f4cbb138e and never reached another project, so there is nothing to retire.
- 11.4 + 11.5 'home memory README drift blocking SASE validation' (also the sase-ns.6.2 DISCOVERED ISSUE note on this bead): RESOLVED, no task. '.venv/bin/sase validate' passes 'init memory --check' and global 'sase init memory --check --diff' exits 0 on this tree; ~/sase/memory/README.md carries no sase_flags entry. Only an unrelated deferred provider-skill redeploy warning remains.
- 11.4 'coverage-instrumented pytest YAML loader failure': DECLINED, not a defect in any lane. It reproduces only when --cov is handed a dotted module path that is not a package ('--cov=sase.bead._flag_gate_response'). '--cov=src/sase' (what CI's just test-cov uses via tools/run_pytest), '--cov=src/sase/bead/_flag_gate_response.py', '--cov=sase.bead', and 'coverage run --source=src/sase/bead -m pytest' all pass 19/19. No lane uses the failing form.
- 11.4 'flaky test_prompt_artifact_file_cache::test_repeat_select_caches_content_read': FILED as task sase-o1 (ready, small) via /sase_new_task. Not a duplicate of any existing bead; root-caused to the test patching process-wide builtins.open and asserting an exact open count, with the durable selection-store failure record cited.

GATE: 'just check' is green on HEAD 6000a54a1 - every lint gate, SASE validation, committed plans, and the scoped test lane (41 of 2802 files).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-nb.11.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-nb.11.land/README.md) | [sase-nb.11](sase-nb.11.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ec2cc19`](https://github.com/sase-org/sase/commit/ec2cc1912cd2fe1b14ab687dadade137b9a34f18) | refactor(flags): retire the sase-nb epic-symbol whitelist | [sase-nb.11](sase-nb.11.md) | 2026-08-16 22:36:25 EDT |
