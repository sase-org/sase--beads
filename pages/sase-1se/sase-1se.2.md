# Bead: sase-1se.2 — Healer ledger keys derive the project from the canonical artifact path parser

[Bead Pages](../README.md) / [sase-1se](README.md) / sase-1se.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bq](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bq.md) · **Assignee:** `sase-1se.2` · **Size:** small
**Created:** 2026-11-12 06:15:58 EST
**Plan:** [202611/auto\_restart\_update\_skew\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/auto_restart_update_skew_fixes.md)

## Description

ledger-project-key: `_target_for_artifacts_dir` derives the ledger project via `parse_agent_artifact_path` instead of `parents[1].name`, so day-sharded ace-run rows key as `<project>__<lineage>` and the at-most-once guarantee holds across both healer enumeration sources.

## Dependencies

- **Blocks:** [sase-1se.3](sase-1se.3.md) ◐ · ⧖ 2026-11-12
- **Blocks:** [sase-1se.4](sase-1se.4.md) ◐ · ⧖ 2026-11-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1se.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1se.2/README.md) | [sase-1se.2](sase-1se.2.md) | 0 |
