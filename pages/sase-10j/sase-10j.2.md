# Bead: sase-10j.2 — Monitor start stops minting doomed members and stealing live claims

[Bead Pages](../README.md) / [sase-10j](README.md) / sase-10j.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.0i.f0` · **Assignee:** `sase-10j.2` · **Size:** medium
**Created:** 2026-09-13 21:53:04 EDT
**Plan:** [202609/failed\_monitor\_blocks\_family\_wait.md](https://github.com/sase-org/sase--plans/blob/main/202609/failed_monitor_blocks_family_wait.md)

## Description

monitor-start-claim: pre-flight the lane workspace claim before create_monitor_member so a doomed start raises without creating a family member, resolve stale transfer pids by adopting only dead holders' claim rows (never transferring away from a live process), and make no-op releases record truthfully.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-10j.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-10j.2/README.md) | [sase-10j.2](sase-10j.2.md) | 0 |
