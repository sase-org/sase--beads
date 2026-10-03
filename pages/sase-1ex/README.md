# Bead: sase-1ex — Make the prompt \`\<space\>\` and \`\<ctrl+n/p\>\` project-cycling keys instant

[Bead Pages](../README.md) / sase-1ex

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vk](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vk.md) · **Assignee:** `sase-1ex.land`
**Created:** 2026-10-02 14:53:42 EDT · **Closed:** 2026-10-03 13:02:34 EDT
**Plan:** [202610/prompt\_space\_and\_project\_cycle\_latency.md](https://github.com/sase-org/sase--plans/blob/main/202610/prompt_space_and_project_cycle_latency.md)

## Description

Opening the prompt bar with `<space>` and cycling the current-project stack with `<ctrl+n>` / `<ctrl+p>` become in-memory operations. Neither key path reads or writes the VCS MRU, lists project records, spawns a subprocess, or stops, starts, or joins a watcher on the event loop. Warm `<ctrl+n/p>` key-to-paint p95 is at most 16 ms. `<space>` reveals a pre-built bar with key-to-paint p95 at most 60 ms. There are no multi-hundred-millisecond first-press or first-visit spikes. Launch, prefill, history, and cycling semantics stay unchanged.

## Notes

[2026-10-03T03:45:50Z · sase-1es.land] DISCOVERED ISSUE: just symvision is red at master 702c8c3167 (ToolRun 39e4b0b10d56d0d1c10bda3c245b0ee2). It reports 'Unused public functions/classes: PublicationPayloadFile and plan_publication_payload_batches in src/sase/core/publication_payload_facade.py'. Both were added only by 5c7e7514ae (sase-1ex.7, 'repair cycle-edit-coalesce verification gates'), and their only consumer is tests/test_core_publication_payload.py. Test references do not count for Symvision. sase-1es.7 note #2 and sase-1ev.6/sase-1ev.11 notes saw the same failure on clean HEAD. Fix per symvision.md: wire up a real non-test consumer, privatize, or delete along with the tests. Reported by sase-1es.land.

[2026-10-03T04:34:39Z · sase-1es.land] DISCOVERED ISSUE: full check ToolRun cfa773a1036ba0fb5cd5208a5908b405 (sase-1es.land, base master 702c8c3167) fails tests that trace to this epic's phases. All of them reproduce deterministically in isolation. (1) tests/ace/tui/test_prompt_bar_editor_stack.py: 13 of 15 fail with AttributeError: '_EditorHarness' object has no attribute '_mounted_prompt_bar' at src/sase/ace/tui/actions/agent_workflow/_prompt_bar_requests.py:82/115. The accessor came from ae16afe548 (sase-1ex.10, 'track active prompt bar explicitly'), and the test harness was never updated. Triage labeled 3 of them NEW and the rest KNOWN. (2) tests/ace/tui/widgets/test_prompt_mount_dedup.py::test_unmount_hook_inventory and ::test_unmount_bodies_run_once: the unmount-hook inventory now has an extra 'JinjaDiagnosticsMixin' entry, from the _jinja_diagnostics.py change in 5c7e7514ae (sase-1ex.7), against the list that 24cff91cd3 (sase-1ex.6) pinned. (3) Possibly related: tests/ace/tui/test_prompt_key_perf_smoke.py::test_prompt_key_io_probe_counts_main_thread_calls fails with FileNotFoundError for <tmp>/.sase/vcs_xprompt_mru.json. Reported by sase-1es.land; none of these touch the pager.

[2026-10-03T09:01:29Z · sase-1eq.3.1.land] DISCOVERED ISSUE: Landing sase-1eq.3.1 independently confirms proposals from sase-1eq.3.1.3 notes 1 and 4 and sase-1eq.3.1.4 note 1 on clean master 0676975ef3 after just install: tests/test_check_sase_core_rs_bindings_tool.py::test_dev_extension_exposes_every_collected_name fails with missing plan_publication_payload_batches. Current linked sase-core 02a062c3d459 wheel (0.36.3) and its Rust sources have no such binding. The Python facade PublicationPayloadFile/plan_publication_payload_batches was introduced exclusively by 5c7e7514ae (sase-1ex.7) and has only tests/test_core_publication_payload.py as a consumer; existing note 1 already owns its Symvision residue. Resolve this facade and its dead helpers/tests per symvision.md, or complete its real core implementation and consumer, in sase-1ex. No rename-caused issue and no duplicate task created.

[2026-10-03T16:12:39Z · sase-1eq.4.1.land] DISCOVERED ISSUE (corroboration from sase-1eq.4.1.land, proposals sase-1eq.4.1.2 #1/#2, sase-1eq.4.1.3 #1, sase-1eq.4.1.5 #3): the 5c7e7514ae (sase-1ex.7) publication facade still breaks master at 9f8c4c529e - installed/pinned sase_core_rs (pin f50782f7) has no plan_publication_payload_batches binding (linked sase-core has no such symbol at all), so tests/test_check_sase_core_rs_bindings_tool.py::test_dev_extension_exposes_every_collected_name fails, symvision flags PublicationPayloadFile and plan_publication_payload_batches as unused public symbols, and Master Gate run 37134560139 (b2c1f58528) fails its lint job at 'Check pinned core bindings'. Reproduces on pre-epic base e847b082c2. Separately, tests/ace/tui/test_launch_context_source.py::test_every_tick_rebroadcasts_to_mounted_views failed in the full scoped lane at 9f8c4c529e and in a targeted -n 8 run on base e847b082c2 but passed in a targeted run at 9f8c4c529e - same load flake sase-1ex.2 note #1 already proposed; no task created.

[2026-10-03T16:22:31Z · sase-1ex.land] LAND FOLLOW-UP TRIAGE (sase-1ex.land, master 9f8c4c529e). New tasks:
- sase-1fn (flake): test_every_tick_rebroadcasts_to_mounted_views, from sase-1ex.2 #1 and sase-1ex.11 #3. ToolRun f5a02662 failed it; 3/3 serial passes at HEAD.
- sase-1fo (ci): agents_tribe_panel_prompts glance/inspect goldens drift with an extra 'sase' tag on the (no Patch) clan row, from sase-1ex.6 #4. Reproduced at HEAD.
- sase-1fp (feature): overlay-docked prompt bar for the missed 60 ms space target, from sase-1ex.11 #2 and sase-1ex.12 #6. The plan sanctions the miss with this follow-up.
- sase-1fq (memory, small): three tui_perf.md rules, from sase-1ex.12 #5. tui_perf.md exists as a tui.md child, contrary to that note; linked to sase-1f2 and sase-1fd.
- sase-1fr (bug, medium): super-chained on_mount at command_line/input.py:254, filter_bar.py:457, axe_entry_editor_rendering.py:146/180, from sase-1ex.12 #7.
Corroborated with +1:
- sase-1a8: ace_page_group focus leak, from sase-1ex.5 #4.
- sase-1bl: test_scroll_derived_cursor_and_streaming_stays in ToolRun f5a02662, from sase-1ex.2 #1.
- sase-1bb: multi-agent OUTPUT VARIABLES heading, from sase-1ex.11 #3. Reproduced solo twice at HEAD.
Active-epic note: sase-1eq got a DISCOVERED ISSUE note. The terminology guard rglobs ignored tests/xprompt dirs, from sase-1ex.8 #2.
Declined:
- sase-1ex.2 #1 peak_tree_rss: sase-1f0's description already cites this sase-1ex.2 report.
- sase-1ex.1 #2 and sase-1ex.8 #1 stale sase-core-rs wheel: environmental and fixed by just install, which lint_and_test.md documents. This venv has 0.36.4 with PromptPredictionCorpus, and test_prompt_prediction_cache passes.
- sase-1ex.3 #1 and sase-1ex.4 #1 io_probe legacy MRU filename: fixed by 5541d4c697 (sase-1eq.3.1.3), and the test passes.
- sase-1ex.10 #1 three_pane_splits flag lint: fixed by c62e4f1491 (sase-1eu.8), which removed the flag.
- sase-1ex.7 #1 per-phase bench delta: superseded by sase-1ex.12's full before/after bench against the baseline.
- sase-1ex.9 #1: it said no action.
- sase-1ex.12 #8 MRU maintenance prune: no user-visible need. Reads filter stale entries, and the 100-entry cap ages them out.
Resolved in landing (epic-caused): the publication_payload_facade proposals (epic notes #1/#3, sase-1ex.7 #2, sase-1ex.11 #3, sase-1ex.12 #4). The dead facade landed in 5c7e7514ae and duplicates the wired core/agent_publication_batches.py, so the landing deletes it with its test.

[2026-10-03T16:22:49Z · sase-1ex.land] DISCOVERED ISSUE (sase-1ex.land, master 9f8c4c529e): the warm ctrl+n/ctrl+p zero-main-thread-I/O guarantee does not hold when the process-wide macro project identity registry is cold. tests/ace/tui/test_launchable_mru.py::test_warm_cycle_performs_zero_main_thread_io and ::test_warm_cycle_ctrl_n_performs_zero_main_thread_io both fail when run alone (list_project_records=1). They pass in the full file only because earlier tests warm sase.macro.project_identity._identity_registry (lru_cache). Main-thread stack: _handle_vcs_mru_cycle_key (_vcs_mru_cycling.py:515) -> _refresh_xprompt_arg_hint_from_cursor -> _get_xprompt_arg_assist_entries -> _xprompt_arg_assist_project_from_text (_xprompt_arg_hints.py:294) -> canonical_macro_project -> _identity_registry -> load_project_display_snapshot -> list_project_records. sase-1ex.7's _cursor_may_need_arg_hint pre-check always passes after a cycle because every #ref contains ':'. Production hits this after startup before any off-thread warm, and after every invalidate_project_display_snapshot / project alias mutation (TUI enable/disable/rename/alias). Epic work: remaining-work tale to follow.

[2026-10-03T17:02:34Z · sase-1ex.land--1] Land sase-1ex: all 12 phases verified closed. Reused sase-1ez.6 _active_prompt_bar; kept GC work from sase-1ez; 60ms space miss paired with sase-1fp. This tale: cold macro-identity key path (project_identity ready/warm + keystroke peek in _xprompt_arg_hints, single-flight warm in _launchable_mru), deleted dead publication_payload_facade + its test (symvision clean of PublicationPayloadFile/plan_publication_payload_batches), retired MRU names integrated, tests updated in test_launchable_mru.py. sase tool run check 339b67f60e0aa47feb709fde15f27601: 52261 passed; 25 NEW failures all in untouched areas (fork envelope, followup markers, export_save/skill-sources terminology drift from sibling commits, parser help, focus-steal) with no imports of changed modules; 3 KNOWN + 1 FLAKY continued (incl. pre-existing symvision discover_macro_plugin_entry_points, untouched). Tale-scope isolation all green: 3 io-probe tests, 70 passed across test_launchable_mru/test_prompt_key_perf_smoke/test_space_prefill/test_prompt_catalog, 60 passed keep-green widgets + macro_project_identity, bench import ok, bindings tool 10 passed. just symvision: only the KNOWN pre-existing finding remains.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1ex.1](sase-1ex.1.md) | Prompt-key perf instrumentation, benchmark, and I/O probes | ✓ closed | small | 2026-10-02 | 1 | 1 |
| [sase-1ex.10](sase-1ex.10.md) | Explicit prompt-active state and one prompt-bar accessor | ✓ closed | medium | 2026-10-02 | 1 | 1 |
| [sase-1ex.11](sase-1ex.11.md) | Make \`\<space\>\` reveal a pre-built hidden prompt bar | ✓ closed | large | 2026-10-02 | 1 | 1 |
| [sase-1ex.12](sase-1ex.12.md) | Final measurements, regression gates, and docs | ✓ closed | small | 2026-10-02 | 1 | 1 |
| [sase-1ex.2](sase-1ex.2.md) | App-owned launchable-MRU snapshot for project cycling | ✓ closed | medium | 2026-10-02 | 1 | 1 |
| [sase-1ex.3](sase-1ex.3.md) | Serve \`\<space\>\` and the other MRU-head entry points from the snapshot | ✓ closed | medium | 2026-10-02 | 1 | 1 |
| [sase-1ex.4](sase-1ex.4.md) | One project-record pass and memoized provider detection per MRU build | ✓ closed | small | 2026-10-02 | 1 | 1 |
| [sase-1ex.5](sase-1ex.5.md) | Pure catalog getters, non-blocking watcher growth, and a wakeable watcher stop | ✓ closed | medium | 2026-10-02 | 1 | 1 |
| [sase-1ex.6](sase-1ex.6.md) | Run each prompt text-area mount, unmount, and worker hook once | ✓ closed | medium | 2026-10-02 | 1 | 1 |
| [sase-1ex.7](sase-1ex.7.md) | One highlight build and no pump-side Jinja inspect per cycle edit | ✓ closed | medium | 2026-10-02 | 1 | 1 |
| [sase-1ex.8](sase-1ex.8.md) | Quiet the work that follows opening or editing the prompt | ✓ closed | small | 2026-10-02 | 1 | 1 |
| [sase-1ex.9](sase-1ex.9.md) | Freeze startup objects and log gen-2 GC pauses | ✓ closed | small | 2026-10-02 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1ex: Make the prompt `&lt;space&gt;` and `&lt;ctrl+n/p&gt;` project-cycling keys instant [closed]"]
    n1["sase-1ex.1: Prompt-key perf instrumentation, benchmark, and I/O probes [closed]"]
    n2["sase-1ex.10: Explicit prompt-active state and one prompt-bar accessor [closed]"]
    n3["sase-1ex.11: Make `&lt;space&gt;` reveal a pre-built hidden prompt bar [closed]"]
    n4["sase-1ex.12: Final measurements, regression gates, and docs [closed]"]
    n5["sase-1ex.2: App-owned launchable-MRU snapshot for project cycling [closed]"]
    n6["sase-1ex.3: Serve `&lt;space&gt;` and the other MRU-head entry points from the snapshot [closed]"]
    n7["sase-1ex.4: One project-record pass and memoized provider detection per MRU build [closed]"]
    n8["sase-1ex.5: Pure catalog getters, non-blocking watcher growth, and a wakeable watcher stop [closed]"]
    n9["sase-1ex.6: Run each prompt text-area mount, unmount, and worker hook once [closed]"]
    n10["sase-1ex.7: One highlight build and no pump-side Jinja inspect per cycle edit [closed]"]
    n11["sase-1ex.8: Quiet the work that follows opening or editing the prompt [closed]"]
    n12["sase-1ex.9: Freeze startup objects and log gen-2 GC pauses [closed]"]
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
    n1 -.-> n8
    n1 -.-> n9
    n1 -.-> n12
    n2 -.-> n3
    n3 -.-> n4
    n5 -.-> n6
    n5 -.-> n7
    n5 -.-> n10
    n6 -.-> n2
    n6 -.-> n3
    n7 -.-> n3
    n8 -.-> n3
    n8 -.-> n11
    n9 -.-> n3
    n9 -.-> n10
    n10 -.-> n3
    n11 -.-> n3
    n12 -.-> n3
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ex.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ex.1/README.md) | [sase-1ex.1](sase-1ex.1.md) | 1 |
| [bbugyi200.athena.sase-1ex.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ex.10.md) | [sase-1ex.10](sase-1ex.10.md) | 1 |
| [bbugyi200.athena.sase-1ex.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ex.11.md) | [sase-1ex.11](sase-1ex.11.md) | 1 |
| [bbugyi200.athena.sase-1ex.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ex.12/README.md) | [sase-1ex.12](sase-1ex.12.md) | 1 |
| [bbugyi200.athena.sase-1ex.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ex.2.md) | [sase-1ex.2](sase-1ex.2.md) | 1 |
| [bbugyi200.athena.sase-1ex.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ex.3/README.md) | [sase-1ex.3](sase-1ex.3.md) | 1 |
| [bbugyi200.athena.sase-1ex.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ex.4.md) | [sase-1ex.4](sase-1ex.4.md) | 1 |
| [bbugyi200.athena.sase-1ex.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ex.5.md) | [sase-1ex.5](sase-1ex.5.md) | 1 |
| [bbugyi200.athena.sase-1ex.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ex.6.md) | [sase-1ex.6](sase-1ex.6.md) | 1 |
| [bbugyi200.athena.sase-1ex.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ex.7.md) | [sase-1ex.7](sase-1ex.7.md) | 1 |
| [bbugyi200.athena.sase-1ex.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ex.8.md) | [sase-1ex.8](sase-1ex.8.md) | 1 |
| [bbugyi200.athena.sase-1ex.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ex.9/README.md) | [sase-1ex.9](sase-1ex.9.md) | 0 |
| [bbugyi200.athena.sase-1ex.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ex.land.md) | [sase-1ex](README.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e0d3645`](https://github.com/sase-org/sase/commit/e0d36453f7a0a4a3493f3ad9a08427ae58ce2e69) | fix: Preserve panel mode when navigating between agents in Agents tab (sase-1ex) | [sase-1ex](README.md) | 2026-02-20 11:56:45 EST |
| sase | [`db40a72`](https://github.com/sase-org/sase/commit/db40a7219ac0e14d14e9965fa968ee58bc88884b) | feat(tui-perf): add prompt-key perf harness with recorded baseline | [sase-1ex.1](sase-1ex.1.md) | 2026-10-02 16:52:09 EDT |
| sase | [`8138678`](https://github.com/sase-org/sase/commit/813867849ce4ff10ae8d1ee9d146367f2e95d475) | feat(ace-tui): app-owned launchable-MRU snapshot for project cycling | [sase-1ex.2](sase-1ex.2.md) | 2026-10-02 19:38:59 EDT |
| sase | [`24cff91`](https://github.com/sase-org/sase/commit/24cff91cd3e5a737d417a5b32cd38835a4125fae) | feat(tui): dispatch prompt mount/unmount/worker hooks once (sase-1ex.6) | [sase-1ex.6](sase-1ex.6.md) | 2026-10-02 19:39:47 EDT |
| sase | [`f896b59`](https://github.com/sase-org/sase/commit/f896b59c4c0fec3d6957aebe46d4a55b8c54d5aa) | feat(ace-tui): serve space and MRU-head entry points from the launchable-MRU snapshot (sase-1ex.3) | [sase-1ex.3](sase-1ex.3.md) | 2026-10-02 20:41:58 EDT |
| sase | [`5c7e751`](https://github.com/sase-org/sase/commit/5c7e7514ae47c29879e9dc122e43948b2984c631) | fix(ace-tui): repair cycle-edit-coalesce verification gates (sase-1ex.7) | [sase-1ex.7](sase-1ex.7.md) | 2026-10-02 21:28:05 EDT |
| sase | [`9dcf826`](https://github.com/sase-org/sase/commit/9dcf826f8bc93ccbe818f7c9df79ba9f48c799ac) | perf(mru): one project-record pass and memoized provider detection per MRU build | [sase-1ex.4](sase-1ex.4.md) | 2026-10-02 21:28:38 EDT |
| sase | [`ae16afe`](https://github.com/sase-org/sase/commit/ae16afe54850ff1eb04f8aa1a74be985f8023b5a) | feat(prompt): track active prompt bar explicitly with one accessor | [sase-1ex.10](sase-1ex.10.md) | 2026-10-02 21:46:17 EDT |
| sase | [`8f910d5`](https://github.com/sase-org/sase/commit/8f910d559b68099aa09e812779a7ef6616cb4786) | feat(prompt-catalog): pure catalog getters, off-pump watcher growth, wakeable watcher stop (sase-1ex.5) | [sase-1ex.5](sase-1ex.5.md) | 2026-10-03 07:13:46 EDT |
| sase | [`3289046`](https://github.com/sase-org/sase/commit/32890465315ebed5bb9be3799951e43aaf59ea29) | feat(prompt-quiet): stagger non-essential bar warm-ups one paint past first paint (sase-1ex.8) | [sase-1ex.8](sase-1ex.8.md) | 2026-10-03 08:24:21 EDT |
| sase | [`90193a0`](https://github.com/sase-org/sase/commit/90193a05d51a7e1339ad9567a8533a870b951c99) | feat(prompt-bar): implement space hot spare phase with lifecycle wiring | [sase-1ex.11](sase-1ex.11.md) | 2026-10-03 11:10:25 EDT |
| sase | [`9f8c4c5`](https://github.com/sase-org/sase/commit/9f8c4c529ee997c0180a9e7036451c8a494c87c5) | docs(perf): record sase-1ex acceptance bench, gates, and runbook results | [sase-1ex.12](sase-1ex.12.md) | 2026-10-03 11:41:21 EDT |
| sase | [`ad1fee5`](https://github.com/sase-org/sase/commit/ad1fee548204ea306831b08303fb7d92851c5a0f) | feat(prompt-keys): cold macro-identity off event loop, drop dead facade, land sase-1ex | [sase-1ex](README.md) | 2026-10-03 13:04:40 EDT |
| sase--plans | [`sase--plans@5fd1654`](https://github.com/sase-org/sase--plans/commit/5fd16547ad968f485ff9d6aacea912bf29851b04) | docs(plans): mark sase-1ex epic and land plans done | [sase-1ex](README.md) | 2026-10-03 13:08:52 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1es.land][1] | Check whether symvision publication_payload_facade failure is already tracked on its causing epic | 1 |
| read-by | [agent:sase-1ev.land][2] | Check whether the publication_payload_facade symvision/binding failures are already recorded on the owning epic | 1 |
| read-by | [agent:sase-1ex.12][3] | Need parent epic notes and phase scope | 1 |
| read-by | [agent:sase-1ex.land--1][4] | land sase-1ex triage | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1es.land/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ev.land/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ex.12/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ex.land.md

<!-- sase:referenced-by:end -->
