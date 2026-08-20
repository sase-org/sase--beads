# Bead: sase-r8.4 — sase artifact link and sase artifact read

[Bead Pages](../README.md) / [sase-r8](README.md) / sase-r8.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08f](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08f.md) · **Assignee:** `sase-r8.4` · **Size:** medium
**Created:** 2026-08-19 19:16:36 EDT · **Closed:** 2026-08-20 08:00:24 EDT
**Plan:** [202608/artifact\_link\_graph.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_link_graph.md)

## Description

cli: ship sase artifact link add/list/rm and sase artifact read with doctor checks and retention protection.

## Notes

[2026-08-20T11:59:54Z · sase-r8.4] PROPOSED FOLLOW-UP: tests/test_llm_provider_usage_limit_disable.py::TestHandlePossibleUsageLimit::test_codex_reset_at_date_failure_writes_until_disable_at_parsed_instant fails serially with assert None is not None — the Codex fixture reset is wall-clock-relative and try_disable_provider_until uses now=None so the rust binding uses current time. Unrelated to the artifact link CLI; just check escalated to the full suite because this phase touched Justfile.

[2026-08-20T12:00:24Z · sase-r8.4] Shipped sase artifact link add/list/rm and sase artifact read. Verified: alphabetical parsers with short aliases and default-list for bare link; idempotent add; flag-off add/rm/migrate-notes --apply errors naming artifact_links and how to enable it; list still reads when flag is off; reserved blocks/depends-on point at sase bead dep; read strips frontmatter and both managed blocks, refuses to print when the audit log cannot be written, and notes when the read is not recorded as a link; show JSON includes a stable links array; doctor reports dangling/stale/companion/HEAD-missing checks (skipped when flag is off) and --fix migrates v1 trees plus rebuilds the aggregate; linked file: ids are protected from reclaim; completion spec regenerated. just check lint passed; scoped run escalated to the full suite (Justfile) with 34982 passed and one unrelated usage-limit date-skew failure noted as PROPOSED FOLLOW-UP. No sase-r8.4 --epic-symbol leftovers.

[2026-08-20T12:01:46Z · sase-r8.4] Shipped sase artifact link add/list/rm and sase artifact read. Verified: alphabetical parsers with short aliases and default-list for bare link; idempotent add; flag-off add/rm/migrate-notes --apply errors naming artifact_links and how to enable it; list still reads when flag is off; reserved blocks/depends-on point at sase bead dep; read strips frontmatter and both managed blocks, refuses to print when the audit log cannot be written, and notes when the read is not recorded as a link; show JSON includes a stable links array; doctor reports dangling/stale/companion/HEAD-missing checks (skipped when flag is off) and --fix migrates v1 trees plus rebuilds the aggregate; linked file: ids are protected from reclaim; completion spec regenerated. just check lint passed; scoped run escalated to the full suite (Justfile) with 34982 passed and one unrelated usage-limit date-skew failure noted as PROPOSED FOLLOW-UP. No sase-r8.4 --epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-r8.3](sase-r8.3.md) ✓ · ⧖ 2026-08-19
- **Blocks:** [sase-r8.8](sase-r8.8.md) ◐ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-r8.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-r8.4/README.md) | [sase-r8.4](sase-r8.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`55ee145`](https://github.com/sase-org/sase/commit/55ee145f6c5a8fc05b34c028b08c5e8fb0262c6f) | feat(artifact): add sase artifact link and sase artifact read | [sase-r8.4](sase-r8.4.md) | 2026-08-20 08:03:12 EDT |
