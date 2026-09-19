# Bead: sase-135.4 — Record run\_silent stages and render the timeline

[Bead Pages](../README.md) / [sase-135](README.md) / sase-135.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0nm](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0nm.md) · **Assignee:** `sase-135.4` · **Size:** medium
**Created:** 2026-09-18 22:19:22 EDT · **Closed:** 2026-09-19 10:28:53 EDT
**Plan:** [202609/tool\_e1\_named\_tools.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e1_named_tools.md)

## Description

stage-timeline: Implement section 4, adding recoverable JSONL start/finish events to run_silent without changing Justfile recipes, parent ingestion, compact progress, monitor timing fields, and timeline recovery tests.

## Notes

[2026-09-19T14:28:53Z · sase-135.4] Implemented stage-timeline: tools/run_silent writes locked JSONL started/finished events when SASE_TOOL_RUN_EVENTS is set (stdlib helper, no SQLite), parent tails on the existing 0.1s wait tick and ingests through tool_run_append_event, compact mode prints one completion line per stage, show/show -j/footer share unattributed union math, lost reconcile rereads events.jsonl, monitor stage JSON gained started_at_epoch and elapsed_seconds. Justfile recipes unchanged.

DEMO: tools/smoke_sase_tool_runs --sase .venv/bin/sase -> dod-6-timeline pass (repeated alpha stage ids, beta failure stops gamma, unattributed_ms int, show lists STAGES/UNATTRIB); failed=0.
DEMO: sase bead epic-symbols sase-135.4 -> no leftovers. Removed unused tool_run_append_event epic-symbol after ingest started calling it.

Verified: just check passed (full suite after Justfile epic-symbol re-key). Unwrapped run_silent still prints ✓/✗ only. Torn/malformed/cross-run events recover valid records. Nested runs do not cross-attribute. Incomplete start-only stages stay incomplete. Lost wrapper recovers hold stages without guessed duration/exit.

## Dependencies

- **Depends on:** [sase-135.3](sase-135.3.md) ✓ · ⧖ 2026-09-18
- **Blocks:** [sase-135.5](sase-135.5.md) ✓ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-135.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-135.4/README.md) | [sase-135.4](sase-135.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a4eb8dd`](https://github.com/sase-org/sase/commit/a4eb8dd0eed0ced1c4d019d0585b097d3833924a) | feat(tool): record run\_silent stages and render ToolRun timelines | [sase-135.4](sase-135.4.md) | 2026-09-19 10:30:48 EDT |
