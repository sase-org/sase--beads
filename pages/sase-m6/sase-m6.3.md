# Bead: sase-m6.3 — One typed entry target on every pane

[Bead Pages](../README.md) / [sase-m6](README.md) / sase-m6.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.01u](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.01u.md) · **Assignee:** `sase-m6.3` · **Size:** large
**Created:** 2026-08-14 17:05:39 EDT · **Closed:** 2026-08-14 19:56:14 EDT
**Plan:** [202608/artifacts\_pane\_contract.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_pane_contract.md)

## Description

identity: promote ArtifactEntryTarget to a typed value carrying pane identity with a canonical token round-trip, give Patch a row target and a real navigator, make ArtifactEntryNavigator an ABC, and retire index-based marks and jump anchors.

## Notes

[2026-08-14T23:56:14Z · sase-m6.3] Implemented artifact_entry_identity.md in full: typed ArtifactEntryTarget dataclass with token round-trip and legacy-tuple conversion; ArtifactEntryNavigator converted Protocol->ABC and implemented on every pane including Patches; request_entry_target()/conditional_footer_entries() added to Files/Stitches; marks moved to stable-target-keyed _artifacts_marked_targets map (marked_indices became a computed property); Patch jump anchors use ArtifactEntryTarget; @patch: reference copy target wired through keymap/registry/help. Verified: just install clean; just check fully green (all lint gates + mypy + scoped tests, which escalated to the full suite and passed); just check-full's lint gates and full test-cost suite all passed silently -- its only failure was the pre-existing selection-health --fail-on-new-flake gate, reproduced and corroborated on bead sase-lc (dirty-workspace flake-classification root cause), none of the 16 flagged nodes touch any file this plan changed. git diff --check clean; spot-checked for leftover marked_indices writes, getattr navigator fallbacks, and raw tuple targets -- none found outside the plan's acknowledged unrelated AXE index-navigation tuples.

## Dependencies

- **Depends on:** [sase-m6.1](sase-m6.1.md) ✓ · ⧖ 2026-08-14
- **Blocks:** [sase-m6.4](sase-m6.4.md) ◐ · ⧖ 2026-08-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m6.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.3.md) | [sase-m6.3](sase-m6.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`33180da`](https://github.com/sase-org/sase/commit/33180daf1e381f44a88a8825fa9e46d7c55b2228) | feat(ace): give every Artifacts pane a typed, serializable row identity | [sase-m6.3](sase-m6.3.md) | 2026-08-14 19:56:53 EDT |
