# Bead: sase-x7.3.1.5 — Deploy and verify the canonical fleet

[Bead Pages](../README.md) / [sase-x7.3.1](sase-x7.3.1.md) / sase-x7.3.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-x7.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-x7.3.md) · **Assignee:** `sase-x7.3.1.5` · **Size:** medium
**Created:** 2026-09-06 09:14:56 EDT · **Closed:** 2026-09-06 14:30:18 EDT
**Plan:** [202609/canonical\_producers.md](https://github.com/sase-org/sase--plans/blob/main/202609/canonical_producers.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | [bead:sase-xh][1] | Proposed by fleet-deploy note 4, with full-suite failure and isolated passing reruns |
| related | file:explicit:da42a703ffc6fda7becf6d62 | attached via sase artifact create --bead |
| related | file:explicit:f937c92641c01044fef763f8 | attached via sase artifact create --bead |

[1]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-xh/README.md

<!-- sase:links:end -->

## Description

fleet-deploy: apply exact landed revisions on all three hosts, reconcile Mac drift, exercise integrations, and certify the producer census.

## Notes

[2026-09-06T15:21:43Z · sase-x7.3.1.5] FLEET RECEIPT file:explicit:f937c92641c01044fef763f8 — chezmoi 32a05927 applied on athena/mac/apollo (verify OK); sase 58f16fe68, github 095181a, telegram 9cc66ab, nvim 84d55af, research babfb46, core 0.32.25. Doctor model_aliases OK x3; completions hashes match source with ~/ stamps; dest sase_changespecs pruned; Mac type:long sase_beads.md removed. Remaining: just check-full via monitor; restart long-lived nvim on athena/mac to drop old in-memory plugin.

[2026-09-06T15:22:04Z · sase-x7.3.1.5] PROPOSED FOLLOW-UP: Restart long-lived nvim on athena (embed pid ~1188569 editing chezmoi sase.yml) and mac (embed pid ~66734 editing ~/.ssh/config) so they load sase-nvim 84d55af; headless new instances already pass filetype/picker/schema smokes.

[2026-09-06T15:53:58Z · sase-x7.3.1.5--1] just check-full after fleet-deploy (this workspace, HEAD 58f16fe68): fmt+lint+SASE validation+committed-plans green; test-cost 1 failed / 38810 passed / 13 skipped in 18m. Failure is tests/ace/tui/widgets/test_prompt_todo_highlight.py::test_todo_background_yields_to_selection_search_yank_and_cursor (gw5). Later check-full gates did not run because test-cost failed. Unrelated to this phase (no TUI/widget changes in the fleet cutover). Bead left open pending a green check-full; see PROPOSED FOLLOW-UP.

[2026-09-06T15:54:30Z · sase-x7.3.1.5--1] PROPOSED FOLLOW-UP: Stabilize test_todo_background_yields_to_selection_search_yank_and_cursor under full-suite xdist — check-full failed once at the final cursor overlay assert (actual todo gold #ffd700 vs expected cursor #e0e0e0) after clearing yank/search and setting cursor_location=(0,0) with no pilot.pause(). Isolated rerun passed; 20/20 additional isolated reruns passed. Not in tests/reproducible_flake_baseline.txt. Likely stale render_line cache vs missing cursor restore analogous to _restore_todo_selection. Unrelated to fleet-deploy.

[2026-09-06T17:51:55Z · sase-x7.3.1.5] FLEET RECEIPT ADDENDUM file:explicit:da42a703ffc6fda7becf6d62 — plan step 6 resolved without restarting user sessions. Probed both long-lived nvim --embed instances over RPC: athena pid 1188569 (started 10:56:17, after the 10:54:37 plugin update) already had 84d55af in memory (_normalize_completion_backend -> picker, .sase -> sase_project_spec, .gp -> builtin gp, no syntax/sase_gp.vim on rtp, canonical yamlls globs). Mac pid 66734 (started Sep 5, plugin updated Sep 6 11:06) also had canonical modules loaded BUT its stored vim.lsp.config.yamlls retained the retired xprompts.schema.json => [**/xprompts.yml,**/xprompts.yaml] association from the pre-84d55af plugin/sase_yamlls.lua; deleted in place over RPC, stored map now identical to athena. No buffer/window/unsaved state touched; restart rejected because the mac session holds 19h of live ~/.ssh/config editing. Apollo has no long-lived editor process.

[2026-09-06T17:52:23Z · sase-x7.3.1.5] RE-CERTIFIED 2026-09-06 (2h after primary receipt), all three hosts: chezmoi source 32a05927; verify OK on athena/mac; apollo verify exits 1 on exactly ~/.codex/config.toml (hook trusted_hash + 100600->100664 mode) = the concurrent-Codex restore from the primary receipt, no SASE-owned file differs. sase skill init --check and sase memory init --check clean x3. sase completion list: bash/fish/zsh installed, chezmoi-owned, stamp 0.17.1, home-relative ~/ paths x3; generated specs have 0 hits for changespec/artifact-file/--changespec and 119/174/26 for patch, while sase changespec -h still dispatches. doctor -C config.model_aliases OK:1 WARN:0 ERROR:0 x3. Effective model aliases identical fleet-wide with pre-change precedence preserved (xsmall = codex/gpt-5.5@medium | grok/grok-4.6, the former xsmall_worker value); no *_worker key anywhere. sase config layers identical x3 with apollo sase_apollo.yml overlay still loaded and unchanged. sase xprompt show commit emits meta_patch from patch_name x3.

[2026-09-06T17:52:50Z · sase-x7.3.1.5] CENSUS: one new hit, classified not-a-producer. apollo:/home/bryan/.config/sase/sase.yml.bak-pass-fix (Sep 3 17:36, 12335B) still contains medium_worker/small_worker/xsmall_worker at lines 237-239. Inert: predates this epic, chezmoi reports "not managed", does not match any config discovery glob (sase.yml / sase_*.yml), sase config layers confirms it is not a loaded layer, and apollo doctor is clean. Left in place — deleting a user backup is not this phase scope.

[2026-09-06T17:53:11Z · sase-x7.3.1.5] PROPOSED FOLLOW-UP: Remove the stale apollo backup /home/bryan/.config/sase/sase.yml.bak-pass-fix (Sep 3, unmanaged, not a config layer) — it is the last file on the fleet still spelling the retired *_worker model aliases and will keep showing up in future census sweeps.

[2026-09-06T17:53:41Z · sase-x7.3.1.5] WITHDRAWN: the earlier "PROPOSED FOLLOW-UP: Restart long-lived nvim on athena/mac" note is resolved and should NOT be triaged into a task bead — athena never held stale plugin code and mac was invalidated in place. See the FLEET RECEIPT ADDENDUM note above.

[2026-09-06T18:22:40Z · sase-x7.3.1.5--1] just check-full re-run after fleet-deploy (this workspace, HEAD ece5db3cc — 58f16fe68 plus three later ACE refactors): NOT green, but the failure is not a test failure and is not this phase. 13 of 14 gates green (fmt x2, ruff, mypy, keep-sorted, feature flags, pyscripts, test waits, changelog, patch/stitch terminology, symvision, toobig, SASE validation, committed plans). The full suite ran green inside the test-cost lane: durable record 20260906T175732Z-ece5db3cc874-2670581-full-run.json is exit_status 0, failures [], tree_dirty false, 38832 nodes across 3543 files on 14 workers in 21m52s. The previously-noted todo-highlight flake (notes #3/#4) did NOT recur. The single red gate is the last one, 'flake baseline' = 'just selection-health --fail-on-new-flake', which is a host-local historical-evidence gate over ~/.sase/test-selection/gh_sase-org__sase full-run records, not a verdict on this tree. Bead left open per the no-close-on-red-gate rule.

[2026-09-06T18:23:11Z · sase-x7.3.1.5--1] PROPOSED FOLLOW-UP: Retire or baseline the six reproducible flakes now failing 'just selection-health --fail-on-new-flake' — tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation, tests/ace/tui/test_axe_status_read_cache.py::test_run_json_mtime_change_invalidates_cache, the three tests/ace/tui/widgets/test_prompt_panel_section_navigation_targets.py nodes (test_active_section_reconciles_across_same_document_rerender, test_cheap_paint_preserves_section_until_enriched_layout_returns, test_resolve_section_at_row_still_resolves_fold_only_anchor), and tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed. Evidence that they are NOT fleet-deploy: across all schema-2 full-run records these six appear in 44 failing runs from 13 different workspaces (41 in the diff-scoped 'fast' lane, 32 on dirty trees), and the newest failure of any of them is 2026-09-06T02:39:18Z at head 43164eace6ba — about 11h BEFORE the fleet-cutover commit caa7917ac landed (2026-09-06T13:54:28Z). Zero failing records for any of the six after caa7917ac, and caa7917ac touches only completion/, doctor/, main/parser_*, xprompts, bead CLI create and memory notes — no ACE TUI widget, axe status cache, or artifact-directory-audit code. This phase cannot self-clear the gate: tests/reproducible_flake_baseline.txt is explicitly 'debt to remove, not suppressions to grow' and an addition requires a filed bead, while epic phase workers never create beads.

[2026-09-06T18:23:40Z · sase-x7.3.1.5--1] PROPOSED FOLLOW-UP: Repair the dead '# fixed-at:' entry in tests/reproducible_flake_baseline.txt for tests/test_plan_approval_actions_epic.py::test_headless_epic_approval_submits_while_inflight_launch_holds_anchor — the gate reports it retired nothing in the current window. Cause is a node-ID rename, not rot: d2f6cb822 'test(plan): split plan approval action tests under 500 lines' (2026-08-30) moved the test into _epic.py, so the retirement names the post-split path while every recorded failure sits under the pre-split tests/test_plan_approval_actions.py::… path, which the same gate run separately lists among 8 node IDs 'no longer collectable'. Fix is either to point the entry at the recorded (old) path or to drop it once the old evidence ages out at RETENTION_DAYS. Advisory only — _flake_gate_result emits it as a diagnostic and it does not set the exit code; the red came solely from the six new flakes. Also predates this phase and is unrelated to fleet-deploy.

## Dependencies

- **Depends on:** [sase-x7.3.1.4](sase-x7.3.1.4.md) ✓ · ⧖ 2026-09-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-x7.3.1.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-x7.3.1.5.md) | [sase-x7.3.1.5](sase-x7.3.1.5.md) | 0 |
