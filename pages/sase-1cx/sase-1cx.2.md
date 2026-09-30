# Bead: sase-1cx.2 — Configurable per-provider soft ceiling export

[Bead Pages](../README.md) / [sase-1cx](README.md) / sase-1cx.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u3.md) · **Assignee:** `sase-1cx.2` · **Size:** medium
**Created:** 2026-09-29 20:32:15 EDT · **Closed:** 2026-09-29 20:46:06 EDT
**Plan:** [202609/tool\_run\_escalation.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_run_escalation.md)

## Description

soft-ceiling: add the `tool_runs.soft_ceiling` config and export `SASE_PROVIDER_SYNC_SOFT_CEILING_SECONDS` around each provider invocation, scrubbed at every agent, monitor, and proc boundary. Nothing consumes it yet.

## Notes

[2026-09-30T00:45:40Z · sase-1cx.2] PROPOSED FOLLOW-UP: just check lint (patch/stitch terminology) fails identically on clean base (exit 1, 14 defects all in sase-core linked-repo fixtures at_bearing_notes.jsonl); unrelated to soft-ceiling change, needs triage by terminology-audit owner

[2026-09-30T00:46:06Z · sase-1cx.2] soft-ceiling landed: tool_runs.soft_ceiling config (default+providers) with get_tool_runs_soft_ceiling_seconds resolver, SASE_PROVIDER_SYNC_SOFT_CEILING_SECONDS export/restore in invoke_agent, exact-key scrub at agent/monitor/proc boundaries, docs in configuration.md/tool.md/llms.md. Verified: 65 focused tests pass (new test_tool_runs_soft_ceiling, new llm_provider/test_soft_ceiling, extended hygiene+monitor tests), ruff+mypy clean, just fix clean, epic-symbols empty. just check fails only on pre-existing patch/stitch terminology audit (reproduces exit 1 on clean base, recorded as PROPOSED FOLLOW-UP). Nothing consumes the value yet, no flag needed.

## Dependencies

- **Blocks:** [sase-1cx.4](sase-1cx.4.md) ◐ · ⧖ 2026-09-29
- **Blocks:** [sase-1cx.6](sase-1cx.6.md) ◐ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cx.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cx.2/README.md) | [sase-1cx.2](sase-1cx.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8804865`](https://github.com/sase-org/sase/commit/8804865f84a795d798067fb1eb97c93f5b6cdd18) | feat(tool-runs): add soft-ceiling config with provider sync env export | [sase-1cx.2](sase-1cx.2.md) | 2026-09-29 20:48:25 EDT |
