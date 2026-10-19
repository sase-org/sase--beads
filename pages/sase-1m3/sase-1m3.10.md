# Bead: sase-1m3.10 — The sase stats group and the project command

[Bead Pages](../README.md) / [sase-1m3](README.md) / sase-1m3.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.1s.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.1s.linker.w0.md) · **Assignee:** `sase-1m3.10` · **Size:** medium
**Created:** 2026-10-16 22:05:25 EDT · **Closed:** 2026-10-19 12:21:42 EDT
**Plan:** [202610/sase\_stats\_project.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_stats_project.md)

## Description

cli: register `sase stats` and `sase stats project` with rich/markdown/json output, the versioned JSON envelope, fetch, exit codes, root help, completion snapshot, and the generated CLI reference page.

## Notes

[2026-10-19T13:18:28Z · sase-1m3.10] PROPOSED FOLLOW-UP: skipped decisions-web record (stats_decision_record=no) — "stats count each fact at its durable source, and footers stamp only underivable facts?"

[2026-10-19T13:18:37Z · sase-1m3.10] PROPOSED FOLLOW-UP: guide candidate — how to inspect and share Admin Center Projects statistics from the CLI (`sase stats project`)

[2026-10-19T16:21:12Z · sase-1m3.10] PROPOSED FOLLOW-UP: pre-existing ACE TUI agent-display/import-budget flakes in sase tool run 77ea9947ca91b0f2c8c521f36dae0656 (8 NEW + 12 KNOWN; none in stats CLI; same family as prior run a534504fe8f54bf315a19419ae9ca9b9)

[2026-10-19T16:21:42Z · sase-1m3.10] Verified sase stats + sase stats project: parser/handler/envelope, -D/-F/-f/-g/-j/-p/-r, bare group help, JSON schema sase.stats.project, docs/completion, help golden. sase tool run check lint/fmt/docs/symvision green; CLI/timezone/completion tests passed. Remaining scoped failures are pre-existing ACE TUI flakes (run 77ea9947).

## Dependencies

- **Blocks:** [sase-1m3.12](sase-1m3.12.md) ✓ · ⧖ 2026-10-16
- **Depends on:** [sase-1m3.5](sase-1m3.5.md) ✓ · ⧖ 2026-10-16
- **Depends on:** [sase-1m3.6](sase-1m3.6.md) ✓ · ⧖ 2026-10-16
- **Depends on:** [sase-1m3.7](sase-1m3.7.md) ✓ · ⧖ 2026-10-16
- **Depends on:** [sase-1m3.9](sase-1m3.9.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1m3.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1m3.10/README.md) | [sase-1m3.10](sase-1m3.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a53f10f`](https://github.com/sase-org/sase/commit/a53f10f6a6ce1103dfe7ce30653ba6712ed24478) | feat(stats): add sase stats project CLI | [sase-1m3.10](sase-1m3.10.md) | 2026-10-19 12:23:58 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1m3.10][1] | Need the phase scope, notes, and remaining work before verifying and closing | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1m3.10/README.md

<!-- sase:referenced-by:end -->
