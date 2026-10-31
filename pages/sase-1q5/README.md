# Bead: sase-1q5 — Restore TUI speed by ending artifact-index lock starvation

[Bead Pages](../README.md) / sase-1q5

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5k.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5k.linker.w0.md) · **Assignee:** `sase-1q5.land`
**Created:** 2026-10-30 18:38:09 EDT · **Closed:** 2026-10-31 01:39:54 EDT
**Plan:** [202610/tui\_index\_lock\_speedup.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_index_lock_speedup.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/tui_index_lock_speedup.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/tui_index_lock_speedup.md

<!-- sase:links:end -->

## Description

The TUI stops falling into 24–30 s O(archive) fallback scans. The stranded-work collector holds the artifact-index lock for seconds instead of minutes. A busy lock is answered from the last good snapshot, never a filesystem scan. The smaller UI-thread hitch sources the research found are trimmed. A restarted TUI can then be re-measured mechanically before any GC-policy change.

## Notes

[2026-10-31T04:37:42Z · sase-1q5.land] LAND TRIAGE of the 12 PROPOSED FOLLOW-UPs from child notes (sase-1q5.land, 2026-10-31):
- 1q5.3#1 fakey gate-capacity join timeout: new flake task sase-1q8. It groups three unowned full-lane flakes by evidence and links to the active flake epic sase-j7.
- 1q5.5#1 bench_tui_jk 8 clean-base failures: +1 on the owners sase-1ge (fleet x3), sase-1gf (clan fold and link-rail stalls), sase-lx (selected tribe fold), and sase-199 (Axe-tab). The unowned Archive warm-open node became new ci task sase-1qa.
- 1q5.5#2 stale macro input schemas: DECLINED. Already fixed upstream (271632e9d7); tools/sync_macro_input_schemas --check exits 0 on master cb230adb5e.
- 1q5.6#1 full-lane failures: zsh PTY +1 on sase-13a; test_start_monitor_serializes_concurrent_starts_in_one_lane recorded as a DISCOVERED ISSUE note on the active epic sase-j7, which already tracks that node (note #50); test_real_ace_page_query_clear_retry_records_the_live_transition went into sase-1q8.
- 1q5.7#1 index-backed machine-capacity query: new feature task sase-1q9, related to sase-1nc and measure-first.
- 1q5.7#2: test_y_then_label_copies_the_links_resolved_path +1 on sase-z1; test_reveal_matches_fresh_home[pairs1-] went into sase-1q8.
- 1q5.8#2 GC soak re-run and #3 GC census: recorded as a sequencing note on the existing GC track sase-1nc, which owns both; no new task.
- 1q5.8#4 index-lock reader/writer split, #5 immutable Agents read model, #6 JSON name-registry retention: NOT FILED. All three are research Step 4 work, evidence-gated by plan design on the post-restart remeasure. They are recorded in the same sase-1nc note as the next candidates if that measurement still shows lock contention or retention.
- 1q5.8#7 stranded per-report reconcile walk: the phase itself declined it, since 1q5.4 scoped the reconcile and measured 2.5 s per report. Agreed.
- 1q5.8#9 test_cli_names handle_agents_sync NameError: new ci task sase-1q7 (small). Still reproduces on master, with root cause c489e94f1e (missing import).

[2026-10-31T04:42:12Z · sase-1q5.land] DISCOVERED ISSUE (caused by sase-1q5.6, commit 001351f5b9): PromptInputBarStackRenderingMixin._refresh_cursor_subtitle skips its write whenever the newly rendered subtitle equals the private _cursor_subtitle_rendered cache. But about ten other writers assign border_subtitle directly (soft completion, next-word hints, mode subtitle, refresh_search_readout). So the displayed cursor readout can stay stale after a burst returns the cursor to its last cached position. Reproduced on master cb230adb5e in a pilot test: seed 'hello', move the cursor to (0,1), call refresh_search_readout(), move it back to (0,5), call refresh_cursor_readouts(), and wait 0.3 s. The displayed subtitle reads 'Ln 1, Col 2' while the render expects 'Ln 1, Col 6'. Verified fix: also require self.border_subtitle to equal the markup recorded after the last write. With it the readout converges and all 14 cursor-readout tests pass. Remaining epic work, planned as a tale that also closes this epic.

[2026-10-31T05:39:54Z · sase-1q5.land--1] Verified all 8 phases against the plan and DECISIONS (pushdown, no rollback flag, tui_perf.md untouched): stranded batch 238->3 queries; 60 s TTL, 30 s forced floor, memoized verdicts/counts; lock-busy serves same-key cache or keeps roster, first paint keeps bounded scan; sase-core 2775bc00 SQL session/name pushdown + NOCASE indexes + scoped reconcile, inside the sase-core-revision.txt pin; capacity/title and runtime-aggregation trims; persistent trim worker, off-pump ToolRun and capacity probes, debounced prompt subtitle; capacity rescan 120 s + parsed-cache reuse; freeze-report slow-load section and perf-runbook remeasure recipe. Integration: no post-epic commit touches the epic's surfaces; no TUI-process lock-busy source scan remains. Fixed the debounced subtitle dedupe staleness from sase-1q5.6 (displayed-markup check plus regression test). Follow-ups triaged in epic note (new tasks sase-1q7, sase-1q8, sase-1q9, sase-1qa; +1s on sase-1ge, sase-1gf, sase-lx, sase-199, sase-z1, sase-13a; sequencing note on sase-1nc; macro-schema proposal declined as already fixed).

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1q5.1](sase-1q5.1.md) | Batch the stranded-work session query per project | ✓ closed | small | 2026-10-30 | 1 | 1 |
| [sase-1q5.2](sase-1q5.2.md) | Throttle and memoize stranded reports | ✓ closed | medium | 2026-10-30 | 1 | 1 |
| [sase-1q5.3](sase-1q5.3.md) | Never answer a busy index lock with a source scan | ✓ closed | medium | 2026-10-30 | 1 | 1 |
| [sase-1q5.4](sase-1q5.4.md) | Indexed session lookup in sase-core | ✓ closed | medium | 2026-10-30 | 1 | 1 |
| [sase-1q5.5](sase-1q5.5.md) | Trim Agents-tab tick and capacity patch work | ✓ closed | medium | 2026-10-30 | 1 | 1 |
| [sase-1q5.6](sase-1q5.6.md) | Move small synchronous work off the UI pump | ✓ closed | small | 2026-10-30 | 1 | 1 |
| [sase-1q5.7](sase-1q5.7.md) | Calm the machine-capacity feed | ✓ closed | small | 2026-10-30 | 1 | 1 |
| [sase-1q5.8](sase-1q5.8.md) | Mechanical re-measurement and follow-up handoff | ✓ closed | small | 2026-10-30 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1q5: Restore TUI speed by ending artifact-index lock starvation [closed]"]
    n1["sase-1q5.1: Batch the stranded-work session query per project [closed]"]
    n2["sase-1q5.2: Throttle and memoize stranded reports [closed]"]
    n3["sase-1q5.3: Never answer a busy index lock with a source scan [closed]"]
    n4["sase-1q5.4: Indexed session lookup in sase-core [closed]"]
    n5["sase-1q5.5: Trim Agents-tab tick and capacity patch work [closed]"]
    n6["sase-1q5.6: Move small synchronous work off the UI pump [closed]"]
    n7["sase-1q5.7: Calm the machine-capacity feed [closed]"]
    n8["sase-1q5.8: Mechanical re-measurement and follow-up handoff [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n1 -.-> n4
    n1 -.-> n8
    n2 -.-> n5
    n2 -.-> n8
    n3 -.-> n5
    n3 -.-> n8
    n4 -.-> n8
    n5 -.-> n8
    n6 -.-> n7
    n6 -.-> n8
    n7 -.-> n8
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1q5.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q5.1.md) | [sase-1q5.1](sase-1q5.1.md) | 1 |
| [bbugyi200.athena.sase-1q5.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q5.2.md) | [sase-1q5.2](sase-1q5.2.md) | 1 |
| [bbugyi200.athena.sase-1q5.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1q5.3/README.md) | [sase-1q5.3](sase-1q5.3.md) | 1 |
| [bbugyi200.athena.sase-1q5.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q5.4.md) | [sase-1q5.4](sase-1q5.4.md) | 1 |
| [bbugyi200.athena.sase-1q5.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q5.5.md) | [sase-1q5.5](sase-1q5.5.md) | 1 |
| [bbugyi200.athena.sase-1q5.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1q5.6/README.md) | [sase-1q5.6](sase-1q5.6.md) | 1 |
| [bbugyi200.athena.sase-1q5.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q5.7.md) | [sase-1q5.7](sase-1q5.7.md) | 1 |
| [bbugyi200.athena.sase-1q5.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q5.8.md) | [sase-1q5.8](sase-1q5.8.md) | 1 |
| [bbugyi200.athena.sase-1q5.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q5.land.md) | [sase-1q5](README.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b585d3b`](https://github.com/sase-org/sase/commit/b585d3b75bcd3fadbe0709d510d18b7cf6db4f7d) | fix(tui): answer a busy index lock from cache, never a source scan | [sase-1q5.3](sase-1q5.3.md) | 2026-10-30 20:06:14 EDT |
| sase | [`ad6e4d4`](https://github.com/sase-org/sase/commit/ad6e4d4c153316088c866b04e99652826ae00e1d) | perf(ace): throttle stranded report refreshes | [sase-1q5.2](sase-1q5.2.md) | 2026-10-30 20:12:35 EDT |
| sase | [`001351f`](https://github.com/sase-org/sase/commit/001351f5b921b165c52fb13fe2da8e0ea2d91a0a) | perf(tui): move small synchronous work off pump | [sase-1q5.6](sase-1q5.6.md) | 2026-10-30 20:13:22 EDT |
| sase | [`58ce6ee`](https://github.com/sase-org/sase/commit/58ce6ee62e468710a118a93b77d0084cad98b1a5) | feat(bead): batch stranded session query per project | [sase-1q5.1](sase-1q5.1.md) | 2026-10-30 20:29:00 EDT |
| sase | [`4a4a2f5`](https://github.com/sase-org/sase/commit/4a4a2f5a91027c4935d83e91373b282d4984e066) | perf(capacity): calm the machine-capacity feed | [sase-1q5.7](sase-1q5.7.md) | 2026-10-30 21:25:08 EDT |
| sase | [`b09d069`](https://github.com/sase-org/sase/commit/b09d06945d17ad00e49e8b513a983d6951a85c0d) | perf(ace): trim Agents tab tick work | [sase-1q5.5](sase-1q5.5.md) | 2026-10-30 21:57:04 EDT |
| sase-core | [`sase-core@2775bc0`](https://github.com/sase-org/sase-core/commit/2775bc00934ba77abbc6990880013a013fc80be5) | feat(index): push session/name filters into SQL with NOCASE indexes | [sase-1q5.4](sase-1q5.4.md) | 2026-10-30 22:38:17 EDT |
| sase | [`1db087e`](https://github.com/sase-org/sase/commit/1db087e108345f1f353be7f1303ec6e6d7439734) | feat(tools): summarize slow agent loads in freeze report | [sase-1q5.8](sase-1q5.8.md) | 2026-10-31 00:13:15 EDT |
| sase | [`e32449d`](https://github.com/sase-org/sase/commit/e32449dad97d3f7b0de3f7e0168066625d0d145d) | fix(ace): repair stale prompt cursor subtitle readout | [sase-1q5](README.md) | 2026-10-31 01:42:42 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1q5.6][1] | Need epic context and prior phase notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1q5.6/README.md

<!-- sase:referenced-by:end -->
