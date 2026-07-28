# Bead: sase-8v.2 — Nested identity config and initializer migration

[Bead Pages](../README.md) / [sase-8v](README.md) / sase-8v.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `athena.sase-8v.2` · **Size:** medium
**Created:** 2026-07-23 16:59:01 UTC
**Plan:** [202607/global\_agent\_hoods.md](https://github.com/sase-org/sase--plans/blob/main/202607/global_agent_hoods.md)

## Description

Move machine_name under id, require id.username in the selected machine overlay, migrate legacy overlays through config/init/doctor, and document the stable per-user identity contract.

## Notes

COMMIT: fe8f1ac59

## Dependencies

- **Depends on:** [sase-8v.1](sase-8v.1.md) ✓
- **Blocks:** [sase-8v.3](sase-8v.3.md) ✓
- **Blocks:** [sase-8v.9](sase-8v.9.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-8v.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-8v.2/README.md) | [sase-8v.2](sase-8v.2.md) | 1 |
| [bbugyi200.athena.sase-8v.2--code](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-8v.2.md#member-code) | [sase-8v.2](sase-8v.2.md) | 0 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`97230f1`](https://github.com/sase-org/sase/commit/97230f1a2901308ea2c28d1079d561ab00670847) | feat(identity)!: require nested owner configuration (sase-8v.2) | [sase-8v.2](sase-8v.2.md) | 2026-07-23 18:56:53 |
