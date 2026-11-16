# Bead: sase-1t3.7.1.2 — Discover after first paint and publish mounted generations coherently

[Bead Pages](../README.md) / [sase-1t3.7.1](sase-1t3.7.1.md) / sase-1t3.7.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t3.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.7.md) · **Assignee:** `sase-1t3.7.1.2` · **Size:** medium
**Created:** 2026-11-16 11:11:56 EST · **Closed:** 2026-11-16 17:43:15 EST
**Plan:** [202611/provider\_tab\_generation.md](https://github.com/sase-org/sase--plans/blob/main/202611/provider_tab_generation.md)

## Description

post-paint-publication: bootstrap fixed descriptors without discovery; schedule coalesced provider discovery after first paint; prepare missing panes and publish one complete generation on the UI thread. Preserve navigation, pane state, diagnostics, retry, and teardown behavior. Add delayed-discovery integration coverage and startup measurements, including the cold Agents identity path, and leave closure evidence for the land agent.

## Notes

[2026-11-16T22:24:20Z · sase-1t3.7.1.2] Phase work implemented; just check running as 4e3f310c000a5e9f5575e1aecb954a28 (selector escalated to full lane on environmental extension bucket). BOOTSTRAP: _state_init_late now builds bootstrap_artifacts_snapshot(gen 0, no project walk/token read/cache write) + publication state. DEFERRED DISCOVERY: new ArtifactsPublicationMixin (_artifacts_publication.py) scheduled once from _start_post_first_paint_services via thin sync callback; pump-free task runs worker body off-pump, one in-flight + one coalesced pending, rejects superseded epochs and post-teardown results; teardwon flag set in on_unmount. PUBLICATION: stage missing panes on UI thread (propagate keymap/scope/split/description), await mount, re-check generation/lifetime/scope/navigation, then synchronous commit (snapshot, view maps, tab strip, switcher, digit bindings rebuilt via keymap_registry.app, selection preserved by stable pane id with fallback to stitches + correct hooks, dead-pane removal by widget id, pending provider target applied or unavailable notice, help/palette refreshed preserving filter/selection, trace event artifacts.provider_publication). NAV: digits resolve only against committed generation and never replay; explicit provider id while pending retained once (cleared by later in-artifacts nav, scope change; tab switch away drops silently). VIEW: pending shown as dim ellipsis in existing Artifacts header spacer; degraded warning unchanged. TESTS: 15 new tests in tests/ace/tui/test_artifacts_post_paint_publication.py (real startup scheduling path, gated worker): bootstrap/discovery-free construction, render/catalog builders, first-paint-then-coherent-publication, hidden-agents startup, pending jump apply/supersede, dead digit, zero providers, retry-after-failure, removal fallback, teardown discard, open help refresh, cold identity, files flag x2. MEASUREMENTS (5 separate-process runs, PYTHONPATH=src, sha ab352aeeb consistent): import 1.73-1.85s, construction 0.76-0.80s with ZERO sync provider calls all runs, deferred worker 0.57-0.60s, cold identity 0.63-0.68s, warm <0.001s. Construction lost the ~0.6s discovery cost vs plan baseline; cold identity stays material and independent (follow-up, not expanded here). Fast-startup harness updated to pin bootstrap to fixture + suppress deferred discovery.

[2026-11-16T22:43:15Z · sase-1t3.7.1.2--1] Fixed E402 in src/sase/ace/testing/_startup.py (moved ArtifactsPublicationMixin import to top); ruff check src/ tests/ clean, 15/15 tests/ace/tui/test_artifacts_post_paint_publication.py pass. Phase verified: bootstrap snapshot with zero sync provider calls, deferred post-first-paint publication, 5-run startup measurements in bead note; no epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-1t3.7.1.1](sase-1t3.7.1.1.md) ✓ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.7.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.7.1.2.md) | [sase-1t3.7.1.2](sase-1t3.7.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7c68d18`](https://github.com/sase-org/sase/commit/7c68d1860cb6fa8b94a43cc77c8ce7672f90170e) | feat(artifacts): publish provider tabs after first paint as one coherent generation | [sase-1t3.7.1.2](sase-1t3.7.1.2.md) | 2026-11-16 17:45:49 EST |
