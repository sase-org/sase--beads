# Bead: sase-n8.2 — Rust core — alias projection, schema 22, and the alias-history query

[Bead Pages](../README.md) / [sase-n8](README.md) / sase-n8.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03t](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03t.md) · **Assignee:** `sase-n8.2` · **Size:** large
**Created:** 2026-08-16 11:31:18 EDT · **Closed:** 2026-08-16 12:18:43 EDT
**Plan:** [202608/launch\_control\_alias\_history.md](https://github.com/sase-org/sase--plans/blob/main/202608/launch_control_alias_history.md)

## Description

core: in the sase-core repo, add the alias trail/origin to AgentMetaWire and PromptStepMarkerWire, project each run's trail into a new normalized agent_artifact_model_aliases table under artifact-index schema 22 with a record_json re-projection migration that backfills legacy rows, and expose a bounded `query_agent_alias_history` PyO3 binding that returns per-alias groups with truncation counts and a directive-stripped prompt snippet.

## Notes

[2026-08-16T16:18:43Z · sase-n8.2] Verified schema-22 alias-history core in sase-core: AgentMetaWire/PromptStepMarkerWire parse and round-trip model_alias_trail/origin (absent values default to empty trail and no origin); agent_artifact_model_aliases is written delete-then-insert on upsert and cleared on delete; v21-to-v22 migration re-projects from record_json without filesystem reads and skips malformed rows; query_agent_alias_history preserves request order including empty groups, newest-first windows, exact truncation counts, non-entry alias_position, hidden/project filters, legacy first-hop fallback, cached vs revalidate freshness, empty-alias rejection, and prompt-snippet strip/collapse/Unicode truncation/directive-only/missing-file/zero-budget cases; PyO3 binding deserializes the query dict and serializes the result wire. just check passed from the sase-core repo root (fmt, clippy -D warnings, cargo test --workspace including sase_core_py).

[2026-08-16T16:21:40Z · sase-n8.2] Verified in sase-core: schema 22 model-alias projection and query_agent_alias_history PyO3 binding landed; just check passed (fmt, clippy -D warnings, cargo test --workspace including sase_core_py).

## Dependencies

- **Blocks:** [sase-n8.3](sase-n8.3.md) ✓ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n8.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-n8.2.md) | [sase-n8.2](sase-n8.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@5078d26`](https://github.com/sase-org/sase-core/commit/5078d263f9078bd66382d40d24ed659154c48b88) | feat(agent\_scan): project alias trails and query bounded alias history | [sase-n8.2](sase-n8.2.md) | 2026-08-16 12:23:18 EDT |
