# Bead: sase-1n8.1 — sase-core: seal-time guards for conditional completion

[Bead Pages](../README.md) / [sase-1n8](README.md) / sase-1n8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.96` · **Assignee:** `sase-1n8.1` · **Size:** medium
**Created:** 2026-10-20 06:52:59 EDT · **Closed:** 2026-10-20 07:42:08 EDT
**Plan:** [202610/host\_completion\_loop\_and\_disk\_churn.md](https://github.com/sase-org/sase--plans/blob/main/202610/host_completion_loop_and_disk_churn.md)

## Description

core-completion-seal-guards: in sase-core, refuse to seal a just check contract whose stages the project cannot report, and refuse re-sealing an identical tree whose passing check was already refused.

## Notes

[2026-10-20T11:42:08Z · sase-1n8.1] Sealed guards land in sase-core working tree (uncommitted for host land): stage_source none refused with required stages, run_silent/absent seal unchanged, matching prior_refusal refused quoting reason. Tests: 8 new completion.rs tests + binding round-trip test pass; sase tool run check ea8731901bfbe5d5257c982226a9c87b succeeded exit=0.

## Dependencies

- **Blocks:** [sase-1n8.2](sase-1n8.2.md) ✓ · ⧖ 2026-10-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n8.1/README.md) | [sase-1n8.1](sase-1n8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@b664b15`](https://github.com/sase-org/sase-core/commit/b664b15bf7b27cc10c342f99d9777409495956e3) | feat(continuation): refuse unsatisfiable and repeated conditional completion seals | [sase-1n8.1](sase-1n8.1.md) | 2026-10-20 07:43:14 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1n8.1][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n8.1/README.md

<!-- sase:referenced-by:end -->
