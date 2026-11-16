# Bead: sase-1t3.7.1.1 — Pin Artifacts consumers to an explicit descriptor snapshot

[Bead Pages](../README.md) / [sase-1t3.7.1](sase-1t3.7.1.md) / sase-1t3.7.1.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t3.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.7.md) · **Assignee:** `sase-1t3.7.1.1` · **Size:** medium
**Created:** 2026-11-16 11:11:56 EST
**Plan:** [202611/provider\_tab\_generation.md](https://github.com/sase-org/sase--plans/blob/main/202611/provider_tab_generation.md)

## Description

snapshot-consumers: introduce the TUI descriptor snapshot and pure lookup boundary; route bindings, Artifacts composition, help, command catalogs, and navigation through the app's committed snapshot. Keep discovery timing unchanged in this preparatory phase. Make command selections target stable pane IDs, preserve standalone synchronous discovery, and test isolation from a newer discovery-cache result.

## Notes

[2026-11-16T16:35:15Z · sase-1t3.7.1.1] Pinned Artifacts TUI consumers to an explicit ArtifactsDescriptorSnapshot. App init still discovers once and stores an immutable per-app snapshot; bindings, ArtifactsView, help, catalogs, navigation, quickstart, onboarding, clipboard, and availability read that snapshot. Catalog entries keep artifacts.<pane-id> identity and execute show_artifacts_pane by pane_id (digit is display-only); missing panes notify unavailable. AcePage/visual fast startup patch discover_artifacts_snapshot on artifact_tabs instead of five consumer resolvers. Tests cover cache isolation, two-app isolation, catalog pane_id vs digit, missing-pane notify, bootstrap/completed-zero/failed status, and AcePage fixture reduction. sase bead epic-symbols sase-1t3.7.1.1 is empty. Focused pytest of snapshot, help, catalog, copy, onboarding, and availability passed; just check is next via prepared completion.

[2026-11-16T17:04:14Z · sase-1t3.7.1.1--1] Recovery: just check failed on mypy assignment in tab_quickstart.py:159. Widened _content_cache_key to tuple[int, int, int | None] and read snapshot.generation directly. Focused pytest of snapshot/help/quickstart/agents pane passed; epic-symbols empty. Re-staging prepared just check.

[2026-11-16T17:16:26Z · sase-1t3.7.1.1--2] Recovery: just check failed on unused public next_artifacts_snapshot_generation in _artifact_tab_snapshot.py. Made it _next_artifacts_snapshot_generation (in-file only). just _lint-symvision passed; focused pytest of snapshot/help/quickstart/agents pane passed (33 tests); epic-symbols empty. Re-staging prepared just check.

[2026-11-16T17:45:30Z · sase-1t3.7.1.1--3] Recovery: just check failed with 2 NEW scoped tests. Allowlisted _artifact_tab_snapshot.py on the ref-prefix dispatch contract (identity lookup, not pane dispatch). AcePage palette catalog now passes the committed snapshot. Marking mock accepts snapshot=. Gate origin-retention test disables held-claim TTL so a 2026-11-02 fixture stamp cannot age past the 14-day default. Focused pytest of contract, marking, scaffold, origin-retention, and snapshot tests passed (14). Re-staging prepared just check.

## Dependencies

- **Blocks:** [sase-1t3.7.1.2](sase-1t3.7.1.2.md) ◐ · ⧖ 2026-11-16
