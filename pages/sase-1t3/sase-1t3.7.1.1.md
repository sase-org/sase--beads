# Bead: sase-1t3.7.1.1 — Pin Artifacts consumers to an explicit descriptor snapshot

[Bead Pages](../README.md) / [sase-1t3.7.1](sase-1t3.7.1.md) / sase-1t3.7.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t3.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.7.md) · **Assignee:** `sase-1t3.7.1.1` · **Size:** medium
**Created:** 2026-11-16 11:11:56 EST · **Closed:** 2026-11-16 16:33:59 EST
**Plan:** [202611/provider\_tab\_generation.md](https://github.com/sase-org/sase--plans/blob/main/202611/provider_tab_generation.md)

## Description

snapshot-consumers: introduce the TUI descriptor snapshot and pure lookup boundary; route bindings, Artifacts composition, help, command catalogs, and navigation through the app's committed snapshot. Keep discovery timing unchanged in this preparatory phase. Make command selections target stable pane IDs, preserve standalone synchronous discovery, and test isolation from a newer discovery-cache result.

## Notes

[2026-11-16T16:35:15Z · sase-1t3.7.1.1] Pinned Artifacts TUI consumers to an explicit ArtifactsDescriptorSnapshot. App init still discovers once and stores an immutable per-app snapshot; bindings, ArtifactsView, help, catalogs, navigation, quickstart, onboarding, clipboard, and availability read that snapshot. Catalog entries keep artifacts.<pane-id> identity and execute show_artifacts_pane by pane_id (digit is display-only); missing panes notify unavailable. AcePage/visual fast startup patch discover_artifacts_snapshot on artifact_tabs instead of five consumer resolvers. Tests cover cache isolation, two-app isolation, catalog pane_id vs digit, missing-pane notify, bootstrap/completed-zero/failed status, and AcePage fixture reduction. sase bead epic-symbols sase-1t3.7.1.1 is empty. Focused pytest of snapshot, help, catalog, copy, onboarding, and availability passed; just check is next via prepared completion.

[2026-11-16T17:04:14Z · sase-1t3.7.1.1--1] Recovery: just check failed on mypy assignment in tab_quickstart.py:159. Widened _content_cache_key to tuple[int, int, int | None] and read snapshot.generation directly. Focused pytest of snapshot/help/quickstart/agents pane passed; epic-symbols empty. Re-staging prepared just check.

[2026-11-16T17:16:26Z · sase-1t3.7.1.1--2] Recovery: just check failed on unused public next_artifacts_snapshot_generation in _artifact_tab_snapshot.py. Made it _next_artifacts_snapshot_generation (in-file only). just _lint-symvision passed; focused pytest of snapshot/help/quickstart/agents pane passed (33 tests); epic-symbols empty. Re-staging prepared just check.

[2026-11-16T17:45:30Z · sase-1t3.7.1.1--3] Recovery: just check failed with 2 NEW scoped tests. Allowlisted _artifact_tab_snapshot.py on the ref-prefix dispatch contract (identity lookup, not pane dispatch). AcePage palette catalog now passes the committed snapshot. Marking mock accepts snapshot=. Gate origin-retention test disables held-claim TTL so a 2026-11-02 fixture stamp cannot age past the 14-day default. Focused pytest of contract, marking, scaffold, origin-retention, and snapshot tests passed (14). Re-staging prepared just check.

[2026-11-16T18:54:14Z · sase-1t3.7.1.1--4] Recovery: prepared just check timed out at 1h during lint (mypy incomplete). rust-install spent 17m 40s compiling sase_core_rs, then model-policy took 13m 28s under loadavg ~25. Tests never started. No NEW product failure. rust wheel is now cached. Re-staging prepared just check with a 2h budget and accept: no-new.

[2026-11-16T19:12:49Z · sase-1t3.7.1.1--5] Recovery: just check failed epic-symbol freshness (stale_checkout) for three closed sase-1t3.6.1.2 rows inherited from HEAD dc09b5eba3 while origin 8a1b84b096 had dropped them in e1d81ee6c6. Fast-forwarded master onto origin, reapplied snapshot-consumers work. Kept upstream origin-retention local_now() fix; dropped the local TTL=0 workaround. Catalog merged hijack options with show_artifacts_pane sources. epic-symbol freshness now exits 0; this bead has no --epic-symbol rows. Re-staging prepared just check.

[2026-11-16T21:29:42Z · sase-1t3.7.1.1--7] in_progress --status -n Recovery: just check had no NEW failures (2 KNOWN, 1 FLAKY) but host completion refused no_new_incomplete_coverage:sase-core. sase check fingerprints only the primary repo, so a covering no-new receipt cannot include the sibling. sase-core just check now passes (1fefcec24edbf1323e63b1b45c1d3542) after schema-4 corpus compile plus clippy needless_bool reductions on master. Landing both via unverified host commit; host commits sase-core first and ratchets sase-core-revision.txt.

PROPOSED FOLLOW-UP: add sase-core to the sase check tool fingerprint.repos so no-new prepared completion can cover a dirty pinned sibling.

[2026-11-16T21:33:59Z · sase-1t3.7.1.1--7] Closed by explicit `sase stitch create -B close` after create_commit landed 1bd855256e ("feat(ace): pin Artifacts consumers to a descriptor snapshot"). The commit author requested bead completion after verifying the bead scope. Reopen with `sase bead open sase-1t3.7.1.1` if more work remains.

## Dependencies

- **Blocks:** [sase-1t3.7.1.2](sase-1t3.7.1.2.md) ✓ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.7.1.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.7.1.1.md) | [sase-1t3.7.1.1](sase-1t3.7.1.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@a2abeb1`](https://github.com/sase-org/sase-core/commit/a2abeb1e1b1905780bcd554f55989114c3995292) | fix(agent-archive): compile corpus against current store schema | [sase-1t3.7.1.1](sase-1t3.7.1.1.md) | 2026-11-16 16:31:40 EST |
| sase | [`1bd8552`](https://github.com/sase-org/sase/commit/1bd855256e1b8c00917caa113f7a0aadb4a467ea) | feat(ace): pin Artifacts consumers to a descriptor snapshot | [sase-1t3.7.1.1](sase-1t3.7.1.1.md) | 2026-11-16 16:33:04 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1t3.7.1.1--7][1] | Need assigned bead scope before diagnosing incomplete sase-core coverage and finishing snapshot-consumers | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.7.1.1.md

<!-- sase:referenced-by:end -->
