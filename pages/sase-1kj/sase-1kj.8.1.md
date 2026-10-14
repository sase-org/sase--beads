# Bead: sase-1kj.8.1 — Move artifact-link indexing into the Rust core

[Bead Pages](../README.md) / [sase-1kj.8](sase-1kj.8.md) / sase-1kj.8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1kj.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kj.8.md) · **Assignee:** `sase-1kj.8.1.land`
**Created:** 2026-10-13 17:50:21 EDT · **Closed:** 2026-10-14 00:13:32 EDT
**Plan:** [202610/artifact\_link\_inverted\_index.md](https://github.com/sase-org/sase--plans/blob/main/202610/artifact_link_inverted_index.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/artifact_link_inverted_index.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | file:explicit:405b9f024864d71654e1cb54 | attached via sase artifact create --bead |

_Plus 4 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/artifact_link_inverted_index.md

<!-- sase:links:end -->

## Description

Complete sase-1kj.8 with one shared native index, lazy link chips, and indexed Patch projections while preserving current behavior

## Notes

[2026-10-14T01:51:24Z · sase-1kj.8.1.land] LANDING AUDIT / FOLLOW-UP TRIAGE (before repair tale proposal): Read this epic, all three children and every note, linked plan and parent phase/DECISIONS; reviewed sase bad0d0ac36 and 16252682b2, core daad8f26 and d776d751, and all non-epic commits since baseline through d69cd499dd. Core pin d776d751 includes native index and manifest v2; retain sec_45. Fixtures pass; real-data evidence hashes match with CHIP_DIFFS=0/PATCH_DIFFS=0, noting real input has zero Patch edges and full eager materialization still costs 3.58s. Fresh focused run: 54 passed, 1 failed (3521 imports vs strict cap 3520). No epic-symbol entries for this epic or parent phase sase-1kj.8. Evidence: file:explicit:405b9f024864d71654e1cb54 includes source review and deterministic reproducers.

Remaining epic work, planned as one medium tale: restore Rust tolerant uses/string parity (True/2.9/1_000 incorrectly become zero); move all cold lazy LinkSubject queries to workers and retain bounded requested-chip caches; fence stale native builds after scope eviction/clear; count both successful out-of-order Patch builds (currently two count as one); defer the two native modules this epic adds to first-paint imports. Keep the plural-label and Patch apply/refresh split changes. Do not close until repaired and fresh wrapped checks finish.

Every PROPOSED FOLLOW-UP disposition: .1 note #2 stale sase-1kj.7 whitelist is already removed and its counter is consumed by startup telemetry; declined new task as resolved. .3 note #1 instruction_manifest v2/v1 mismatch is fixed by 96090a52cf and its test passes; declined new task as resolved. .3 note #2 baseline import overage corroborated existing sase-1ic (+1); this epic own +2 modules (confirmed by import-closure diff) remain repair work, not follow-up. .3 note #3 registry flake corroborated exact existing sase-1em (+1); reporter abandoned index.lock flake corroborated shared stale-lock recovery task sase-1kr (+1) with permission-denied /proc evidence; AcePage missing update-check boundary routed as DISCOVERED ISSUE to active containing epic sase-1kj because phase .6 introduced sequential startup maintenance (not duplicate sase-1kf). All three nodes passed focused reruns. Additional audit discovery: later finalizer ToolRun f85ceff9dc8b864503dedc497ce70514 has 267 failures rather than the earlier five; its finalizer-env guard cluster corroborates sase-19g (+1). Not every failure in that later run is classified; repair must verify its own current gate result. No new tasks created because all unresolved out-of-scope issues have existing or active-epic owners. Include these outcomes and repair evidence in eventual close note. Tale must close this epic normally, run just symvision, mark plan:202610/artifact_link_inverted_index.md done, then verify and normally close only parent phase sase-1kj.8; leave sase-1kj for its lander.

[2026-10-14T04:13:32Z · sase-1kj.8.1.land] Implemented the approved artifact-link landing repairs across sase and linked sase-core. Core now preserves legacy Python string/count coercion semantics for artifact-link rows, with Rust and PyO3 regression coverage. The TUI uses deferred core imports, a per-ref bounded chip cache and event coalescing, worker-captured style context, async cold per-ref queries, selected-ref capture on the UI thread, race/generation guards, and cleanup on teardown. Native pending-build fences now avoid permanent tombstones; Patch full-build counters and clear epochs are covered by tests. Lazified agent-scan facade implementation imports to keep the TUI import closure at 3519 modules, equal to baseline. Rebuilt the local extension and ran just fmt successfully. Focused artifact-link, parity, pager, import-budget, facade, and related tests passed 135/135. The linked sase-core wrapped check passed. The main wrapped check e3290324a8eee4f12f8877a8d66b4b99 exited 1 after 24630 passed and 12 skipped; its sole failure was tests/instructions/test_delivery_plan.py::test_render_failure_notifies_once, independently reproduced unchanged and routed to active epic sase-1ko because its test monkeypatch targets _instruction_boundary while the implementation imports from instruction_delivery. Two Symvision findings were KNOWN from prior evidence. The core-floor probe is advisory and did not change the gate outcome. Re-audited the saved 41295-row aggregate: hash 6907c9500c61e00055a6cb2ebbe2b4b3ee5dd80f1e8383803736e8fb8e0a48fe; zero chip diffs under the saved style context and zero Patch diffs. Current live research-provider descriptor styling changes icon/accent only. Current sampled timings: cold build 1.88s, eager consumption 2.62s, representative queries 15ms, public cold 1.34s, warm hit 5ms; Patch projection measured 1.36s and includes first handle/index construction, so it is not a pure query measurement. Timing varies by capture and the combined eager work remains material. Existing follow-up dispositions reviewed and retained; delivery-plan fallback issue recorded on sase-1ko. Leave containing epic sase-1kj open.

[2026-10-14T05:19:39Z · sase-1kj.8.1.land--3] FINAL VERIFICATION (2026-10-14): Completed the Rust legacy-coercion parity, lazy worker-side LinkSubject chip queries with a bounded cache, stale-build/clear epoch fences, successful Patch build counting, and import-budget repair. The focused suite passed 121 tests; Symvision passed, and final wrapped `sase tool run check` ToolRun 19d6fee23156d49850d24ea226393ad9 passed (verdict pass). Parity evidence remains the saved 41,295-row aggregate (hash 6907c9500c61e00055a6cb2ebbe2b4b3ee5dd80f1e8383803736e8fb8e0a48fe), with zero chip and Patch diffs. Sample timings were 1.88s cold build, 2.62s eager consumption, 15ms representative queries, 1.34s public cold, 5ms warm hit, and 1.36s Patch projection including first handle/index construction; timings vary by capture and combined eager work remains material. Follow-up dispositions stand: stale .7 whitelist removed; manifest mismatch fixed; import overage covered by sase-1ic plus this repair; registry and lock flakes routed to sase-1em/sase-1kr; AcePage update-check retained on active epic sase-1kj; finalizer guard corroborated sase-19g; delivery-plan fallback remains with active sase-1ko. No duplicate beads were created.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kj.8.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kj.8.1.land.md) | [sase-1kj.8.1](sase-1kj.8.1.md) | 3 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@b2b6626`](https://github.com/sase-org/sase-core/commit/b2b662664d64b7e42c770ab04b9f27291b18b6bd) | fix(artifact-link): preserve legacy coercion in native index | [sase-1kj.8.1](sase-1kj.8.1.md) | 2026-10-14 01:20:55 EDT |
| sase | [`e07c600`](https://github.com/sase-org/sase/commit/e07c6007c3a3b52306e3d60c9cf90492ddbea5a4) | feat(artifact-links): finish indexed queries and verification repairs | [sase-1kj.8.1](sase-1kj.8.1.md) | 2026-10-14 01:50:40 EDT |
| sase--plans | [`sase--plans@64277bd`](https://github.com/sase-org/sase--plans/commit/64277bd74d50d4d81d030f6be7e3c01266a358a5) | docs(plan): record artifact-link inverted index plan | [sase-1kj.8.1](sase-1kj.8.1.md) | 2026-10-14 01:56:11 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1kj.8.1.1][1] | Need parent epic DECISIONS and phase split | 1 |
| read-by | [agent:sase-1kj.8.1.2][2] | Need DECISIONS, prior notes, and parent epic context | 1 |
| read-by | [agent:sase-1kj.8.1.3][3] | Need parent epic decisions and scope | 1 |
| read-by | [agent:sase-1kj.8.1.land--3][4] | Verify the appended final evidence note and closed status | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kj.8.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kj.8.1.2/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kj.8.1.3/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kj.8.1.land.md

<!-- sase:referenced-by:end -->
