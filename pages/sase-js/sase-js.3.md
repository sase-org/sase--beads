# Bead: sase-js.3 — Provider registry, plugin hooks, and config

[Bead Pages](../README.md) / [sase-js](README.md) / sase-js.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.y2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.y2/README.md) · **Assignee:** `sase-js.3` · **Size:** large
**Created:** 2026-08-11 13:21:26 EDT · **Closed:** 2026-08-11 16:20:31 EDT
**Plan:** [202608/artifact\_ref\_contract.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_ref_contract.md)

## Description

registry: add the `sase_artifact` pluggy project with ref-provider and file-hook provider hookspecs, the spec registry with `use:`/inline merge and validation, the config schema deltas, the builtin `plan` provider, the `sase init` writer, and fail-soft diagnostics.

## Notes

[2026-08-11T20:20:31Z · sase-js.3] Implemented artifact provider registry plan; verified with focused pytest slices, just fmt, and just check including the escalated full-suite lane.

## Dependencies

- **Depends on:** [sase-js.1](sase-js.1.md) ✓ · ⧖ 2026-08-11
- **Depends on:** [sase-js.2](sase-js.2.md) ✓ · ⧖ 2026-08-11
- **Blocks:** [sase-js.4](sase-js.4.md) ◐ · ⧖ 2026-08-11
- **Blocks:** [sase-js.5](sase-js.5.md) ◐ · ⧖ 2026-08-11
- **Blocks:** [sase-js.8](sase-js.8.md) ◐ · ⧖ 2026-08-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-js.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-js.3.md) | [sase-js.3](sase-js.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f53e43a`](https://github.com/sase-org/sase/commit/f53e43ab139a7db2c50b75971fb7a5fc202619e5) | feat!: add artifact provider registry | [sase-js.3](sase-js.3.md) | 2026-08-11 16:21:40 EDT |
