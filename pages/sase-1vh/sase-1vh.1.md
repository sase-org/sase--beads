# Bead: sase-1vh.1 — Opt-in busy patience at the lookup facades, installed by the agent runner

[Bead Pages](../README.md) / [sase-1vh](README.md) / sase-1vh.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1gu](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1gu.md) · **Assignee:** `sase-1vh.1` · **Size:** medium
**Created:** 2026-11-26 14:45:31 EST
**Plan:** [202611/launch\_lookup\_busy\_resilience.md](https://github.com/sase-org/sase--plans/blob/main/202611/launch_lookup_busy_resilience.md)

## Description

runner-lookup-patience: add a process-wide LookupPatience policy and retry_while_busy helper, wrap the artifact and dismissed-bundle lookup facades so busy-incomplete results retry with capped backoff under patience, install it in the agent runner entry with concise retry log lines, and test the default single-attempt path stays unchanged.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vh.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vh.1/README.md) | [sase-1vh.1](sase-1vh.1.md) | 0 |
