# Bead: sase-m6.4 — ArtifactsPaneContract and derived, explainable capabilities

[Bead Pages](../README.md) / [sase-m6](README.md) / sase-m6.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.01u](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.01u.md) · **Assignee:** `sase-m6.4` · **Size:** large
**Created:** 2026-08-14 17:05:46 EDT · **Closed:** 2026-08-14 21:16:50 EDT
**Plan:** [202608/artifacts\_pane\_contract.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_pane_contract.md)

## Description

contract: introduce ArtifactsPaneContract with a closed PaneCapability vocabulary derived from declared data by named auditable rules, collapse every ref-prefix dispatch site onto it, and add the synthetic third-party provider fixture.

## Notes

[2026-08-15T01:16:50Z · sase-m6.4--1] Artifacts pane contract shipped: immutable ArtifactsPaneContract with named ON/OFF derivation rules; descriptors attach one contract; ArtifactsSnapshotPane shared loader; behavioral TUI no longer dispatches on ref: prefix; sase artifact pane show explains verdicts in text/JSON; synthetic schema-v1 notes fixture earns only fact-derived generic document capabilities. Verified: just check-full passed (NO_COLOR=1, monitor y3wtfde1hqm9, ~11m, exit 0); focused suite 63 passed (artifacts_contract, test_artifact_pane, test_artifacts_snapshot_pane). SASE_TUI_PERF=1 j/k bench not run.

## Dependencies

- **Depends on:** [sase-m6.2](sase-m6.2.md) ✓ · ⧖ 2026-08-14
- **Depends on:** [sase-m6.3](sase-m6.3.md) ✓ · ⧖ 2026-08-14
- **Blocks:** [sase-m6.5](sase-m6.5.md) ✓ · ⧖ 2026-08-14
- **Blocks:** [sase-m6.6](sase-m6.6.md) ◐ · ⧖ 2026-08-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m6.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.4.md) | [sase-m6.4](sase-m6.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7060a2e`](https://github.com/sase-org/sase/commit/7060a2ec45dc8a89f6f29b72e9555259103259e7) | feat(tui): drive Artifacts panes from a derived host contract | [sase-m6.4](sase-m6.4.md) | 2026-08-14 21:17:24 EDT |
