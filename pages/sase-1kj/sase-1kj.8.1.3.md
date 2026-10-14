# Bead: sase-1kj.8.1.3 — Route link chips and Patch projections through the shared native handle

[Bead Pages](../README.md) / [sase-1kj.8.1](sase-1kj.8.1.md) / sase-1kj.8.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1kj.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kj.8.md) · **Assignee:** `sase-1kj.8.1.3` · **Size:** medium
**Created:** 2026-10-13 17:50:22 EDT · **Closed:** 2026-10-13 20:57:51 EDT
**Plan:** [202610/artifact\_link\_inverted\_index.md](https://github.com/sase-org/sase--plans/blob/main/202610/artifact_link_inverted_index.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:adbc4a4bfd916ef633b7c1a7 | attached via sase artifact create --bead |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

<!-- sase:links:end -->

## Description

python-integration: install the thin single-flight adapters, preserve Patch deferral, remove the Python aggregate walks, verify the source pin and parity, and measure the improvement.

## Notes

[2026-10-14T00:46:28Z · sase-1kj.8.1.3] PROPOSED FOLLOW-UP: instruction_manifest wire mismatch — tests/core/test_instruction_manifest.py::test_schema_version_matches_binding fails (core checkout reports 2, sase pins 1); neither file is in this phase diff, fails identically on clean base; no tracking bead found

[2026-10-14T00:46:32Z · sase-1kj.8.1.3] PROPOSED FOLLOW-UP: TUI import budget still over cap (3519 vs 3513) — already tracked by sase-1kk.5/sase-1kk (reproduced on clean base at 3517); this phase contributes the 2 attributed modules sase.ace.tui.relations._native_link_index and sase.core.artifact_link_index_facade, cap still needs ratchet

[2026-10-14T00:46:37Z · sase-1kj.8.1.3] PROPOSED FOLLOW-UP: three parallel-lane flakes pass in isolation but failed in the 15-min check lane (test_registry_rebuild_keeps_live_identity_pending_claim, test_reporter_dev_command_runner_recovers_abandoned_ff_lock, test_ace_page_real_startup_policy_invokes_production_boundaries); unrelated to artifact-link files, likely load flakes

[2026-10-14T00:57:51Z · sase-1kj.8.1.3] python-integration done. Adapters: new src/sase/core/artifact_link_index_facade.py (typed binding adapter) and src/sase/ace/tui/relations/_native_link_index.py (single-flight shared handle, 8-scope LRU, synthetic-id cache, seq-guarded publish, links.index_build span); link chips lazy per-ref (128-cap) via shared handle; artifact_link_edges via indexed project; Patch memo single-flight with exact counting; lifecycle clears handle cache; pin ratcheted to daad8f26. Parity: fixture goldens green; real 41295-row aggregate CHIP_DIFFS=0/PATCH_DIFFS=0 (evidence file:explicit:adbc4a4bfd916ef633b7c1a7). Timings (wall/cpu, loadavg~7): shared cold 1.40/1.40 (was 2.04), selected 9-ref queries 0.025/0.025 (was 0.212), shared Patch projection 0.098/0.098 (was 0.574), warm ~1e-4, combined ~1.52s vs ~2.83s; full materialization 3.58s is test-only eager cost, not production. Tests: 101 focused pass; sase check 55590 pass/5 fail (3 load flakes pass isolated; import-budget over cap tracked by sase-1kk.5 and instruction_manifest v2-vs-1 pre-existing, follow-ups noted). Core co-change (declare both repos, commit core first): deterministic row-order alias pass in index/compile.rs + regression test; core check green. No epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-1kj.8.1.2](sase-1kj.8.1.2.md) ✓ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kj.8.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kj.8.1.3/README.md) | [sase-1kj.8.1.3](sase-1kj.8.1.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@d776d75`](https://github.com/sase-org/sase-core/commit/d776d751046f26c212898a8520d9eccc9028e1a0) | fix(artifact-link-index): resolve colliding alias spellings in deterministic row order | [sase-1kj.8.1.3](sase-1kj.8.1.3.md) | 2026-10-13 20:59:18 EDT |
| sase | [`1625268`](https://github.com/sase-org/sase/commit/16252682b27e345d2b061923835c4a98fbada5ed) | feat(artifact-links): route link chips and patch projections through shared native handle | [sase-1kj.8.1.3](sase-1kj.8.1.3.md) | 2026-10-13 21:30:17 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1kj.8.1.3][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kj.8.1.3/README.md

<!-- sase:referenced-by:end -->
