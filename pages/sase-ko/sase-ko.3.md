# Bead: sase-ko.3 — Guard skips stop consuming run\_every cadence

[Bead Pages](../README.md) / [sase-ko](README.md) / sase-ko.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yx](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yx/README.md) · **Assignee:** `sase-ko.3` · **Size:** small
**Created:** 2026-08-12 16:00:14 EDT
**Plan:** [202608/chop\_agent\_runners\_guard.md](https://github.com/sase-org/sase--plans/blob/main/202608/chop_agent_runners_guard.md)

## Description

guard-cadence: stop advancing a chop's `run_every` clock when the skip came from an `inhibit_if` guard rather than from the configured trigger, so a guarded chop retries on the next tick.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ko.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ko.3/README.md) | [sase-ko.3](sase-ko.3.md) | 0 |
