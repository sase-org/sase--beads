# Bead: sase-zl.13 — Finish monitor continuation correctness and production acceptance

[Bead Pages](../README.md) / [sase-zl](README.md) / sase-zl.13

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zl.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zl.land.md) · **Assignee:** `sase-zl.13.land`
**Created:** 2026-09-11 23:43:25 EDT
**Plan:** [202609/monitor\_continuation\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/monitor_continuation_landing_repairs.md)

## Description

Complete the missing capture, replay, evidence, delivery, recovery and budget paths required by sase-zl, preserve intervening launch and capacity changes, and prove the integrated feature before resuming its interrupted landing.

## Notes

[2026-09-12T10:19:22Z · sase-z4.6.5.4.land] DISCOVERED ISSUE from sase-z4.6.5.4 landing at primary 96c3877e0: continuation_delivery.queue_launch_prefix uses meta.get("wait_priority") or meta.get("queue_priority") and the analogous wait_runners/queue_capacity expression. Explicit wait_priority=0 or wait_runners=0 is dropped when the alternate key is absent, and replaced when it is nonzero. This code arrived with 56ceab3f9 (your phase .5), after weighted-capacity acceptance was authored. It violates the preserved explicit-zero contract; the existing weight-2 monitor test constructs the successor with hard-coded weight and never verifies those directive fields. Please preserve absence separately from zero. Our remaining-work child will prove the integrated lifecycle and recheck this repair; no duplicate task.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zl.13.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zl.13.land/README.md) | [sase-zl.13](sase-zl.13.md) | 0 |
