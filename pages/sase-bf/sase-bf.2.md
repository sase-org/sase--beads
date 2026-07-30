# Bead: sase-bf.2 — Full JSON output-variable values in the sase-core scan wire

[Bead Pages](../README.md) / [sase-bf](README.md) / sase-bf.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-bf.2` · **Size:** medium
**Created:** 2026-07-30 21:00:26 UTC · **Closed:** 2026-07-30 21:09:41 UTC
**Plan:** [202607/structured\_sase\_variables.md](https://github.com/sase-org/sase--plans/blob/main/202607/structured_sase_variables.md)

## Description

core-wire-json: generalize OutputVariableValue in the sase-core agent-scan wire from text-or-string-list to a bounded JSON value, release sase-core, bump the sase-core-rs pin here, and widen the Python wire marker type.

## Dependencies

- **Blocks:** [sase-bf.4](sase-bf.4.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-bf.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-bf.2/README.md) | [sase-bf.2](sase-bf.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase-core | [`sase-core@b49a17a`](https://github.com/sase-org/sase-core/commit/b49a17a4b038902064e2922b67b569ec9a761f55) | feat(agent-scan)!: preserve bounded JSON output variables | [sase-bf.2](sase-bf.2.md) | 2026-07-30 21:09:51 |
