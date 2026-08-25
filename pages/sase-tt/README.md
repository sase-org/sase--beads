# Bead: sase-tt — Make Artifacts sub-tab queries fast, starting with the Agent pane

[Bead Pages](../README.md) / sase-tt

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0do](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0do.md) · **Assignee:** `sase-tt.land`
**Created:** 2026-08-25 14:59:11 EDT · **Closed:** 2026-08-25 19:55:47 EDT
**Plan:** [202608/artifacts\_query\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_query_performance.md)

## Description

Every Artifacts sub-tab paints its default `limit:100` view in well under half a second on a live-scale corpus, and the corpus work that only a wider query needs happens after first paint instead of before it.

## Notes

[2026-08-25T20:09:00Z · 0ds] INTEGRATION: epic sase-tw ("Artifact links that survive, derive themselves, and pay for
the turn", plan:202608/artifact_link_durability_and_derivation.md) was proposed 35
minutes after this epic, and its phase sase-tw.13 (agent-pane-filters) edits four of the
same files: src/sase/agents/catalog/_query.py,
src/sase/ace/tui/widgets/artifacts/query_rows.py,
src/sase/ace/tui/widgets/artifacts/agents_data.py, and src/sase/agents/cli_search.py.
Neither plan mentions the other. sase-tw.13 already carries a "do not start until
sase-tj.10 has landed" gate; it now also waits for this whole epic to land, and has been
told so on its own bead.

This epic lands first and owns the Agent pane's first-paint budget, so §2.1's ≤400ms
Agent target is a shared budget rather than a private one. sase-tw.13 adds a per-row
artifact-link facet join to agent_catalog_query_entry — the exact function sase-tt.5 is
shrinking — and has been told to re-run tests/perf/bench_artifacts_first_paint.py and
hold that number. See the note on sase-tt.8 for what that requires of the perf recipe.

One fact this epic's measured breakdown does not itemize: AgentsSnapshot already carries
an artifact_links: ArtifactLinksSnapshot field, and load_agents_snapshot already calls
load_artifact_links_snapshot(project) (agents_data.py:24-56). It is cheap today at 112
machine-global aggregate rows. Epic sase-tw's stated goal is ~1,600+ rows, so treat it
as a growing cost on the load path rather than a constant.

[2026-08-25T22:12:15Z · sase-tt.land] LAND IN PROGRESS (sase-tt.land, master f56cf4333 + uncommitted land diff).

VERIFIED (step 1): all 8 phases closed; read every child note and the epic's commits. Phase work confirmed in source: tt.1 bench (4fcd56796), tt.2 registry memo (fe663948f), tt.3 two-stage Agent pane (6ffdfb0a9), tt.4 direct dict-to-QueryRow in sase-core, tt.5 paired row/wire marshalling (e394b9d9c), tt.6 deferred plan metadata (446e9a43c), tt.7 deferred external-issue refresh (e234d5df9), tt.8 perf recipe (f56cf4333). Re-ran both benches on this checkout: bench_artifacts_first_paint first-paint p50 Agent 169.30ms (<=400), Bead 661.78ms (<=700), Plan 202.43ms (<=400), File 31.21ms (<=500) -- all four s2.1 targets met at p50; bench_agent_catalog 155ms median vs its 550ms budget. sase bead epic-symbols sase-tt: no entries.

EPIC-CAUSED REGRESSION FOUND AND FIXED (step 1). Phase tt.2 left two tests red on master, both in the file its own commit last touched, contradicting its plan section's explicit correctness bar ('the existing tests in tests/ covering registry staleness, rebuild, and reset_name_registry_caches_for_tests must pass unchanged'):
  - tests/test_agent_names_auto_name.py::TestGetNextAutoName::test_dotted_suffix_reserves_prefix -- the 2s stale-proof memo made get_next_auto_name() blind to artifact directories created after the memo was armed, so it returned an already-taken name ('0' instead of 'n'). That is a name-collision hazard, not just a test artifact.
  - tests/test_agent_name_registry_rebuild.py::test_stale_proof_memo_invalidated_by_mutation -- added by that same commit and failing since it landed (2 != 1); its 'arm the memo' line never armed it, because load_name_registry()'s rebuild branch returns before _record_stale_proof_memo().
FIX: reservation-facing queries (get_reserved_agent_names / get_reserved_clan_names / get_reserved_family_names / get_reserved_agent_name_map / is_name_reserved / lookup_registered_name / lowest_name_suggestion) now load through _load_registry_for_reservations(), which passes trust_stale_proof_memo=False and pays the full staleness proof; display reads (the Agent pane's load_name_registry) keep the memo. Perf unaffected: the pane path and bench_agent_catalog do not use those queries. Repaired the mutation test's false premise and added test_reservation_reads_skip_the_stale_proof_memo pinning the split. Considered and rejected arming the memo inside rebuild_name_registry: it breaks the pre-existing test_stale_index_rebuilds_when_owner_disappears contract.

ALSO ADDRESSED: phase tt.3's integration note item 2 asked for an explicit, code-recorded decision on whether the bounded head-slice pass populates AgentsSnapshot.artifact_links. It populates it; that decision, its measured basis, and its growth trigger are now recorded in agents_data.py. Note items 1 and 3 were already satisfied (tt.3 added no new visible affordance, so it does not contend for sase-tj.10.3's goldens; and _apply_agents_query_index / _filtered_agents_snapshot both refuse to present a full index over an incomplete snapshot). tests/perf/README.md's certified table labelled Bead and Plan 'missed' on a p95 reading of median targets; it now states the criterion and both readings, since sase-tw.13 is told to hold those numbers.

INTEGRATION (step 2): 7 non-epic commits landed in this window (sase-tw.1/.2/.3/.5/.11, the 0dt jump-targets plan, and the sase init memory regeneration). Zero file overlap with the epic's commits. No concurrent commit added a corpus/query-row producer that should adopt tt.5's paired marshalling -- it lives inside compile_artifact_query_index, which every pane already routes through. The four memory-shim PROPOSED FOLLOW-UPs (tt.2/tt.3/tt.6/tt.7) are resolved on master by a7478bdab: sase init memory --check exits 0 and test_init_memory_committed_drift passes. tt.4's floor-raise proposal was withdrawn by its own correction note (the release-branch reconciler owns the window). tt.8's remaining PROPOSED FOLLOW-UP nodes are not this epic's: test_artifact_cli_link_health now passes, and the completion-snapshot + test_artifact_handler failures were traced to sase-tw.5's commit 1282c7a8c (+1 recorded on task sase-pr, DISCOVERED ISSUE recorded on epic sase-tw).

REMAINING: just check-full over the combined tree, then close. just fmt, all 12 lint gates (incl. symvision), and SASE validation already pass on this tree.

[2026-08-25T22:42:13Z · 0dv] DISCOVERED ISSUE CORROBORATION: During bead_show_paging_and_multi_id verification on 2026-08-25, just check escalated to the governed full pytest lane and failed tests/test_agent_name_registry_rebuild.py::test_stale_proof_memo_invalidated_by_mutation and tests/test_agent_names_auto_name.py::TestGetNextAutoName::test_dotted_suffix_reserves_prefix. A focused rerun reproduced both deterministically with the same assertions recorded in note #2 on this active epic. The local diff is bead show paging/multi-ID/parser/docs/tests work and does not touch agent-name registry code. This corroborates the active epic-owned regression instead of creating a standalone task bead.

[2026-08-25T23:55:47Z · sase-tt.land--2] LANDED (sase-tt.land, master f56cf4333 + land diff).

STEP 1 VERIFY. All 8 phases closed; read every child note and every epic commit. Phase work confirmed in source: tt.1 bench (4fcd56796), tt.2 registry memo (fe663948f), tt.3 two-stage Agent pane (6ffdfb0a9), tt.4 direct dict-to-QueryRow in sase-core, tt.5 paired row/wire marshalling (e394b9d9c), tt.6 deferred plan metadata (446e9a43c), tt.7 deferred external-issue refresh (e234d5df9), tt.8 perf recipe (f56cf4333). Re-ran both benches on this checkout: bench_artifacts_first_paint p50 Agent 169.30ms (<=400), Bead 661.78ms (<=700), Plan 202.43ms (<=400), File 31.21ms (<=500) -- all four §2.1 targets met at p50; bench_agent_catalog 155ms median vs its 550ms budget.

EPIC-CAUSED REGRESSION FOUND AND FIXED. Phase tt.2 left two tests red on master, both in the file its own commit last touched, contradicting its plan section's correctness bar. The 2s stale-proof memo made get_next_auto_name() blind to artifact directories created after the memo was armed (returning an already-taken name -- a real name-collision hazard, not a test artifact), and the mutation test tt.2 shipped never armed the memo it claimed to test. FIX: reservation-facing queries now load through _load_registry_for_reservations() (trust_stale_proof_memo=False, full staleness proof); display reads keep the memo, so the pane path and bench_agent_catalog are unaffected. Repaired the mutation test's premise and added test_reservation_reads_skip_the_stale_proof_memo. Confirmed: 57 passed across tests/test_agent_name_registry_rebuild.py + tests/test_agent_names_auto_name.py. Also recorded tt.3's requested decision on AgentsSnapshot.artifact_links in agents_data.py, and corrected tests/perf/README.md's certified table (it labelled Bead/Plan "missed" on a p95 reading of median targets).

STEP 2 INTEGRATE. 7 non-epic commits landed in this window (sase-tw.1/.2/.3/.5/.11, the 0dt jump-targets tale, the sase init memory regeneration). Zero file overlap with the epic's commits. No concurrent commit added a corpus/query-row producer that should adopt tt.5's paired marshalling -- it lives inside compile_artifact_query_index, which every pane already routes through. The four memory-shim PROPOSED FOLLOW-UPs (tt.2/tt.3/tt.6/tt.7) are resolved on master by a7478bdab. tt.4's floor-raise proposal was withdrawn by its own correction note.

STEP 3 VERIFICATION AND TRIAGE. just fmt, all 12 lint gates (incl. symvision and toobig), SASE validation, and committed plans pass on this tree. Full test lane (monitor hxz0b4zxzgcw, 1h02m): 37073 passed, 4 failed, 13 skipped. tools/check_test_cost_budgets --report-advisories exits 0 (6 advisories, all wall-clock/contention, none gating).

  - 3 of the 4 failures (tests/completion/test_snapshot.py x2, tests/main/test_artifact_handler.py::test_public_long_options_are_alphabetical_and_have_short_aliases) were already red on clean master from commit 1282c7a8c (sase-tw.5 added `sase artifact link relation` without running just sync-completion-spec or updating a hardcoded assertion). Already on task sase-pr and as a DISCOVERED ISSUE on epic sase-tw. Not fixed here.
  - The 4th, tests/test_keymaps_display_help.py::test_all_tab_help_guides_show_forward_jump_and_agents_metadata_sections, is new and NOT caused by this epic. Traced t

… and 3643 more characters

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-tt.1](sase-tt.1.md) | Honest first-paint benchmarks for the Artifacts panes | ✓ closed | small | 2026-08-25 | 1 | 1 |
| [sase-tt.2](sase-tt.2.md) | Stop revalidating the agent-name registry on every load | ✓ closed | medium | 2026-08-25 | 1 | 1 |
| [sase-tt.3](sase-tt.3.md) | Two-stage Agent pane load | ✓ closed | medium | 2026-08-25 | 1 | 1 |
| [sase-tt.4](sase-tt.4.md) | Direct dict-to-QueryRow corpus construction in sase-core | ✓ closed | medium | 2026-08-25 | 1 | 1 |
| [sase-tt.5](sase-tt.5.md) | Cut the Python-side corpus marshalling cost | ✓ closed | medium | 2026-08-25 | 1 | 1 |
| [sase-tt.6](sase-tt.6.md) | Defer plan metadata reads past the inventory slice | ✓ closed | medium | 2026-08-25 | 1 | 1 |
| [sase-tt.7](sase-tt.7.md) | Take the external-issue network call off the Bead first-paint path | ✓ closed | medium | 2026-08-25 | 1 | 1 |
| [sase-tt.8](sase-tt.8.md) | End-to-end verification and the perf recipe | ✓ closed | small | 2026-08-25 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-tt: Make Artifacts sub-tab queries fast, starting with the Agent pane [closed]"]
    n1["sase-tt.1: Honest first-paint benchmarks for the Artifacts panes [closed]"]
    n2["sase-tt.2: Stop revalidating the agent-name registry on every load [closed]"]
    n3["sase-tt.3: Two-stage Agent pane load [closed]"]
    n4["sase-tt.4: Direct dict-to-QueryRow corpus construction in sase-core [closed]"]
    n5["sase-tt.5: Cut the Python-side corpus marshalling cost [closed]"]
    n6["sase-tt.6: Defer plan metadata reads past the inventory slice [closed]"]
    n7["sase-tt.7: Take the external-issue network call off the Bead first-paint path [closed]"]
    n8["sase-tt.8: End-to-end verification and the perf recipe [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n1 -.-> n2
    n1 -.-> n3
    n1 -.-> n4
    n1 -.-> n5
    n1 -.-> n6
    n1 -.-> n7
    n2 -.-> n8
    n3 -.-> n8
    n4 -.-> n8
    n5 -.-> n8
    n6 -.-> n8
    n7 -.-> n8
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tt.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tt.1/README.md) | [sase-tt.1](sase-tt.1.md) | 1 |
| [bbugyi200.athena.sase-tt.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-tt.2.md) | [sase-tt.2](sase-tt.2.md) | 1 |
| [bbugyi200.athena.sase-tt.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tt.3/README.md) | [sase-tt.3](sase-tt.3.md) | 1 |
| [bbugyi200.athena.sase-tt.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tt.4/README.md) | [sase-tt.4](sase-tt.4.md) | 1 |
| [bbugyi200.athena.sase-tt.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tt.5/README.md) | [sase-tt.5](sase-tt.5.md) | 1 |
| [bbugyi200.athena.sase-tt.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tt.6/README.md) | [sase-tt.6](sase-tt.6.md) | 1 |
| [bbugyi200.athena.sase-tt.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tt.7/README.md) | [sase-tt.7](sase-tt.7.md) | 1 |
| [bbugyi200.athena.sase-tt.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tt.8/README.md) | [sase-tt.8](sase-tt.8.md) | 1 |
| [bbugyi200.athena.sase-tt.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-tt.land.md) | [sase-tt](README.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4fcd567`](https://github.com/sase-org/sase/commit/4fcd56796af06c5d42611f9b94c2cc92ec8c3918) | test(perf): add first-paint bench for artifacts pane and dedupe agent-catalog bench helpers | [sase-tt.1](sase-tt.1.md) | 2026-08-25 15:46:55 EDT |
| sase | [`e234d5d`](https://github.com/sase-org/sase/commit/e234d5df9bd3422c6fa099bbd727ee90f54dac1a) | perf(beads): defer external issue refresh | [sase-tt.7](sase-tt.7.md) | 2026-08-25 16:23:47 EDT |
| sase | [`fe66394`](https://github.com/sase-org/sase/commit/fe663948fa8d495d3eda69d67a7dc7f0ae757f75) | perf(agent-names): memoize registry staleness checks | [sase-tt.2](sase-tt.2.md) | 2026-08-25 16:25:21 EDT |
| sase-core | [`sase-core@6e76e37`](https://github.com/sase-org/sase-core/commit/6e76e37df9905f3e1ebd2cef0dfd822ffd303e7e) | perf(query): build QueryRow directly from PyDict rows in compile\_corpus\_with\_profile | [sase-tt.4](sase-tt.4.md) | 2026-08-25 16:27:24 EDT |
| sase | [`6ffdfb0`](https://github.com/sase-org/sase/commit/6ffdfb0a97a976cdadaccf11c29595d5996d4a8f) | feat(artifacts): load agent pane in two stages | [sase-tt.3](sase-tt.3.md) | 2026-08-25 16:39:19 EDT |
| sase | [`446e9a4`](https://github.com/sase-org/sase/commit/446e9a43c359fc8ed943f29ab4eb24c91601dd21) | perf(plans): defer plan metadata reads past the inventory slice | [sase-tt.6](sase-tt.6.md) | 2026-08-25 16:40:29 EDT |
| sase | [`e394b9d`](https://github.com/sase-org/sase/commit/e394b9d9c062ee9b4e226442b201b0c598042890) | perf(query): reduce artifact row marshalling | [sase-tt.5](sase-tt.5.md) | 2026-08-25 16:55:27 EDT |
| sase | [`f56cf43`](https://github.com/sase-org/sase/commit/f56cf433328eea77e9d0a634fa41018cd2d34f58) | docs(perf): record artifacts first-paint verification | [sase-tt.8](sase-tt.8.md) | 2026-08-25 17:29:44 EDT |
| sase | [`5a1b886`](https://github.com/sase-org/sase/commit/5a1b8868335d8a183e4f6a0fe760efcb8fab9767) | fix(agent-names): pay the full staleness proof on reservation reads | [sase-tt](README.md) | 2026-08-25 19:59:16 EDT |
