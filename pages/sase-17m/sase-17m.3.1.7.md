# Bead: sase-17m.3.1.7 — Classification sweep and phase verification

[Bead Pages](../README.md) / [sase-17m.3.1](sase-17m.3.1.md) / sase-17m.3.1.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.3.md) · **Assignee:** `sase-17m.3.1.7` · **Size:** small
**Created:** 2026-09-24 02:56:51 EDT · **Closed:** 2026-09-24 10:49:22 EDT
**Plan:** [202609/agent\_session\_wire\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_wire_cutover.md)

## Description

verify: sweep the wire-cutover surfaces for remaining agent-family keys, confirm every durable surface has a legacy-input test and a no-legacy-emitted test, run sase tool run check, and record hand-offs for runtime-cutover, ace-cutover, and core-contract on the sase-17m.3 phase bead.

## Notes

[2026-09-24T14:48:15Z · sase-17m.3.1.7] PROPOSED FOLLOW-UP: sase tool run check is red on unrelated tool_run_claim / tool_run_request_stop bindings required by HEAD validator but absent from pinned core eef7ca4

[2026-09-24T14:49:22Z · sase-17m.3.1.7] Verify sweep done: remaining agent-family literals are all in named legacy readers/boundary helpers with legacy comments (plan_chain LEGACY_* constants, agent_bundle LEGACY_AGENT_FIELD_NAMES, fleet new-then-legacy hydrations, capacity agent_family_parallel boundary awaiting core-contract); cli_list JSON keys handed to runtime-cutover. Legacy-input + no-legacy-emitted tests confirmed for durable surfaces, wire mirrors, canonical keys, agent model, and name-registry v2->v3; 113 focused tests pass. sase tool run check fails only on unrelated tool_run_claim/tool_run_request_stop bindings (HEAD validator vs pinned core eef7ca4), recorded as PROPOSED FOLLOW-UP. Hand-offs for runtime-cutover, ace-cutover, core-contract recorded on sase-17m.3.

## Dependencies

- **Depends on:** [sase-17m.3.1.5](sase-17m.3.1.5.md) ✓ · ⧖ 2026-09-24
- **Depends on:** [sase-17m.3.1.6](sase-17m.3.1.6.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.3.1.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.7/README.md) | [sase-17m.3.1.7](sase-17m.3.1.7.md) | 0 |
