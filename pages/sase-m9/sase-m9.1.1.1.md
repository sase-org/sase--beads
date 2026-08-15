# Bead: sase-m9.1.1.1 — Canonical sase-agent projection and compatibility aliases

[Bead Pages](../README.md) / [sase-m9.1.1](sase-m9.1.1.md) / sase-m9.1.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m9.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.1.md) · **Assignee:** `sase-m9.1.1.1` · **Size:** medium
**Created:** 2026-08-14 19:23:49 EDT · **Closed:** 2026-08-14 19:57:34 EDT
**Plan:** [202608/shell\_taxonomy.md](https://github.com/sase-org/sase--plans/blob/main/202608/shell_taxonomy.md)

## Description

sase-agent-projection: introduce SaseAgentRef and sase-agent projection helpers as the canonical vocabulary, retain narrow AgentLaneRef and lane_* import/serialization aliases for compatibility, clarify concrete-shell versus family/container provenance, and update focused unit and integration tests without changing identity resolution or sidecar paths.

## Notes

[2026-08-14T23:57:13Z · sase-m9.1.1.1] PROPOSED FOLLOW-UP: CLI/TUI tests assert unstyled strings but fail under CI/FORCE_COLOR — just check escalated to the full suite and 57 tests (bead CLI, plan validate, plugin panes, file-hook list, commit publication warnings) compared raw text to ANSI-styled output. Independent of this projection rename; reproduce with CI=1 just test tests/test_file_hook_cli.py tests/test_plan_validate.py.

[2026-08-14T23:57:34Z · sase-m9.1.1.1] Introduced SaseAgentRef and sase-agent projection helpers in sase.sase_agent (sase_agent_ref_for_shell from a concrete agent shell, sase_agent_ref_for_name from an already-projected name, sase_agent_page_path, sase_agent_name). Retained AgentLaneRef and lane_* as import aliases from sase.sase_agent and the sase.agent_lanes shim. Migrated provenance/ownership callers (association, publication, prompt archive, hosted links, artifact provider, commit finalization, image attachments, chat catalog) to canonical names without changing identity resolution or sidecar page paths; artifact property key remains lane. Verified solo/family/reserved-family/local-global/legacy-alias/page-path/missing-registry behavior, and that SASE_AGENT_NAME is the concrete shell while SASE_AGENT= records the sase agent. just lint passed; 155 focused projection/publication/association/hosted-link tests passed.

[2026-08-14T23:58:36Z · sase-m9.1.1.1] Introduced SaseAgentRef and sase-agent projection helpers in sase.sase_agent; retained AgentLaneRef/lane_* aliases; migrated provenance callers without changing identity resolution or sidecar paths. Verified solo/family/reserved-family/local-global/legacy-alias/page-path/missing-registry cases; SASE_AGENT_NAME stays the concrete shell while SASE_AGENT= records the sase agent; just lint passed; 155 focused projection/publication/association/hosted-link tests passed.

## Dependencies

- **Blocks:** [sase-m9.1.1.2](sase-m9.1.1.2.md) ✓ · ⧖ 2026-08-14
- **Blocks:** [sase-m9.1.1.3](sase-m9.1.1.3.md) ✓ · ⧖ 2026-08-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m9.1.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m9.1.1.1/README.md) | [sase-m9.1.1.1](sase-m9.1.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4280bc9`](https://github.com/sase-org/sase/commit/4280bc990c59dd3c2558af442673b0c037015281) | refactor(agents): introduce canonical SaseAgentRef projection | [sase-m9.1.1.1](sase-m9.1.1.1.md) | 2026-08-14 19:59:18 EDT |
