# Bead: sase-1le.20.1.15 — Retire the hand-maintained CLI flag tables and cli.md

[Bead Pages](../README.md) / [sase-1le.20.1](sase-1le.20.1.md) / sase-1le.20.1.15

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1le.20](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.md) · **Assignee:** `sase-1le.20.1.15` · **Size:** medium
**Created:** 2026-10-16 08:04:39 EDT · **Closed:** 2026-10-16 16:55:12 EDT
**Plan:** [202610/docs\_decompose.md](https://github.com/sase-org/sase--plans/blob/main/202610/docs_decompose.md)

## Description

cli: compare configuration.md CLI Flags and cli.md against the generated CLI pages, port missing facts into argparse help or subsystem pages, delete the tables with anchor targets, and finish both pages as stubs.

## Notes

[2026-10-16T20:55:00Z · sase-1le.20.1.15] PROPOSED FOLLOW-UP: Investigate clean-base `just check` failing at `init memory --check` because seven generated memory and provider instruction files are out of sync — reproduced with all other validation checks passing.

[2026-10-16T20:55:12Z · sase-1le.20.1.15] Updated generated CLI help and split the legacy CLI/configuration reference into focused pages; just fix and generated-doc checks completed. In just check, all lint and other SASE validation checks passed; init memory --check failed on seven generated memory/provider files, reproduced on the clean base tree. Direct sase validate passed after refreshing memory. Recorded the reproducible clean-base issue as a proposed follow-up. epic-symbols reported no leftovers.

## Dependencies

- **Depends on:** [sase-1le.20.1.11](sase-1le.20.1.11.md) ✓ · ⧖ 2026-10-16
- **Depends on:** [sase-1le.20.1.14](sase-1le.20.1.14.md) ✓ · ⧖ 2026-10-16
- **Blocks:** [sase-1le.20.1.21](sase-1le.20.1.21.md) ◐ · ⧖ 2026-10-16
- **Depends on:** [sase-1le.20.1.6](sase-1le.20.1.6.md) ✓ · ⧖ 2026-10-16
- **Depends on:** [sase-1le.20.1.7](sase-1le.20.1.7.md) ✓ · ⧖ 2026-10-16
- **Depends on:** [sase-1le.20.1.9](sase-1le.20.1.9.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.20.1.15](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.15/README.md) | [sase-1le.20.1.15](sase-1le.20.1.15.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`367562b`](https://github.com/sase-org/sase/commit/367562ba5251a66cd36562cd7996ced23b235f87) | feat(cli): generate root flag reference and split CLI docs | [sase-1le.20.1.15](sase-1le.20.1.15.md) | 2026-10-16 16:56:16 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1le.20.1.15][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.15/README.md

<!-- sase:referenced-by:end -->
