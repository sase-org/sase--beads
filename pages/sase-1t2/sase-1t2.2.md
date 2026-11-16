# Bead: sase-1t2.2 — Keep the hijack capability stamp and read the model facts runners actually write

[Bead Pages](../README.md) / [sase-1t2](README.md) / sase-1t2.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ct](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ct.md) · **Assignee:** `sase-1t2.2` · **Size:** small
**Created:** 2026-11-15 20:00:08 EST
**Plan:** [202611/agent\_hijack\_dependability.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack_dependability.md)

## Description

meta_facts: fix D3 (runner_capabilities erased by directive extraction) with one shared RUNNER_BOOT_META_KEYS tuple, a runner-side re-stamp, and an invariant test. Fix D4 (wrong model-fact keys, float-only booted_at, monitor/gate classified from live rows or never-written keys) using durable records and a fixture captured from a real runner meta.

## Dependencies

- **Blocks:** [sase-1t2.4](sase-1t2.4.md) ◐ · ⧖ 2026-11-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.2/README.md) | [sase-1t2.2](sase-1t2.2.md) | 0 |
