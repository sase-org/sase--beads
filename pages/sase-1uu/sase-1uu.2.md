# Bead: sase-1uu.2 — Gate aggregate write retries and publish rebuilds on the caller deadline

[Bead Pages](../README.md) / [sase-1uu](README.md) / sase-1uu.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ew](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ew.md) · **Assignee:** `sase-1uu.2` · **Size:** medium
**Created:** 2026-11-21 10:59:30 EST
**Plan:** [202611/artifact\_link\_aggregate\_timeouts.md](https://github.com/sase-org/sase--plans/blob/main/202611/artifact_link_aggregate_timeouts.md)

## Description

Make _write_merged_aggregate stop retrying after a lost CAS race when the next preview cannot finish before the caller's deadline. Thread the deadline through rebuild_aggregate, reconcile_aggregate, and the publish-path apply_events_to_aggregate, with typed deferral handling in both chops. Add per-sub-phase publish timings.

## Dependencies

- **Depends on:** [sase-1uu.1](sase-1uu.1.md) ✓ · ⧖ 2026-11-21
- **Blocks:** [sase-1uu.3](sase-1uu.3.md) ◐ · ⧖ 2026-11-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1uu.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1uu.2/README.md) | [sase-1uu.2](sase-1uu.2.md) | 0 |
