# Bead: sase-17m.5.1.5 — Snapshot renames, perf check, and classification sweep

[Bead Pages](../README.md) / [sase-17m.5.1](sase-17m.5.1.md) / sase-17m.5.1.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.5.md) · **Assignee:** `sase-17m.5.1.5` · **Size:** medium
**Created:** 2026-09-25 00:06:06 EDT
**Plan:** [202609/agent\_session\_ace\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_ace_cutover.md)

## Description

snapshots-sweep: rename the family-named PNG snapshot tests, fixture modules, and goldens, and every remaining family-named tests/ace or tests/perf file. Update the shard-timing and flake baselines. Run a full just fix-tui-screenshots through /sase_monitor, inspect the report, and remove stale goldens only after the full run. Run the j/k navigation benchmark to confirm no regression. Classify every remaining famil hit in ACE scope, record hand-offs on sase-17m.5, and run sase tool run check.

## Dependencies

- **Depends on:** [sase-17m.5.1.4](sase-17m.5.1.4.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.5.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.5.1.5/README.md) | [sase-17m.5.1.5](sase-17m.5.1.5.md) | 0 |
