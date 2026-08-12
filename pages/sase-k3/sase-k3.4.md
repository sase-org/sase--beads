# Bead: sase-k3.4 — Read-only freshness policy for ACE's Tier-1 index query

[Bead Pages](../README.md) / [sase-k3](README.md) / sase-k3.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yo](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yo/README.md) · **Assignee:** `sase-k3.4` · **Size:** medium
**Created:** 2026-08-12 11:37:58 EDT
**Plan:** [202608/ace\_startup\_critical\_path.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_startup_critical_path.md)

## Description

repair: add a freshness knob to the artifact-index query wire in sase-core so ACE's startup and auto-refresh queries skip hidden-row repair and per-row marker revalidation, stop selecting record_json in refresh_stale_rows, and run one coalesced revalidating reconcile after first paint on a long cadence.

## Dependencies

- **Depends on:** [sase-k3.1](sase-k3.1.md) ◐ · ⧖ 2026-08-12
- **Blocks:** [sase-k3.6](sase-k3.6.md) ◐ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-k3.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-k3.4/README.md) | [sase-k3.4](sase-k3.4.md) | 0 |
