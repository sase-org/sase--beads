# Bead: sase-17y.2 — Identity-verified relocation handling in bead work launches

[Bead Pages](../README.md) / [sase-17y](README.md) / sase-17y.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qv](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qv.md) · **Assignee:** `sase-17y.2` · **Size:** medium
**Created:** 2026-09-24 11:57:13 EDT
**Plan:** [202609/bead\_relocation\_safe\_epic\_launch.md](https://github.com/sase-org/sase--plans/blob/main/202609/bead_relocation_safe_epic_launch.md)

## Description

launch-guard: replace the prompt and env text rewrite in launch_epic_bead_work with an identity-verified check. Foreign relocations are ignored; a relocation of the launch's own graph rolls back on the moved IDs and raises EpicGraphRelocatedError. Also fix the resume callback that drops relocations, guard the task path, and make the text rewrite helper token-safe.

## Dependencies

- **Blocks:** [sase-17y.3](sase-17y.3.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17y.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17y.2/README.md) | [sase-17y.2](sase-17y.2.md) | 0 |
