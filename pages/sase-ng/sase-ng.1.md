# Bead: sase-ng.1 — Retire dead ACE in-process launch and cleanup bodies

[Bead Pages](../README.md) / [sase-ng](README.md) / sase-ng.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ng](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ng.md) · **Assignee:** `sase-ng.1.land`
**Created:** 2026-08-17 15:16:50 EDT
**Plan:** [202608/retire\_dead\_ace\_launch\_cleanup\_bodies.md](https://github.com/sase-org/sase--plans/blob/main/202608/retire_dead_ace_launch_cleanup_bodies.md)

## Description

ACE's launch and cleanup procs have exactly one implementation each — the durable argv path production actually runs — with no orphaned in-process body family, no vestigial `proc_callable` parameters, no test double that reaches a code path production cannot reach, and no user-facing capability silently dropped on the way.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ng.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ng.1.land/README.md) | [sase-ng.1](sase-ng.1.md) | 0 |
