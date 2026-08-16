# Bead: sase-n8.2 — Rust core — alias projection, schema 22, and the alias-history query

[Bead Pages](../README.md) / [sase-n8](README.md) / sase-n8.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03t](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03t.md) · **Assignee:** `sase-n8.2` · **Size:** large
**Created:** 2026-08-16 11:31:18 EDT
**Plan:** [202608/launch\_control\_alias\_history.md](https://github.com/sase-org/sase--plans/blob/main/202608/launch_control_alias_history.md)

## Description

core: in the sase-core repo, add the alias trail/origin to AgentMetaWire and PromptStepMarkerWire, project each run's trail into a new normalized agent_artifact_model_aliases table under artifact-index schema 22 with a record_json re-projection migration that backfills legacy rows, and expose a bounded `query_agent_alias_history` PyO3 binding that returns per-alias groups with truncation counts and a directive-stripped prompt snippet.

## Dependencies

- **Blocks:** [sase-n8.3](sase-n8.3.md) ◐ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n8.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-n8.2.md) | [sase-n8.2](sase-n8.2.md) | 0 |
