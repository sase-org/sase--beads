# Bead: sase-1sl.1 — sase-core: capacity-only scan cost scales with live records, not archive size

[Bead Pages](../README.md) / [sase-1sl](README.md) / sase-1sl.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1c0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1c0.md) · **Assignee:** `sase-1sl.1` · **Size:** large
**Created:** 2026-11-12 16:45:04 EST
**Plan:** [202611/capacity\_scan\_tui\_runaway.md](https://github.com/sase-org/sase--plans/blob/main/202611/capacity_scan_tui_runaway.md)

## Description

core-capacity-scan: in the linked sase-core repo, add a statx-only live-marker precheck plus meta-light closure classification (and, per the verdict_cache decision, a sticky never-live verdict cache) to the capacity_only scanner path, with parity tests and a scan-cost bench guarding identical retained records.

## Dependencies

- **Blocks:** [sase-1sl.2](sase-1sl.2.md) ◐ · ⧖ 2026-11-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sl.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sl.1.md) | [sase-1sl.1](sase-1sl.1.md) | 0 |
