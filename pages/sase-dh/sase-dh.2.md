# Bead: sase-dh.2 — Local .sase/artifacts staging at prompt launch

[Bead Pages](../README.md) / [sase-dh](README.md) / sase-dh.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rh/README.md) · **Assignee:** `sase-dh.2` · **Size:** medium
**Created:** 2026-08-01 15:06:32 UTC · **Closed:** 2026-08-01 16:22:00 UTC
**Plan:** [202608/artifact\_persistence\_sidecars.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_persistence_sidecars.md)

## Description

stage: capture every prompt artifact reference into the content-addressed .sase/artifacts pool, move .sase/home under it, and record one manifest row per reference.

## Notes

[2026-08-01T16:07:57Z · sase-dh.2] PROPOSED FOLLOW-UP: Fix existing Symvision private-import violation — `_hierarchical_id_key` is imported by `src/sase/ace/tui/widgets/artifacts/bead_plan_links.py`, causing `just check` to stop before tests; this phase does not touch either side of that import.

[2026-08-01T16:13:51Z · sase-dh.2] PROPOSED FOLLOW-UP: Reconcile existing ACE Artifacts-pane tests and PNG goldens with the new Beads/files layout — full `just test` passes 24,953 tests but 307 existing TUI cases still expect PR-first navigation/onboarding and old snapshots; no staging-phase file changes overlap the ACE TUI.

[2026-08-01T16:22:00Z · sase-dh.2] Implemented Rust-backed prompt artifact staging for artifact and plain file references, content-addressed pooling, VCS clean/dirty classification, size caps, append-locked manifests, terminal-published pool GC, .sase/artifacts/home relocation, and stale .sase/home doctor reporting. Verified 136 focused tests, full Ruff, full mypy, and git diff checks pass. just check reaches only the pre-existing Symvision private-import failure noted on this bead; the full suite's unrelated stale ACE failures are also recorded as a proposed follow-up.

[2026-08-01T16:23:44Z · sase-dh.2] Implemented Rust-backed prompt artifact staging for artifact and plain file references, content-addressed pooling, VCS clean/dirty classification, size caps, append-locked manifests, terminal-published pool GC, .sase/artifacts/home relocation, and stale .sase/home doctor reporting. Verified 136 focused tests, full Ruff, full mypy, and git diff checks pass. just check reaches only the pre-existing Symvision private-import failure noted on this bead; the full suite's unrelated stale ACE failures are also recorded as a proposed follow-up.

## Dependencies

- **Depends on:** [sase-dh.1](sase-dh.1.md) ✓
- **Blocks:** [sase-dh.3](sase-dh.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-dh.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dh.2/README.md) | [sase-dh.2](sase-dh.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`24432d9`](https://github.com/sase-org/sase/commit/24432d9d50246e39109dcb0468816f98dbd7635c) | feat(artifacts): stage prompt references for durable capture | [sase-dh.2](sase-dh.2.md) | 2026-08-01 16:24:55 |
