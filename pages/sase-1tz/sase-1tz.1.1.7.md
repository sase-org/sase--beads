# Bead: sase-1tz.1.1.7 — Report repeated managed-tmp reaper skips as one standing state

[Bead Pages](../README.md) / [sase-1tz.1.1](sase-1tz.1.1.md) / sase-1tz.1.1.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.1.md) · **Assignee:** `sase-1tz.1.1.7` · **Size:** small
**Created:** 2026-11-19 07:28:42 EST
**Plan:** [202611/outage\_disk\_attribution\_and\_held\_workspaces.md](https://github.com/sase-org/sase--plans/blob/main/202611/outage_disk_attribution_and_held_workspaces.md)

## Description

standing_skips: the managed_tmp_reap chop keeps refusing to reap entries it cannot fully inspect. It warns once when a skip appears or its reason changes, and logs again when the skip clears, instead of warning every pass.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.1.1.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.1.1.7/README.md) | [sase-1tz.1.1.7](sase-1tz.1.1.7.md) | 0 |
