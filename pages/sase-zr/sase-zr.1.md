# Bead: sase-zr.1 — Measure approval stages and replace full-history gate lookup

[Bead Pages](../README.md) / [sase-zr](README.md) / sase-zr.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.athena.0js` · **Assignee:** `sase-zr.1` · **Size:** medium
**Created:** 2026-09-12 05:06:13 EDT
**Plan:** [202609/prompt\_gate\_approval.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompt_gate_approval.md)

## Description

bounded-gate-resolution: In sase-core and sase, instrument the approval boundaries from submission through paint and replace find_gate_shell_by_gate_id's full-history scan with an indexed exact gate-id lookup exposed through the Rust binding. Maintain the lookup on gate creation and marker mutation, handle old indexes off the interactive path, and test that lookup work stays bounded as unrelated history grows. Resolve the exact owning shell, not a successor inheriting its gate id. Preserve project scoping and newest-real-shell behavior. Run focused Rust/PyO3 and Python tests and each changed repository's required checks.

## Dependencies

- **Blocks:** [sase-zr.2](sase-zr.2.md) ◐ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-zr.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-zr.1.md) | [sase-zr.1](sase-zr.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`93f3d58`](https://github.com/sase-org/sase/commit/93f3d58911b9968575bd08676c65b3577e01e016) | feat(gate-shell): add indexed gate-shell-by-gate-id lookup with telemetry | [sase-zr.1](sase-zr.1.md) | 2026-09-13 19:12:59 EDT |
