# Bead: sase-r8.3 — Python store, flag, and aggregate index

[Bead Pages](../README.md) / [sase-r8](README.md) / sase-r8.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08f](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08f.md) · **Assignee:** `sase-r8.3` · **Size:** medium
**Created:** 2026-08-19 19:16:36 EDT · **Closed:** 2026-08-20 07:03:32 EDT
**Plan:** [202608/artifact\_link\_graph.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_link_graph.md)

## Description

store: create the artifact_links beta flag, the per-artifact truth adapter, the rebuildable aggregate index, and the v1-to-v2 migration.

## Notes

[2026-08-20T11:03:07Z · sase-r8.3] PROPOSED FOLLOW-UP: tests/test_llm_provider_usage_limit_disable.py::TestHandlePossibleUsageLimit::test_codex_reset_at_date_failure_writes_until_disable_at_parsed_instant fails serially with ValueError: expires_at must be in the future — the Codex fixture reset is 2026-08-20 06:38 UTC and try_disable_provider_until passes now=None so the rust binding uses wall-clock time. Unrelated to the artifact_links store; just check escalated to the full suite because this phase touched Justfile and pyproject.toml.

[2026-08-20T11:03:32Z · sase-r8.3] Created artifact_links beta flag (bead sase-rc) and the Python store adapter: per-artifact v2 links/ JSON with atomic replace, rebuildable ~/.sase/projects/<key>/artifact-links.json, in-memory and write-on-upsert v1-to-v2 cites/prompt_ref migration (live monitor_followup_wait_release.json plus three corpus fixtures), audited artifact_reads.jsonl helper, and sase doctor project.artifact_links_aggregate. Flag off refuses v2 writes while v1 Referenced By refresh still runs and skips schema-2 files. Raised sase-core-rs floor to 0.29.3 and required the new artifact_link bindings. just check lint passed; scoped run escalated to the full suite (Justfile/pyproject) with 34960 passed and one unrelated usage-limit date-skew failure noted as PROPOSED FOLLOW-UP. No sase-r8.3 --epic-symbol leftovers; CLI-facing symbols are keyed to sase-r8.4.

[2026-08-20T11:04:34Z · sase-r8.3] Created artifact_links beta flag (bead sase-rc) and the Python store adapter: per-artifact v2 links/ JSON with atomic replace, rebuildable ~/.sase/projects/<key>/artifact-links.json, in-memory and write-on-upsert v1-to-v2 cites/prompt_ref migration (live monitor_followup_wait_release.json plus three corpus fixtures), audited artifact_reads.jsonl helper, and sase doctor project.artifact_links_aggregate. Flag off refuses v2 writes while v1 Referenced By refresh still runs and skips schema-2 files. Raised sase-core-rs floor to 0.29.3 and required the new artifact_link bindings. just check lint passed; scoped run escalated to the full suite (Justfile/pyproject) with 34960 passed and one unrelated usage-limit date-skew failure noted as PROPOSED FOLLOW-UP. No sase-r8.3 --epic-symbol leftovers; CLI-facing symbols are keyed to sase-r8.4.

## Dependencies

- **Depends on:** [sase-r8.1](sase-r8.1.md) ✓ · ⧖ 2026-08-19
- **Depends on:** [sase-r8.2](sase-r8.2.md) ✓ · ⧖ 2026-08-19
- **Blocks:** [sase-r8.4](sase-r8.4.md) ◐ · ⧖ 2026-08-19
- **Blocks:** [sase-r8.5](sase-r8.5.md) ◐ · ⧖ 2026-08-19
- **Blocks:** [sase-r8.6](sase-r8.6.md) ◐ · ⧖ 2026-08-19
- **Blocks:** [sase-r8.7](sase-r8.7.md) ◐ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-r8.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-r8.3/README.md) | [sase-r8.3](sase-r8.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6d87cf2`](https://github.com/sase-org/sase/commit/6d87cf2270b8d16dd6aad7de93e53cd2751e7d83) | feat(sdd): add artifact\_links store, flag, and aggregate index | [sase-r8.3](sase-r8.3.md) | 2026-08-20 07:05:27 EDT |
