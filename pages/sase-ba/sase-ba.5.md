# Bead: sase-ba.5 — Opt-in retention configuration and enforcement

[Bead Pages](../README.md) / [sase-ba](README.md) / sase-ba.5

**Status:** ◐ in_progress · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ba.5` · **Size:** small
**Created:** 2026-07-30 14:41:11 UTC
**Plan:** [202607/artifact\_store\_lifecycle.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_store_lifecycle.md)

## Description

retention-config: add the `artifacts.retention` configuration block defaulting to disabled, its schema entries and accessors, and the bounded, fail-safe enforcement pass that runs after automatic capture at finalization and purges expired trash.

## Dependencies

- **Depends on:** [sase-ba.3](sase-ba.3.md) ✓
- **Blocks:** [sase-ba.6](sase-ba.6.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ba.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ba.5/README.md) | [sase-ba.5](sase-ba.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`6999e31`](https://github.com/sase-org/sase/commit/6999e31a3dd9b90e117ae36efe30a4a113fccdb9) | feat(artifacts): add opt-in retention policy | [sase-ba.5](sase-ba.5.md) | 2026-07-30 17:12:09 |
| sase | [`1a4e838`](https://github.com/sase-org/sase/commit/1a4e838df607139e5402596398ea666b77280389) | test(artifacts): align retention fixtures with protection ids | [sase-ba.5](sase-ba.5.md) | 2026-07-30 17:30:16 |
