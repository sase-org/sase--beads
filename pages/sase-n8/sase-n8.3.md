# Bead: sase-n8.3 — Python wire mirror, facade call, and skew probes

[Bead Pages](../README.md) / [sase-n8](README.md) / sase-n8.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03t](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03t.md) · **Assignee:** `sase-n8.3` · **Size:** medium
**Created:** 2026-08-16 11:31:32 EDT
**Plan:** [202608/launch\_control\_alias\_history.md](https://github.com/sase-org/sase--plans/blob/main/202608/launch_control_alias_history.md)

## Description

wire: mirror the new core contract on the Python side — alias trail/origin on the marker wires, a new agent_alias_history_wire module with its to_dict/from_dict helpers, a `query_agent_alias_history` facade function under the artifact-index operation lock — and extend the sase_core_rs validator so a stale wheel fails loudly instead of returning empty history.

## Dependencies

- **Depends on:** [sase-n8.2](sase-n8.2.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-n8.5](sase-n8.5.md) ◐ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n8.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n8.3/README.md) | [sase-n8.3](sase-n8.3.md) | 0 |
