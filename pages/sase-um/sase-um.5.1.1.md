# Bead: sase-um.5.1.1 — Fix the three fast-suite failures the gate reports

[Bead Pages](../README.md) / [sase-um.5.1](sase-um.5.1.md) / sase-um.5.1.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-um.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-um.5.md) · **Assignee:** `sase-um.5.1.1` · **Size:** medium
**Created:** 2026-08-27 08:17:49 EDT
**Plan:** [202608/master\_gate\_green.md](https://github.com/sase-org/sase--plans/blob/main/202608/master_gate_green.md)

## Description

fastlane: stop the gate's own SASE_TEST_SHARD leaking into nested run_pytest subprocesses, give chat-path naming an in-process fallback so it no longer needs a developer dotfile, and rewrite the two relation-panel tests that still describe pre-Link-Rail behavior.

## Dependencies

- **Blocks:** [sase-um.5.1.3](sase-um.5.1.3.md) ◐ · ⧖ 2026-08-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-um.5.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-um.5.1.1/README.md) | [sase-um.5.1.1](sase-um.5.1.1.md) | 0 |
