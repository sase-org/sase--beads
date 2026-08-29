# Bead: sase-vd.5 — Coverage for the one-workspace invariant

[Bead Pages](../README.md) / [sase-vd](README.md) / sase-vd.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ft](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ft.md) · **Assignee:** `sase-vd.5` · **Size:** small
**Created:** 2026-08-28 18:06:21 EDT · **Closed:** 2026-08-28 21:27:24 EDT
**Plan:** [202608/one\_workspace\_per\_agent\_family.md](https://github.com/sase-org/sase--plans/blob/main/202608/one_workspace_per_agent_family.md)

## Description

one-workspace-invariant-coverage: add a doctor check that reports any single live pid holding more than one numbered RUNNING claim for a project, plus regression tests that replay the incident shape -- a gate-shell follow-up carrying `#gh:`, a monitor handoff, and a subsequent pool allocation -- and assert exactly one numbered claim per runner and no release of a checkout whose family is still live.

## Notes

[2026-08-29T01:27:24Z · sase-vd.5] Implemented multi-workspace live-pid occupancy conflict detection and incident replay coverage; verified targeted pytest suite (42 passed), live sase doctor -C workspace.occupancy_conflicts --json (OK, 0 conflicts), just check, and no epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-vd.1](sase-vd.1.md) ✓ · ⧖ 2026-08-28
- **Depends on:** [sase-vd.2](sase-vd.2.md) ✓ · ⧖ 2026-08-28
- **Depends on:** [sase-vd.3](sase-vd.3.md) ✓ · ⧖ 2026-08-28
- **Depends on:** [sase-vd.4](sase-vd.4.md) ✓ · ⧖ 2026-08-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-vd.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vd.5/README.md) | [sase-vd.5](sase-vd.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6d88905`](https://github.com/sase-org/sase/commit/6d889058c89a0318ad74f3eabede360c7580680f) | feat(workspace): detect multi-workspace pid claims | [sase-vd.5](sase-vd.5.md) | 2026-08-28 21:28:38 EDT |
