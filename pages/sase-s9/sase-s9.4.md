# Bead: sase-s9.4 — Procs pane filter session

[Bead Pages](../README.md) / [sase-s9](README.md) / sase-s9.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0bh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0bh.md) · **Assignee:** `sase-s9.4` · **Size:** medium
**Created:** 2026-08-23 08:01:37 EDT
**Plan:** [202608/procs\_filter.md](https://github.com/sase-org/sase--plans/blob/main/202608/procs_filter.md)

## Description

pane: wire `/` into the Procs pane -- a filter-session mixin that filters the rendered rows, keeps selection and jump hints stable, refreshes on output churn, honors `limit:`, and reports match counts, errors, and the no-match empty state.

## Dependencies

- **Depends on:** [sase-s9.3](sase-s9.3.md) ✓ · ⧖ 2026-08-23
- **Blocks:** [sase-s9.5](sase-s9.5.md) ◐ · ⧖ 2026-08-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-s9.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s9.4/README.md) | [sase-s9.4](sase-s9.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2e0ac0f`](https://github.com/sase-org/sase/commit/2e0ac0f37c0dafb6e5ef3afc2c213abae9058d15) | feat(ace): wire Procs filter bar into pane with empty-state and count messaging | [sase-s9.4](sase-s9.4.md) | 2026-08-23 10:40:57 EDT |
