# Bead: sase-1qz.1 — sase-core: hijack statuses, ledger wire, and eligibility

[Bead Pages](../README.md) / [sase-1qz](README.md) / sase-1qz.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.33.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.33.linker.w0.md) · **Assignee:** `sase-1qz.1` · **Size:** medium
**Created:** 2026-11-02 17:42:14 EST · **Closed:** 2026-11-02 20:43:49 EST
**Plan:** [202611/agent\_hijack.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack.md)

## Description

core_ledger: in sase-core, add the HIJACKED/ESCALATED/CONTINUED status rows and the done-marker-to-status mapping, the AgentHijackRecordWire v1 state machine, the eligibility function, and the auto-restart exclusion. Then expose PyO3 bindings, bump sase's pin, and add the thin Python wrappers.

## Notes

[2026-11-03T01:43:20Z · sase-1qz.1] PROPOSED FOLLOW-UP: Investigate baseline monitor settlement and sudo ledger reclaimer failures — the monitor starter race and both sudo settlement tests failed identically on clean base commit 4dc226bdea; TUI startup-toast and pulse-navigation failures from ToolRun 4ef1b69fcd passed in the clean-base rerun; no existing task bead was found.

[2026-11-03T01:43:49Z · sase-1qz.1] Implemented core hijack ledger/state transitions, eligibility, status/done-marker mapping, auto-restart exclusion, PyO3 bindings, and Python wrappers. Rust and binding focused tests passed (12 core, 2 PyO3, plus run-state classification); just check lint/validation passed but scoped tests had 5 unrelated failures, 3 of which reproduced on clean base and are recorded as a proposed follow-up. Epic-symbol scan was clear.

## Dependencies

- **Blocks:** [sase-1qz.3](sase-1qz.3.md) ◐ · ⧖ 2026-11-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1qz.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1qz.1/README.md) | [sase-1qz.1](sase-1qz.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@65925ca`](https://github.com/sase-org/sase-core/commit/65925ca8b6427fc0037c9ddbb5ebba8e6927fabe) | feat(agent-hijack): add core ledger and eligibility | [sase-1qz.1](sase-1qz.1.md) | 2026-11-02 20:45:42 EST |
| sase | [`85c8d46`](https://github.com/sase-org/sase/commit/85c8d4613a3a8ef06ec2e67de6c398d59b92b412) | feat(agent-hijack): add Python hijack workflow wrappers | [sase-1qz.1](sase-1qz.1.md) | 2026-11-02 20:48:03 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1qz.1][1] | Need the phase scope and design file | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1qz.1/README.md

<!-- sase:referenced-by:end -->
