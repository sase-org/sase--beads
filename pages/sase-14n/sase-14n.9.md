# Bead: sase-14n.9 — Disclose the run id on a failed launch and gate the floor smoke

[Bead Pages](../README.md) / [sase-14n](README.md) / sase-14n.9

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oe](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oe.md) · **Assignee:** `sase-14n.9` · **Size:** small
**Created:** 2026-09-20 17:14:17 EDT
**Plan:** [202609/fix\_triaged\_bug\_and\_ci\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202609/fix_triaged_bug_and_ci_beads.md)

## Description

toolrun_cli: print the wrapper header for a run whose child never starts, and add the ToolRun smoke to the release core-floor job now that the floor contains it.

## Dependencies

- **Depends on:** [sase-14n.1](sase-14n.1.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14n.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14n.9/README.md) | [sase-14n.9](sase-14n.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a7dde7d`](https://github.com/sase-org/sase/commit/a7dde7dbe661a5239393a30e2ccf516c50f21d45) | fix(tool): disclose run id on spawn-failure path and gate floor smoke | [sase-14n.9](sase-14n.9.md) | 2026-09-20 18:03:46 EDT |
