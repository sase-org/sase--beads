# Bead: sase-17x.13.10.4 — Fresh caches, project and cd resolution, and the keystroke probe

[Bead Pages](../README.md) / [sase-17x.13.10](sase-17x.13.10.md) / sase-17x.13.10.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17x.13.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17x.13.land.md) · **Assignee:** `sase-17x.13.10.4` · **Size:** medium
**Created:** 2026-09-25 08:41:44 EDT · **Closed:** 2026-09-25 14:59:36 EDT
**Plan:** [202609/command\_line\_landing\_gaps.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_landing_gaps.md)

## Description

completion-sources: bypass the provider disk cache after a block finishes and drop in-flight stale fetches. Resolve `cd +<label>` and `+home`, and merge the provider into project slots. Offer `cd -` and dotfiles. Stamp the perf probe at the key. Close the listed source test gaps.

## Notes

[2026-09-25T18:58:52Z · sase-17x.13.10.4] PROPOSED FOLLOW-UP: 5 tests fail identically on a pristine HEAD export (verified) after just install rebuilt sase_core_rs from the current sase-core checkout — tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_queue_argument_rows_match (3 params), tests/ace/tui/widgets/test_directive_arg_completion.py::test_queue_capacity_completion_describes_limit (description now ends "…, or <M>x multiplier of this machine's max_running_agents budget"), and tests/main/test_var_integration.py::test_var_cli_end_to_end_refreshes_index_and_round_trips_machine_outputs — the sase expectations and the rebuilt core disagree; not touched by this phase

[2026-09-25T18:59:08Z · sase-17x.13.10.4] PROPOSED FOLLOW-UP: two tests failed once in the full scoped lane at host load ~20 and passed on rerun — tests/main/test_ace_handler.py::test_run_ace_app_does_not_join_default_executor_worker and tests/ace/tui/test_statistics_pane_filters.py::test_reverse_range_cycles_backward_wraps_and_reenters_from_custom; likely load-sensitive timing, worth a stability look

[2026-09-25T18:59:36Z · sase-17x.13.10.4] completion-sources landed. Disk-cache bypass: candidates_for(use_disk_cache=False) + ProviderCache.invalidate() bumps the generation (drops in-flight commits), marks the disk cache suspect until each (kind, project) refetches once; invalidate_provider_cache also cancels the in-flight task, and an active menu keeps its rows while the next render refetches past the disk cache. cd +<label>/+home: _resolve_project_checkout matches canonical key first, then ProjectDisplaySnapshot label, include_home=True, still off the UI thread via resolve_cd in to_thread. Project slots always merge the provider behind in-memory rows (deduped by value); proc/agent/patch keep in-memory-first with provider fallback. cd offers '-' last in the empty-argument menu; path scan lists dotfiles once the typed basename starts with '.' (separate source key). Perf probe stamps at CommandLineInput._on_key (only under SASE_TUI_PERF=1, valid only when the text changed) and _refresh_completion consumes it; probe append tasks are held in a module set. Tests: new tests/ace/tui/command_line/test_completion_sources.py (18 tests, 14 fail on the pre-change src) covers all listed gaps (marked agent row on mounted screen, path scan thread, cd dirs, proc/project provider fetch, --cwd path rows via complete(), disk bypass, labelled/home cd resolution) plus a provider-level use_disk_cache test; also fixed a race in test_policy_io::test_palette_tip_marker_write_runs_off_loop (waited on the spy, not the marker; failed on clean base). Verified: just fix; sase tool run check — every lint gate passed (ruff, mypy, symvision, flags, terminology, validation); scoped lane escalated to the full suite: 47446 passed, 7 failed, none in files this phase touched — 5 reproduce identically on a pristine HEAD export (queue-capacity directive description parity x4, test_var_integration; recorded as PROPOSED FOLLOW-UP), 2 were load-flaky and passed on rerun (also noted). The ~/.sase-independent venv needed just install for the fresh CommandLineGrammar binding. No goldens regenerated (goldens-walkthrough owns that).

## Dependencies

- **Depends on:** [sase-17x.13.10.3](sase-17x.13.10.3.md) ✓ · ⧖ 2026-09-25
- **Blocks:** [sase-17x.13.10.6](sase-17x.13.10.6.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.13.10.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.13.10.4/README.md) | [sase-17x.13.10.4](sase-17x.13.10.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`136a3e9`](https://github.com/sase-org/sase/commit/136a3e94885a455fc56d1405beabf71ccc6cb07c) | fix(command-line): fresh completion caches, cd project resolution, key-receipt probe (sase-17x.13.10.4) | [sase-17x.13.10.4](sase-17x.13.10.4.md) | 2026-09-25 15:01:28 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17x.13.10.4][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.13.10.4/README.md

<!-- sase:referenced-by:end -->
