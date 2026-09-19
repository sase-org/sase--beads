# Bead: sase-135.2 — Add the project-owned catalog and tool list command

[Bead Pages](../README.md) / [sase-135](README.md) / sase-135.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0nm](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0nm.md) · **Assignee:** `sase-135.2` · **Size:** medium
**Created:** 2026-09-18 22:19:19 EDT · **Closed:** 2026-09-19 06:11:50 EDT
**Plan:** [202609/tool\_e1\_named\_tools.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e1_named_tools.md)

## Description

catalog: Implement section 2, including whole project-layer tool definitions, Rust validation, operational retention configuration, five repository tools, versioned list output, and parser/default-list coverage.

## Notes

[2026-09-19T10:11:50Z · sase-135.2] Implemented the project-owned tools catalog and sase tool list.

DEMO: sase tool -> 'No subcommand provided for sase tool; delegating to sase tool list.' then five named tools (check, check-full, install, test, test-visual) with LAST/TYPICAL em dashes.
DEMO: sase tool list -j -> schema_version 1, five entries, last=null, typical_duration_ms=null.
DEMO: malformed fixture sase.yml tools.ping.shell=true -> sase tool list -j exits 2 naming tools.ping and unknown field shell; never spawns.
DEMO: tools/smoke_sase_tool_runs --sase .venv/bin/sase -> dod-1-catalog pass; dod-2/dod-3 remain phase-pending.

Verified: sase bead epic-symbols sase-135.2 has no leftovers. Removed sase-135.2 epic-symbols for tool_run_normalize_definition and tool_run_summary (now consumed by catalog/list); re-keyed tool_run_list to sase-135.3. just check lint stages passed; test-scoped 43362 passed after refreshing the completion spec snapshot. Compact root help still omits tool (phase 6).

## Dependencies

- **Depends on:** [sase-135.1](sase-135.1.md) ✓ · ⧖ 2026-09-18
- **Blocks:** [sase-135.3](sase-135.3.md) ◐ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-135.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-135.2/README.md) | [sase-135.2](sase-135.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`423316a`](https://github.com/sase-org/sase/commit/423316a05119ce40327edb864eff941013424bc6) | feat(tool): add the project-owned catalog and sase tool list | [sase-135.2](sase-135.2.md) | 2026-09-19 06:13:22 EDT |
