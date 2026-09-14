# Bead: sase-zw.8 — Finish disk retention safety and integrated footprint acceptance

[Bead Pages](../README.md) / [sase-zw](README.md) / sase-zw.8

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zw.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zw.land.md) · **Assignee:** `sase-zw.8.land`
**Created:** 2026-09-13 18:40:37 EDT
**Plan:** [202609/disk\_footprint\_remaining\_work.md](https://github.com/sase-org/sase--plans/blob/main/202609/disk_footprint_remaining_work.md)

## Description

SASE disk owners enforce bounded, safe retention through Rust core, disk pressure reports and invokes the same policies, and the remaining host acceptance is measured.

## Notes

[2026-09-14T15:29:22Z · 0kk--code] COORDINATION from sase-10r: managed-tmp pressure now takes additive wire field `pressure_low_free_space_min_age_seconds` (config `managed_tmp.pressure.low_free_space_min_age_seconds`, default 1h) and reports `pressure_effective_min_age_seconds`. Whenever the free-space floor is breached, regardless of trigger, the effective pressure min age is `min(base, low-space)`. Please preserve this and its tests while completing disk-pressure owner delegation.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zw.8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zw.8.land/README.md) | [sase-zw.8](sase-zw.8.md) | 0 |
