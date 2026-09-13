# Bead: sase-zn.9 — Finish ACE typing-lag correctness and measured acceptance

[Bead Pages](../README.md) / [sase-zn](README.md) / sase-zn.9

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zn.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zn.land.md) · **Assignee:** `sase-zn.9.land`
**Created:** 2026-09-12 17:29:01 EDT
**Plan:** [202609/finish\_ace\_typing\_lag.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_ace_typing_lag.md)

## Description

Repair the notification cache race and scratch pressure integration, attribute retained ACE memory, and prove the original responsiveness targets under real athena load.

## Notes

[2026-09-13T14:13:44Z · sase-zu.land] LOAD-TIERING AUDIT from sase-zu landing at 654335d555: confirmed production full-history index reads miss an artifact created after index rebuild while reporting complete_history=true and needs_full_history_reconcile=false. Full-history revalidation also scans marker signatures across matching tiers before candidate filtering, and active search disables exact delta updates. The sase-zu remaining-work child will own indexed history completeness, bounded revalidation, query-key reuse and production-path benchmarks; preserve this ownership while sase-zn.9.4/.5 address broader loop/pump/heap responsiveness and live-host evidence.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zn.9.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zn.9.land/README.md) | [sase-zn.9](sase-zn.9.md) | 0 |
