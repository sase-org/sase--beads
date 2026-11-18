# Bead: sase-1t3.10.1.4 — Bound snapshot and detail retention and measure the result

[Bead Pages](../README.md) / [sase-1t3.10.1](sase-1t3.10.1.md) / sase-1t3.10.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t3.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.10.md) · **Assignee:** `sase-1t3.10.1.4` · **Size:** medium
**Created:** 2026-11-17 12:28:10 EST · **Closed:** 2026-11-18 11:10:34 EST
**Plan:** [202611/slim\_agent\_list\_rows.md](https://github.com/sase-org/sase--plans/blob/main/202611/slim_agent_list_rows.md)

## Description

bounded-retention: retain one compact artifact snapshot generation, release obsolete wire and detail payloads, add ownership regression tests, and record comparable load and heap measurements. Prepare evidence for this child epic's land agent to complete sase-1t3.10; do not close an ancestor as a phase worker.

## Notes

[2026-11-18T16:03:33Z · sase-1t3.10.1.4] LAND EVIDENCE (bounded-retention): one compact generation + bounded selected detail.

What changed (completed tree vs base HEAD 637a70a0f1, sase-core pin 71c59dca unchanged):
- src/sase/ace/tui/models/_agent_loader_artifact_cache.py: cache is now one retained generation (max_entries 1, generic over snapshot type). ARTIFACT_SNAPSHOT_CACHE is compact-only; the legacy full-shape index path owns FULL_ARTIFACT_SNAPSHOT_CACHE so a full read can never evict the live compact generation. Same-key lock-busy stale reads still serve the one stale generation; different keys miss; mutation-refusal and bypass behavior preserved.
- src/sase/ace/tui/models/_agent_loader_artifact_index.py: legacy full path rewired to FULL_ARTIFACT_SNAPSHOT_CACHE (alias, behavior identical).
- src/sase/ace/tui/models/_projected_record.py: new bounded selected-detail owner (bound 2: current + previous selection, weakrefs only so roster replacement stays collectible). hydrate_projected_agent stashes pre-hydration list facts and registers the generation; the oldest generation is restored to compact list facts on eviction. Full record trees stay transient in the hydrating worker. New public seams release_projected_agent_detail + projected_detail_owner_size (epic-symbols keyed to sase-1t3.10.1 for the land agent).
- src/sase/ace/tui/util/_gc_policy_config.py: watchlist entry corrected to the defining module sase.core.agent_scan_wire_records.AgentArtifactRecordWire (was the sase.core.agent_scan_wire re-export, which never matches gc type keys); added sase.core.agent_scan_list_wire.AgentArtifactListRecordWire so the census tracks the retained compact representation.
- Justfile: two --epic-symbol rows keyed to sase-1t3.10.1 for the new seams. No --epic-symbol entries remain on sase-1t3.10.1.4 itself.
- tests/ace/tui/models/test_projected_detail_retention.py (new, 6 tests): single-generation cache retention/eviction, same-key-only stale lock-busy, no full-record decode on list paths, 20-selection detail bound, release restores list facts + re-hydration, orphaned generations collectible. Existing full-path cache tests re-keyed to FULL_ARTIFACT_SNAPSHOT_CACHE (behavior contract unchanged).

Measurements (identical fixture workload, /tmp/measure_retention.py, 200 compact rows, ~578KB binding payload, before=base HEAD / after=completed tree):
- cache after 20 generation changes: before 6 entries/1200 records retained, 14 hits; after 1 entry/200 records, 19 evictions. Warm same-key repeat still hits (unit test).
- detail after 20 selections w/ ~100KB outputs: before 20 hydrated retained / 2,080,000 detail bytes; after 2 retained / 208,000 bytes. Zero full Python wire records retained in both.
- decode 5x200 rows: before 1.61s / after 1.55s (load path unchanged).
Real-data smoke (separate process, completed tree, real 375MB index): cold Tier-1 2.03s, warm 0.27-0.39s (25/50 rows); after 10 alternating refreshes cache holds 1 entry/103 records; 7 real rows hydrated with owner size 2 and zero retained full records; RSS 64 -> 242.8MB across loads, flat across hydration. gen-2 pause timing not sampled headless; interactive j/k responsiveness is deferred to the sase-1t3.14 soak, which owns it.
Gate: sase tool run check lint stages all green incl. symvision; diff-scoped test lane joined to monitor for completion.

[2026-11-18T16:10:34Z · sase-1t3.10.1.4--1] Verified: sase tool run check green (lint incl. symvision + diff-scoped test lane); one-generation compact cache and bounded selected-detail owner covered by tests/ace/tui/models/test_projected_detail_retention.py and the before/after measurements in the bead land-evidence note.

## Dependencies

- **Depends on:** [sase-1t3.10.1.3](sase-1t3.10.1.3.md) ✓ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.10.1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.10.1.4.md) | [sase-1t3.10.1.4](sase-1t3.10.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fbc1e34`](https://github.com/sase-org/sase/commit/fbc1e34fbcc4dc7b7636bd10fc02b4f791991830) | perf(tui): bound snapshot and detail retention to one compact generation | [sase-1t3.10.1.4](sase-1t3.10.1.4.md) | 2026-11-18 11:07:35 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1t3.10.1.3--1][1] | check next phase status for re-key | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.10.1.3.md

<!-- sase:referenced-by:end -->
