# Bead: sase-17m.5.1.6.4 — Docs integration, perf re-run, classification, and full verification

[Bead Pages](../README.md) / [sase-17m.5.1.6](sase-17m.5.1.6.md) / sase-17m.5.1.6.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.5.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.5.1.land.md) · **Assignee:** `sase-17m.5.1.6.4` · **Size:** medium
**Created:** 2026-09-25 04:39:13 EDT · **Closed:** 2026-09-25 09:20:05 EDT
**Plan:** [202609/agent\_session\_ace\_cutover\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_ace_cutover_finish.md)

## Description

docs-verify: update docs that still name the renamed perf scenarios or the retired agent-family copy (docs/perf_runbook.md, docs/ace.md, docs/pager.md, the orchestration blog post, and any doc describing copy changed in copy-stragglers). Run the full non-visual tests/ace and tests/perf suites, a visual check over the session/tribe/clan/fleet goldens, the j/k navigation bench on a quiet host plus the view-hints regression check, the final famil classification sweep, and `sase tool run check`.

## Notes

[2026-09-25T13:19:21Z · sase-17m.5.1.6.4] PROPOSED FOLLOW-UP: re-run tests/ace/tui/bench_tui_jk.py on a quiet host (1-min load < 2) — the host never dropped below load ~7.5 in a 20-minute wait, so 6 of 10 benches (clan fold level 1, selected tribe fold level 1 [existing bead sase-lx], the three Fleet fault scenarios, and the Axe tab-set assertion) missed identically on this tree and on pre-epic 02c4b029a; no epic-attributable regression, but the tight 16 ms budgets remain unverified on an idle host.

[2026-09-25T13:19:33Z · sase-17m.5.1.6.4] PROPOSED FOLLOW-UP: test_bench_axe_jk (tests/ace/tui/bench_tui_jk_panes.py:90) fails its non-budget assertion {sample["tab"]} == {"axe"} identically on pre-epic 02c4b029a and on master under host load; looks like agents-tab samples leaking into the Axe window rather than a latency miss — investigate the sample-window boundary.

[2026-09-25T13:20:05Z · sase-17m.5.1.6.4] Docs: perf_runbook.md renamed session_container_press/session_container_unfolded_press and the agent_session_container trace counter (was family_container, x5 spots); ace.md plan-family -> plan-session (x2); pager.md 'Session and clan conversations'; orchestration blog 'clan, session, or tribe identity'; workspace.md 'session follow-up'. ace.md tribe-composition/statistics/revert copy already matched. Left agents_sidecar.md, families/ sidecar URLs, agent_sessions.md 'formerly agent families' as intentional history. Verification: (1) pytest -n 8 -m 'not visual and not slow' tests/ace tests/perf = 14481 passed, 1 skipped, 0 failed. (2) Visual check-mode over test_ace_png_snapshots_agents_*, artifacts_agents, config_center_statistics, revert = 153 passed, 1 failed (only the known sase-18y test_agent_session_panel_fold_levels_and_member_override agent-xprompt timeout); created=0 updated=0, no golden changed. (3) Perf: tests/perf/check_view_hints_regression.py all 12 gates PASS (unfolded session press view_files p50 1.79 ms vs baseline 85.4; unfolded render p50 38.5 vs 83.5; clan press 2.69 ms). The host never got quiet (1-min load 7.5-13 for the whole window after a 20-min wait, other agents), so j/k bench = noisy: bench_tui_jk.py 6 failed/4 passed on HEAD (twice) AND on a worktree of pre-epic 02c4b029a in the same window, same 6 tests. p50/p95 ms next|prev, HEAD run1 / HEAD run2 / pre-epic: large-list 14.09/38.29|14.09/30.27 / 15.91/27.90|16.10/29.39 / 15.39/34.30|13.47/26.51; clan L1 14.42/19.36|13.63/23.83 / 14.59/18.38|13.37/16.31 / 13.50/20.72|11.61/13.93; tribe L1 48.69/61.06|47.26/57.70 / 49.31/86.35|50.57/86.32 / 46.06/62.72|47.42/62.16; fleet hung_host 12.49/32.17|13.37/29.85 / 14.00/32.48|15.69/36.39 / 12.94/29.45|12.88/32.30; axe (untouched by epic) 13.21/34.89|10.25/34.65 / 10.86/33.63|9.00/35.69 / 11.87/31.71|12.79/32.94; patches 1.00/1.90 / 1.34/2.97 / 1.22/1.54. No regression attributable to the epic; misses predate it (existing bead sase-lx covers tribe L1); recorded PROPOSED FOLLOW-UPs for quiet-host rerun and the axe tab-set assertion. (4) Classification sweep (git grep -in famil): src/sase/ace 233 hits = 68 marked/named legacy readers (fleet/agent_bundle/notification/revert/dismissed/directive-completion/legacy-syntax-flag rewrites) + 165 unrelated (RelationKind/Role.FAMILY, Patch revert/sibling family, MarkerFamily, search-operator family, model_family/usage family: scopes, font/hue/color families, detect_vcs_family, filename/version family, Beads epic family, generic English, _same_workflow_artifact_family = artifact-dir grouping); tests/ace 357 = 157 legacy wire fixtures/named legacy-input tests + 149 opaque rendered visual data + 51 unrelated (artifacts_contract, MarkerFamily, search-operator, RelationKind...); tests/perf 0; default_config.yml 0; schema 2 hits both the legacy_agent_family_syntax flag entry. One small straggler fixed: test_glossary_preview_render.py wrapped-alias data 'agent family' -> 'agent group'. (5) sase tool run check first failed on 4 stale copy-pin tests outside tests/ace (test_copy_agent_name, test_keymaps_app_bindings, test_keymaps_defaults_modes, test_dynamic_agent_session_root_zero_suffix pinned 'family container'/'Workflow/Family'/'Set family level'/'FAMILY' header that src already renders as session); updated them; rerun of sase tool run check PASSED (exit 0). epic-symbols: none for sase-17m.5.1.6.4, sase-17m.5.1.6, its 3 sibling phases, or sase-17m.5.1.

## Dependencies

- **Depends on:** [sase-17m.5.1.6.3](sase-17m.5.1.6.3.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.5.1.6.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.5.1.6.4/README.md) | [sase-17m.5.1.6.4](sase-17m.5.1.6.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`24615e1`](https://github.com/sase-org/sase/commit/24615e18d44570c0650fcd597ac2e7f2b8c678e5) | docs(agent-session): match renamed perf scenarios and session copy, fix stale copy-pin tests (sase-17m.5.1.6.4) | [sase-17m.5.1.6.4](sase-17m.5.1.6.4.md) | 2026-09-25 09:21:24 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.5.1.6.4][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.5.1.6.4/README.md

<!-- sase:referenced-by:end -->
