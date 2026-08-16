# Bead: sase-mi — High-impact task bead sweep

[Bead Pages](../README.md) / sase-mi

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.02y](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.02y.md) · **Assignee:** `sase-mi.land`
**Created:** 2026-08-15 20:00:31 EDT · **Closed:** 2026-08-16 00:17:31 EDT
**Plan:** [202608/high\_impact\_task\_bead\_sweep.md](https://github.com/sase-org/sase--plans/blob/main/202608/high_impact_task_bead_sweep.md)

## Description

Reconcile every ready sase task bead, retire stale recommendations with evidence, and complete the five live fixes with the largest durability, verification, responsiveness, and commit-workflow impact.

## Notes

[2026-08-16T02:03:32Z · toobig-2s.split_file.src.sase.ace.tui.widgets.artifacts.files_pane.0] DISCOVERED ISSUE: the bead store is currently wedged for writes — every 'sase bead' mutation aborts at commit with sase.bead._stream_integrity.BeadStreamIntegrityError: 'cannot publish non-append-only bead event stream sase-mk: worktree rewrote ancestor event 5' (raised from _stream_integrity.prepare_event_streams_for_commit via sdd/_commit_store.commit_sdd_files). Reproduced 2026-08-15 ~22:00 EDT from workspace sase_12 on master 117476b7d: 'sase bead +1 sase-mk --note ...' failed and recorded nothing (bead history sase-mk still ends at the 01:48:51Z issue_updated event), and an unrelated 'sase bead note sase-mf ...' failed with the SAME sase-mk error even though its own note event WAS appended locally (bead history sase-mf shows my note_appended at 02:02:13Z) — so writes now land in the worktree but can never be published, and the failure is attributed to whichever stream is dirty rather than the bead being written. 'sase bead doctor' reports 'bead state has uncommitted changes' plus 14 ERROR-level rewritten/short streams already in published history (sase-m5 ev3, sase-m7 ev2, sase-m8 ev2, sase-mb ev6, sase-m4 ev46, sase-md ev2, sase-me ev5, sase-ll ev11, sase-lk ev11, sase-mh ev4, sase-jw ev6, sase-mk ev2, sase-ml ev3, and sase-j7 shorter than its own history missing events 62-63), each naming a first offending commit. Causal link: phase sase-mi.2 'Protect append-only bead event streams' added the commit/push guard (b681d1bc3) that is now, correctly, refusing a store whose history was already rewritten before the guard existed; nothing repairs or quarantines that pre-existing damage, so the guard converts old corruption into a total write outage. Phase sase-mi.7 owns verifying the combined tree and reconciling task beads. Suggested scope for the fix: repair or quarantine the 14 damaged streams, and make the commit path fail only for the streams actually being written (or report every offending stream) instead of aborting an unrelated bead's write. Reported here rather than as a task because filing a task bead is itself blocked by this defect. RELATED: sase-li (concurrent bead sync can silently delete an event from a shared stream — plausible upstream cause of these rewrites); sase-mk (in-progress symvision task whose +1 evidence I could not record because of this).

[2026-08-16T02:05:41Z · sase-mk] DISCOVERED ISSUE: After sase-mk publicized the Models-panel provider-routing helpers, just _lint-symvision no longer reports those 16 private-import findings. It now fails on leftover unused-public symbols from this epic's closed phases: StreamIntegrityResult, analyze_stream_against_ancestor, encode_stream_events, is_event_stream_relpath, and parse_stream_text in src/sase/bead/_stream_integrity.py (sase-mi.2; in-file + tests only) and clear_agent_page_url_registry_cache in src/sase/ace/tui/models/agent_page_url.py (sase-mi.4; tests only). These still block just check. Per symvision.md, privatize the in-file helpers (and the test-only cache-clear seam) rather than allowlisting them.

[2026-08-16T02:14:17Z · sase-mk] DISCOVERED ISSUE: sase bead close sase-mk writes a valid append (note_appended + issue_closed) but re-serializes event 5 and drops payload.fields.resolution:null. prepare_event_streams_for_commit then treats missing-vs-null as a rewrite of ancestor event 5, restores HEAD, and aborts the commit. Captured: event_id sase-mk:000005:issue_updated:... stays the same; only the explicit null key is omitted. This is a serializer/integrity mismatch from sase-mi.2, not a real history rewrite, and it currently blocks closing sase-mk.

[2026-08-16T02:39:15Z · toobig-2s.split_file.src.sase.llm_provider.registry.0] DISCOVERED ISSUE: During unrelated llm_provider registry-split verification on 2026-08-15 at HEAD 392dcc962, just check passed fmt, keep-sorted, Ruff, mypy, pyscripts, test-waits, changelog, and terminology, then Symvision failed on eight unused-public leftovers causally introduced by this epic: StreamIntegrityResult, analyze_stream_against_ancestor, encode_stream_events, is_event_stream_relpath, and parse_stream_text in src/sase/bead/_stream_integrity.py (closed phase sase-mi.2); clear_agent_page_url_registry_cache in src/sase/ace/tui/models/agent_page_url.py (closed phase sase-mi.4); and PublicationDrainTimedOut plus configured_publication_drain_timeout in src/sase/agents_sync/commit_publication.py (active phase sase-mi.6). The current registry diff touches only src/sase/llm_provider/registry*.py. This independently confirms the existing sase-mi note from sase-mk for the phase 2/4 symbols and adds the phase 6 findings; phase sase-mi.7 owns combined-tree verification.

[2026-08-16T03:13:45Z · toobig-2s.split_file.tests.test_plan_filter_query.0] DISCOVERED ISSUE (still live, newer HEAD): the eight unused-public leftovers already recorded on this epic still fail 'lint (symvision)' at master 4fae4e794 — i.e. after 7a8f1138f cleared the 16 private-import findings and after 392dcc962 landed. Reproduced 2026-08-15 from workspace sase_14 while my own diff touched only tests/test_plan_filter_query*.py; 'git stash -u' + 'just _lint-symvision' on the clean 4fae4e794 tree reports the identical list: StreamIntegrityResult, analyze_stream_against_ancestor, encode_stream_events, is_event_stream_relpath, parse_stream_text (sase-mi.2); clear_agent_page_url_registry_cache (sase-mi.4); PublicationDrainTimedOut, configured_publication_drain_timeout (sase-mi.6). No new evidence about the cause — recording only that in-progress phase sase-mi.7's verification target is not yet met and 'just check' still stops at the symvision gate before running any tests. The ninth symbol, FilesQueryIndexResult, is ready task sase-mn and was +1'd there, not here.

[2026-08-16T03:42:20Z · toobig-2t.split_file.src.sase.ace.tui.modals.models_panel_display.0] DISCOVERED ISSUE: The eight unused-public leftovers already tracked here still block just check on newer HEAD c6d84d2a4 during unrelated Models-panel display splitting. The gate passed formatting, Ruff, mypy, pyscripts, test-waits, changelog, and terminology, then reported StreamIntegrityResult, analyze_stream_against_ancestor, encode_stream_events, is_event_stream_relpath, parse_stream_text (sase-mi.2), clear_agent_page_url_registry_cache (sase-mi.4), and PublicationDrainTimedOut plus configured_publication_drain_timeout (sase-mi.6). My diff touches only models_panel_display.py and the new models_panel_display_options.py. Phase sase-mi.7 remains the causal owner for combined-tree verification. The ninth finding, FilesQueryIndexResult, was independently corroborated on task sase-mn.

[2026-08-16T04:17:31Z · sase-mi.land] VERIFIED (read the code and commits, not just the phase notes). Phase 1: 19 ready tasks audited, 6 closed with named evidence, 5 selected preserved. Phase 2 / sase-li -> b681d1bc3: prepare_event_streams_for_commit guards both commit paths (sdd/_commit_store.py, bead/_sync_git.py), refuse_unpublished_event_stream_shrink guards the push in sync_worker.py, diagnose_event_stream_history feeds doctor/sync and names stream, event range, and first offending commit -- confirmed live in sase bead doctor output. Phase 3 / sase-lc -> 6f3d84736: tri-state tree_dirty plus positive-proof _is_attributable_dirty_failure and an auditable excluded-count report. Phase 4 / sase-lw -> 517d09b71: registry snapshot cache keyed by store/project/root/freshness token with 30s TTL and write-side invalidation; benchmark warm p50 8.4ms vs the reported 400-800ms. Phase 5 / sase-mb -> 51ac2c683: deterministic operation bounds replace the 1.0s wall-clock assert with the 2000-request workload intact. Phase 6 / sase-mh -> 392dcc962: _bounded_publication_drain releases sase-agents-sync.lock and keeps the outbox request for retry. Phase 7 -> daf933aa5. RE-RAN AT HEAD daf933aa5: 381 focused tests green (stream integrity, agent_page_url, selection-health, all tests/agents_sync incl. bounded drain and large backlog, registry reservations, commit-finalizer publication); a diff-scoped lane escalated to the full suite and passed 30693 with 10 skipped and exactly one failure, tests/ace/tui/test_top_bar_order.py::test_override_pills_keep_narrow_top_bar_in_bounds, which is separately owned ready task sase-mp; every just check lint gate passes except lint(symvision) on FilesQueryIndexResult, which is separately owned ready task sase-mn and blocks the gate for every agent; just selection-health --fail-on-new-flake no longer names sase-lc's marker-audit node and exceeds baseline only on sase-mp and sase-j7 nodes. EPIC-CAUSED ISSUES RESOLVED: all 4 DISCOVERED ISSUE notes about 8 unused-public leftovers (StreamIntegrityResult, analyze_stream_against_ancestor, encode_stream_events, is_event_stream_relpath, parse_stream_text, clear_agent_page_url_registry_cache, PublicationDrainTimedOut, configured_publication_drain_timeout) are fixed -- symvision reports none of them, and there are no sase-mi epic-symbol whitelist entries to expire. The bead-store write wedge recorded here was root-caused and fixed outside this epic by tale 202608/bead_event_resolution_roundtrip.md (a non-round-trip-stable sase-core resolution field, not a real history rewrite); its residue is tracked as sase-mr, sase-ms, and sase-mu. INTEGRATION: commit ac5d95810 added tests/test_proc_submission_static_invariants.py, an AST audit over all of src/sase, after phase 3 curated _SOURCE_AUDIT_SCAN_ROOTS, so its dirty-tree failures could still have become shared flake debt; registered it with a regression test and added a guard test that fails if any registered audit file is renamed or split away. f935acace (rewrite-diff diagnosis) and daf933aa5 (privatization) already compose cleanly in _stream_integrity.py; no other post-epic commit duplicates or conflicts with this epic, and no new bead-store commit path bypasses the guard. FOLLOW-UPS: the only PROPOSED FOLLOW-UP acros

… and 1939 more characters

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-mi.1](sase-mi.1.md) | Audit and reconcile the ready task queue | ✓ closed | medium | 2026-08-15 | 1 | 0 |
| [sase-mi.2](sase-mi.2.md) | Protect append-only bead event streams | ✓ closed | medium | 2026-08-15 | 1 | 1 |
| [sase-mi.3](sase-mi.3.md) | Exclude attributable dirty-tree failures from flake debt | ✓ closed | medium | 2026-08-15 | 1 | 1 |
| [sase-mi.4](sase-mi.4.md) | Bound agent page-link resolution latency | ✓ closed | medium | 2026-08-15 | 1 | 1 |
| [sase-mi.5](sase-mi.5.md) | Stabilize the large publication backlog contract | ✓ closed | small | 2026-08-15 | 1 | 1 |
| [sase-mi.6](sase-mi.6.md) | Bound post-push agent publication | ✓ closed | medium | 2026-08-15 | 1 | 1 |
| [sase-mi.7](sase-mi.7.md) | Verify the combined tree and reconcile task beads | ✓ closed | medium | 2026-08-15 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-mi: High-impact task bead sweep [closed]"]
    n1["sase-mi.1: Audit and reconcile the ready task queue [closed]"]
    n2["sase-mi.2: Protect append-only bead event streams [closed]"]
    n3["sase-mi.3: Exclude attributable dirty-tree failures from flake debt [closed]"]
    n4["sase-mi.4: Bound agent page-link resolution latency [closed]"]
    n5["sase-mi.5: Stabilize the large publication backlog contract [closed]"]
    n6["sase-mi.6: Bound post-push agent publication [closed]"]
    n7["sase-mi.7: Verify the combined tree and reconcile task beads [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n1 -.-> n2
    n1 -.-> n3
    n1 -.-> n4
    n1 -.-> n5
    n2 -.-> n7
    n3 -.-> n7
    n4 -.-> n7
    n5 -.-> n6
    n5 -.-> n7
    n6 -.-> n7
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mi.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mi.1/README.md) | [sase-mi.1](sase-mi.1.md) | 0 |
| [bbugyi200.athena.sase-mi.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mi.2/README.md) | [sase-mi.2](sase-mi.2.md) | 1 |
| [bbugyi200.athena.sase-mi.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mi.3/README.md) | [sase-mi.3](sase-mi.3.md) | 1 |
| [bbugyi200.athena.sase-mi.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mi.4/README.md) | [sase-mi.4](sase-mi.4.md) | 1 |
| [bbugyi200.athena.sase-mi.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mi.5/README.md) | [sase-mi.5](sase-mi.5.md) | 1 |
| [bbugyi200.athena.sase-mi.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mi.6/README.md) | [sase-mi.6](sase-mi.6.md) | 1 |
| [bbugyi200.athena.sase-mi.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mi.7/README.md) | [sase-mi.7](sase-mi.7.md) | 1 |
| [bbugyi200.athena.sase-mi.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mi.land/README.md) | [sase-mi](README.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`517d09b`](https://github.com/sase-org/sase/commit/517d09b7107277354852b907f5b85ddcd11cb732) | perf(tui): cache agent page registry snapshots | [sase-mi.4](sase-mi.4.md) | 2026-08-15 20:59:21 EDT |
| sase | [`6f3d847`](https://github.com/sase-org/sase/commit/6f3d84736cff4592898545b58f519b12263a9072) | fix(selection-health): exclude attributable dirty-tree failures from flake debt | [sase-mi.3](sase-mi.3.md) | 2026-08-15 21:01:02 EDT |
| sase | [`51ac2c6`](https://github.com/sase-org/sase/commit/51ac2c683bec169435df78db70d022eb6208aacb) | test: stabilize publication backlog performance contract | [sase-mi.5](sase-mi.5.md) | 2026-08-15 21:27:34 EDT |
| sase | [`b681d1b`](https://github.com/sase-org/sase/commit/b681d1bc3dda0bdab25d8866da718267d1e4942a) | fix(beads): refuse append-only event-stream shrinks at commit and push | [sase-mi.2](sase-mi.2.md) | 2026-08-15 21:28:32 EDT |
| sase | [`392dcc9`](https://github.com/sase-org/sase/commit/392dcc962982ebf1458f10d21997341519c4ad90) | fix(agents-sync): bound the post-push agent-hood publication drain | [sase-mi.6](sase-mi.6.md) | 2026-08-15 22:22:44 EDT |
| sase | [`daf933a`](https://github.com/sase-org/sase/commit/daf933aa5aef62111343b94a1957ddc6fa605195) | fix(perf): group optional resolver spans in detail benchmark | [sase-mi.7](sase-mi.7.md) | 2026-08-15 23:55:20 EDT |
| sase | [`298cea9`](https://github.com/sase-org/sase/commit/298cea9665ed67dac6810e6cdbe40c80274f8782) | test(selection-health): register the proc-submission audit as a source-tree audit | [sase-mi](README.md) | 2026-08-16 00:24:01 EDT |
| sase--plans | [`sase--plans@e6293e4`](https://github.com/sase-org/sase--plans/commit/e6293e4c562a92cf2621b292d78b79a1c985b699) | docs(plans): mark high\_impact\_task\_bead\_sweep done | [sase-mi](README.md) | 2026-08-16 00:27:23 EDT |
