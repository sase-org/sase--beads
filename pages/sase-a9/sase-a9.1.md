# Bead: sase-a9.1 — Page shell, breadcrumbs, and golden refresh tooling

[Bead Pages](../README.md) / [sase-a9](README.md) / sase-a9.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-a9.1` · **Size:** medium
**Created:** 2026-07-27 20:35:29 UTC · **Closed:** 2026-07-27 21:31:41 UTC
**Plan:** [202607/agent\_page\_artifacts.md](https://github.com/sase-org/sase--plans/blob/main/202607/agent_page_artifacts.md)

## Description

shell: split the browsing renderer into focused modules, add breadcrumb navigation to agent and family pages, and add the pytest flag that rewrites the agents-sync markdown goldens.

## Notes

[2026-07-27T21:31:35Z · sase-a1.land] [2026-07-27T20:58:31Z · sase-a9.1] (restored 2026-07-27) Implemented the renderer module split, agent and family breadcrumbs, and the intentional-failure agents golden refresh flag. Verified 130 agents-sync tests pass; formatting, Ruff, mypy, Symvision, toobig, and plan validation pass. The full suite reached 22,788 passing tests with one unrelated ACE visual flake that passed in isolation. A later SASE validation rerun was blocked only by concurrent one-line drift in five global generated sase_beads provider files, which were left untouched.

## Dependencies

- **Blocks:** [sase-a9.2](sase-a9.2.md) ✓
- **Blocks:** [sase-a9.3](sase-a9.3.md) ✓
- **Blocks:** [sase-a9.4](sase-a9.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-a9.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-a9.1/README.md) | [sase-a9.1](sase-a9.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`dbddc16`](https://github.com/sase-org/sase/commit/dbddc16c12396524ab7dec8c81a1fa1e33019d53) | feat(agents): add page breadcrumbs and golden refresh (sase-a9.1) | [sase-a9.1](sase-a9.1.md) | 2026-07-27 21:00:26 |
