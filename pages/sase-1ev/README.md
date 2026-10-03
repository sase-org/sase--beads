# Bead: sase-1ev — Memory history in the TUI: a time-aware Memory pane

[Bead Pages](../README.md) / sase-1ev

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vj.md) · **Assignee:** `sase-1ev.land`
**Created:** 2026-10-02 14:43:02 EDT · **Closed:** 2026-10-03 07:12:17 EDT
**Plan:** [202610/memory\_history\_tui.md](https://github.com/sase-org/sase--plans/blob/main/202610/memory_history_tui.md)

## Description

The ACE Memory pane knows about time. Every memory note, web, strand, and agent instruction file can be stepped through, diffed, and reviewed in place, in the pager's exact visual language. Cross-file memory changes can be reviewed without leaving ACE, agents show which memory version they actually read, and every hand-off to the pager lands on the exact version that was on screen. No key blocks, nothing fails silently, and there is no second history engine.

## Notes

[2026-10-03T09:05:24Z · sase-1eq.3.1.land] DISCOVERED ISSUE: sase-1eq.3.1 landing on unchanged clean master 0676975ef3 ran just install then sase tool run check 6541adcd5aba30801281d54d4c0423ad. All earlier lint gates passed; Symvision failed with 24 unused memory-history public definitions introduced by this epic, plus two separately owned publication_payload_facade definitions on sase-1ex. In particular glance_glyph_only in src/sase/ace/tui/modals/memory_pane_rail_glance.py was labeled NEW, but git history attributes it to 8b27e3f011 (sase-1ev.8), already present at this land turn start, with no working-tree source changes. Other failures are ChangesetView, FeedDay, FeedSubjectView, ProvenanceItem, authored_subjects, consequence_displays, first_subject_label, is_home_scope, is_regen_only, scope_chips_text in memory/history/feed_model.py; DeletedSubject, build_deleted_row_text, build_recency_map, deleted_age_text, deleted_subjects, glance_suffix, history_only_node, is_promotion_class, node_glance_path, subject_displays in memory_pane_rail_glance.py; instruction_display_for_subject_id and instruction_row_chips in memory_pane_instructions.py; compute_memory_badge in config_hub_pane.py. Resolve by wiring, privatizing, or deleting per symvision.md before this epic lands; no independent task duplicate found and no new task created. None is a macro-rename symbol.

[2026-10-03T11:12:17Z · sase-1ev.land] LAND VERIFICATION (sase-1ev.land, base master 957513c8e1, 2026-10-03).

STEP 1 — VERIFY. Read the epic, all 13 phases and every note; compared each phase section of plan:202610/memory_history_tui.md against its commit and HEAD source (3691b88ae7, f42f9f225a, 5389d0df3c, b4b1e32754, ba91bf93c1, 166fdefce5, be7d191912, 8b27e3f011, d854842e89, a582a422eb, 0676975ef3, 957513c8e1). Findings fixed in this landing:
- sase-1ev.10 agents-bridge commit 42d5c6866f was never on master (rebase-repair turn left it unpushed in sase_13). Recovered by cherry-pick -n; ported AceMemoryHistory.version_for_blob into a new private sibling _memory_history_blobs.py (BlobQueries over TimelineQueries) because a445a2951d split memory_history.py; blob memo lives in the base store and is dropped by invalidate_subject/invalidate_scope; kept the newer core pin c2a415e5 (descends from ba63f9df, which carries the core blob:OID selector). Agents MEMORY lane chips, AGENTS.md-as-launched row, version-pinned v hints, batch read report versions, CLI blob:OID help, and their tests/goldens now land.
- sase-1ev.9: MemoryPane.on_worker_state_changed never routed the instruction subject/body workers, so the INSTRUCTIONS group could never appear live. Routed both.
- Timeline lens listed versions oldest-first (now the pager's now + newest-first order); cursor/base marks went stale on motion onto prefetched rows (now repaints the two affected rows); the base mark wrapped onto its own line (now sits in the marker column).
- Past/tombstone card heads repeated vN instead of the age; the diff-view context now sheds full -> Δ short form -> none like the pager.
- Rail glance vanished when a description filled the line; it now stays right-aligned on the first line with the description wrapped below (spec §4.6). ≡ 1 shim singular; history-only rows (instruction/tombstone) no longer offer relation-chip links; `stale` chip shows only with a kept snapshot.
- Front door (§7): H now toasts `could not open history: <reason>`, `no history yet · commit this file…`, or `home memory is not in git`, and re-checks _host_visible after the await; @ refuses untracked/NO VCS with the same honest words; card diff folds read `H to expand` (build_diff_body fold_verb).
- Test isolation: the post-startup history warm-up synced the host checkout in every ACE test (the sase-1ev.12 visual-idle stall); autouse fixture in tests/ace/tui/conftest.py no-ops it (badge golden 28.5s -> 4.3s).
- Symvision: 24 unused memory-history definitions resolved (22 privatized, 2 dead feed_model helpers deleted). `sase bead epic-symbols sase-1ev`: none.
- Docs: memory_history.md gains "In the TUI" + blob:OID; stale H/C wording fixed in memory_history.md, ace.md, memory.md, configuration.md, sase.schema.json; Agents-tab chips documented in ace.md/memory.md.
- Goldens: 2 missing time-strip goldens created (clock pinned), 4 memory-panel goldens refreshed (History row -> time strip), 10 new history-state goldens (past read, past diff, timeline lens, rail glance + DELETED tombstone, INSTRUCTIONS group; dark/light 120x40); all inspected; check mode clean twice (22 unchanged).
- New tests: H reason/hidden-hub/web+strand, honest-toast unit, pinned guards and link refusal, past-strand no audit, pin re-resolve, o on hand-written/managed instruction rows, lens order/markers/refusal, card-head age, stale chip, long-description glance, fold verb.
- Perf (§5.5, headless SASE_TUI_TRACE, 300-version subject, 376-changeset feed): step p50 10.7ms / p95 14.5ms (<=30); = diff toggle p95 17.6ms (<=30); Timeline lens open p95 39.4ms (<=100); Changes lens open action 2.3ms. Launch-phase service numbers stand (timeline 56ms, feed 45ms). Live stall-log soak not run.

STEP 2 — INTEGRATE. Reviewed every non-epic commit since 2026-10-02 14:43: a445a2951d memory_history split (integrated above); sase-1eq.3.1.x macro rename/guard (test_macro_terminology passes on this tree); sase-1es/sase-1eu pager+deck work, sase-1ez TUI perf, sase-1ex MRU work — no overlap; warm-up already runs after the startup stopwatch (55eec1b986). origin/master b4e667d1eb only touches the contract manifest.

ABSORBED BEADS. sase-1e6 closed superseded (watermark-core + watermark-tui). Notes on sase-1e5 (remaining: sase memory log rows) and sase-1en (remaining: CLI text vocabulary).

FOLLOW-UP TRIAGE.
- 1ev.4#1, 1ev.5#4, 1ev.11#1 flags rule 7 (sase-1ey three_pane_splits): no longer reproduces (just _lint-flags exit 0) — declined.
- 1ev.4#2, 1ev.5#2, 1ev.6#2, 1ev.8#2, 1ev.13#1-2 goldens: done here.
- 1ev.4#3, 1ev.5#3, 1ev.6#2 perf: measured here (table above).
- 1ev.6#1, 1ev.7#1, 1ev.9#1, 1ev.11#1 publication_payload_facade symvision + missing plan_publication_payload_batches binding: owned by active epic sase-1ex (notes #1/#3) — no new record.
- 1ev.6#3, 1ev.7#1, 1ev.8#1, 1ev.9#1, 1ev.12#3 prompt_bar_editor_stack, pager three_panes, xprompt __getattr__ symvision, macro/doctor suites: all pass/resolved on current master — declined; the unnamed parallel-load flakes in 1ev.6#3/1ev.12#3 carried no failure signatures — declined.
- 1ev.10#3 test_prompt_key_io_probe (resolved on master) declined; peak_tree_rss flake -> +1 sase-1f0.
- 1ev.11#1 completion host-store leaks -> +1 sase-14o (with the plan-candidates sibling).
- 1ev.12#1 visual-lane convergence stall: epic-caused, fixed here. 1ev.12#2 stale sase-1eu epic-symbols: already gone.
- 1ev.13#3 agents-bridge gap: recovered here.
- New: sase-1fk (light-theme badge contrast, pre-existing since sase-1dr). Landing check AcePageGroup flakes -> +1 sase-1a8 and sase-13c; stale contract manifest filed as sase-1fl then closed superseded by b4e667d1eb.

CHECK. sase tool run check 9c299cefca56681b54ce3beac6555f82: every lint stage green except 2 KNOWN symvision (sase-1ex); tests 52177 passed, 5 failed, all outside this epic (bindings: sase-1ex; launch_executor: KNOWN; contract manifest: fixed by b4e667d1eb; 2 AcePageGroup load flakes pass 3/3 in isolation). toobig: memory_pane_changes_lens.py (2115) and memory_pane_timeline_lens.py (1490) exceed 1000 lines since phases 7/6 — left to the toobig_split routine per lint_and_test.md.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1ev.1](sase-1ev.1.md) | Repair the H and C front door | ✓ closed | small | 2026-10-02 | 1 | 1 |
| [sase-1ev.10](sase-1ev.10.md) | Memory as seen by the agent in the Agents tab | ✓ closed | medium | 2026-10-02 | 1 | 1 |
| [sase-1ev.11](sase-1ev.11.md) | Core review watermark and the CLI feed header | ✓ closed | medium | 2026-10-02 | 1 | 2 |
| [sase-1ev.12](sase-1ev.12.md) | Review watermark in the Changes lens | ✓ closed | small | 2026-10-02 | 1 | 1 |
| [sase-1ev.13](sase-1ev.13.md) | Document, measure, and review end to end | ✓ closed | small | 2026-10-02 | 1 | 1 |
| [sase-1ev.2](sase-1ev.2.md) | App-scoped history service and the public history kit | ✓ closed | medium | 2026-10-02 | 1 | 1 |
| [sase-1ev.3](sase-1ev.3.md) | Pinned card head with the two-row time strip | ✓ closed | medium | 2026-10-02 | 1 | 1 |
| [sase-1ev.4](sase-1ev.4.md) | Step through versions on the card | ✓ closed | medium | 2026-10-02 | 1 | 1 |
| [sase-1ev.5](sase-1ev.5.md) | Word-diff view on the card | ✓ closed | medium | 2026-10-02 | 1 | 1 |
| [sase-1ev.6](sase-1ev.6.md) | Lens framework and the Timeline lens | ✓ closed | medium | 2026-10-02 | 1 | 1 |
| [sase-1ev.7](sase-1ev.7.md) | Changes lens over a shared feed view-model | ✓ closed | medium | 2026-10-02 | 1 | 1 |
| [sase-1ev.8](sase-1ev.8.md) | Rail recency glance and deleted subjects | ✓ closed | medium | 2026-10-02 | 1 | 1 |
| [sase-1ev.9](sase-1ev.9.md) | Instructions group and instruction cards | ✓ closed | medium | 2026-10-02 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1ev: Memory history in the TUI: a time-aware Memory pane [closed]"]
    n1["sase-1ev.1: Repair the H and C front door [closed]"]
    n2["sase-1ev.10: Memory as seen by the agent in the Agents tab [closed]"]
    n3["sase-1ev.11: Core review watermark and the CLI feed header [closed]"]
    n4["sase-1ev.12: Review watermark in the Changes lens [closed]"]
    n5["sase-1ev.13: Document, measure, and review end to end [closed]"]
    n6["sase-1ev.2: App-scoped history service and the public history kit [closed]"]
    n7["sase-1ev.3: Pinned card head with the two-row time strip [closed]"]
    n8["sase-1ev.4: Step through versions on the card [closed]"]
    n9["sase-1ev.5: Word-diff view on the card [closed]"]
    n10["sase-1ev.6: Lens framework and the Timeline lens [closed]"]
    n11["sase-1ev.7: Changes lens over a shared feed view-model [closed]"]
    n12["sase-1ev.8: Rail recency glance and deleted subjects [closed]"]
    n13["sase-1ev.9: Instructions group and instruction cards [closed]"]
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
    n0 --> n13
    n1 -.-> n6
    n2 -.-> n3
    n3 -.-> n4
    n4 -.-> n5
    n6 -.-> n2
    n6 -.-> n7
    n7 -.-> n8
    n8 -.-> n9
    n9 -.-> n10
    n10 -.-> n11
    n11 -.-> n12
    n12 -.-> n13
    n13 -.-> n4
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ev.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ev.1/README.md) | [sase-1ev.1](sase-1ev.1.md) | 1 |
| [bbugyi200.athena.sase-1ev.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ev.10.md) | [sase-1ev.10](sase-1ev.10.md) | 1 |
| [bbugyi200.athena.sase-1ev.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ev.11/README.md) | [sase-1ev.11](sase-1ev.11.md) | 2 |
| [bbugyi200.athena.sase-1ev.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ev.12/README.md) | [sase-1ev.12](sase-1ev.12.md) | 1 |
| [bbugyi200.athena.sase-1ev.13](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ev.13/README.md) | [sase-1ev.13](sase-1ev.13.md) | 1 |
| [bbugyi200.athena.sase-1ev.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ev.2/README.md) | [sase-1ev.2](sase-1ev.2.md) | 1 |
| [bbugyi200.athena.sase-1ev.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ev.3.md) | [sase-1ev.3](sase-1ev.3.md) | 1 |
| [bbugyi200.athena.sase-1ev.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ev.4/README.md) | [sase-1ev.4](sase-1ev.4.md) | 1 |
| [bbugyi200.athena.sase-1ev.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ev.5.md) | [sase-1ev.5](sase-1ev.5.md) | 1 |
| [bbugyi200.athena.sase-1ev.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ev.6/README.md) | [sase-1ev.6](sase-1ev.6.md) | 1 |
| [bbugyi200.athena.sase-1ev.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ev.7.md) | [sase-1ev.7](sase-1ev.7.md) | 1 |
| [bbugyi200.athena.sase-1ev.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ev.8/README.md) | [sase-1ev.8](sase-1ev.8.md) | 1 |
| [bbugyi200.athena.sase-1ev.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ev.9.md) | [sase-1ev.9](sase-1ev.9.md) | 1 |
| [bbugyi200.athena.sase-1ev.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ev.land/README.md) | [sase-1ev](README.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3691b88`](https://github.com/sase-org/sase/commit/3691b88ae7fe33bdae10dc5c6aeb5bba4217a759) | fix(ace-tui): open memory history pagers directly from app thread | [sase-1ev.1](sase-1ev.1.md) | 2026-10-02 15:12:30 EDT |
| sase | [`f42f9f2`](https://github.com/sase-org/sase/commit/f42f9f225ad9a78892c357312c2b9efb988bd7c2) | feat(history): shared history service with ACE SWR timeline and pager history kit | [sase-1ev.2](sase-1ev.2.md) | 2026-10-02 16:42:13 EDT |
| sase | [`5389d0d`](https://github.com/sase-org/sase/commit/5389d0df3cb0dfac41d3d593418068b5d0647e02) | feat(ace-tui): pinned memory card head with two-row time strip | [sase-1ev.3](sase-1ev.3.md) | 2026-10-02 20:27:25 EDT |
| sase-core | [`sase-core@ba63f9d`](https://github.com/sase-org/sase-core/commit/ba63f9dfd99916765c989fcd380313591c936728) | feat(core): add memory history query and cache coverage | [sase-1ev.10](sase-1ev.10.md) | 2026-10-02 20:46:07 EDT |
| sase | [`b4b1e32`](https://github.com/sase-org/sase/commit/b4b1e327545ab801621e7dabe8ceb6472a5f3693) | feat(memory-pane): add card time-stepping with pinned past view | [sase-1ev.4](sase-1ev.4.md) | 2026-10-02 21:49:04 EDT |
| sase | [`ba91bf9`](https://github.com/sase-org/sase/commit/ba91bf93c12bfdee6ddd1560516292ab43b8df00) | feat(ace): add memory pane diff, history, and time views | [sase-1ev.5](sase-1ev.5.md) | 2026-10-02 22:26:30 EDT |
| sase-core | [`sase-core@c2a415e`](https://github.com/sase-org/sase-core/commit/c2a415e50d8353fc01bc14aaa3949e20326432e2) | feat(memory-history): add review state store with query and mark-reviewed | [sase-1ev.11](sase-1ev.11.md) | 2026-10-02 22:50:42 EDT |
| sase | [`a582a42`](https://github.com/sase-org/sase/commit/a582a422eb61df9bfe6d0480d37e3cb262f5c693) | feat(memory-history): add review watermark and CLI feed header with mark-reviewed | [sase-1ev.11](sase-1ev.11.md) | 2026-10-02 22:55:05 EDT |
| sase | [`166fdef`](https://github.com/sase-org/sase/commit/166fdefce5860d62ce8e73e84ec7d170905937c8) | feat(ace): add memory pane Timeline lens with kit picker rail | [sase-1ev.6](sase-1ev.6.md) | 2026-10-03 00:19:44 EDT |
| sase | [`be7d191`](https://github.com/sase-org/sase/commit/be7d19191255f3f3d8f8427312e3bc0077cdd56f) | feat(memory-history): changes lens over shared feed view-model (sase-1ev.7) | [sase-1ev.7](sase-1ev.7.md) | 2026-10-03 01:25:13 EDT |
| sase | [`8b27e3f`](https://github.com/sase-org/sase/commit/8b27e3f011019c3caad2584ddb53dc78919a8f4d) | feat(memory-history): rail recency glance and deleted subjects (sase-1ev.8) | [sase-1ev.8](sase-1ev.8.md) | 2026-10-03 02:22:31 EDT |
| sase | [`d854842`](https://github.com/sase-org/sase/commit/d854842e893bacf6285b2ef5cd21d5b596f7500e) | feat(memory-history): collapsed INSTRUCTIONS rail group and instruction cards (sase-1ev.9) | [sase-1ev.9](sase-1ev.9.md) | 2026-10-03 03:12:24 EDT |
| sase | [`0676975`](https://github.com/sase-org/sase/commit/0676975ef3624059393e9e058a43678f6c58e34f) | feat(memory-history-tui): Changes-lens review chip + unreviewed dots + m to mark reviewed, MEMORY badge (sase-1ev.12) | [sase-1ev.12](sase-1ev.12.md) | 2026-10-03 04:46:01 EDT |
| sase | [`957513c`](https://github.com/sase-org/sase/commit/957513c8e14971fb7b76b53556c667f95b89fa55) | docs(memory): document Memory panel instructions group and review watermark | [sase-1ev.13](sase-1ev.13.md) | 2026-10-03 05:03:41 EDT |
| sase | [`e847b08`](https://github.com/sase-org/sase/commit/e847b082c26fbb7fedda20cf4486e0d88427caf9) | feat(memory-history-tui): land sase-1ev with the recovered agents bridge and pane fixes | [sase-1ev](README.md) | 2026-10-03 07:15:05 EDT |
| sase--plans | [`sase--plans@505dd2b`](https://github.com/sase-org/sase--plans/commit/505dd2b81022dd5d132db793f755f8f1f55f117b) | chore(plans): mark memory\_history\_tui epic plan done (sase-1ev) | [sase-1ev](README.md) | 2026-10-03 07:17:15 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ev.11][1] | Need parent epic design and watermark spec | 1 |
| read-by | [agent:sase-1ev.13][2] | Need epic children status | 1 |
| read-by | [agent:sase-1ev.6][3] | epic context for phase | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ev.11/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ev.13/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ev.6/README.md

<!-- sase:referenced-by:end -->
