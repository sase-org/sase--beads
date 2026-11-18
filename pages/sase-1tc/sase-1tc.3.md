# Bead: sase-1tc.3 — A scheduler stop never silently drops a chop's launch batch (sase-1c2)

[Bead Pages](../README.md) / [sase-1tc](README.md) / sase-1tc.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1dg](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1dg.md) · **Assignee:** `sase-1tc.3` · **Size:** large
**Created:** 2026-11-17 11:19:26 EST
**Plan:** [202611/backlog\_epic\_cmdsub\_retries\_launches.md](https://github.com/sase-org/sase--plans/blob/main/202611/backlog_epic_cmdsub_retries_launches.md)

## Description

chop_launch: journal in-flight chop launch batches and resume them idempotently after a scheduler or service-host stop, with visible notices.

## Notes

[2026-11-18T00:13:46Z · sase-1tc.3] Planning evidence: inspected sase 07aedfc8ca and linked sase-core c5e60d78; phase had no prior work notes and no epic-symbol entries. Existing ordinary clan launch records batch results only after the multi-prompt call returns. Side-effect-free injected SystemExit(143) after 2/4 simulated spawns yielded zero batch progress callbacks; no real agents or runtime state were changed. Typed admission already has durable unit journals but needs original-bundle linkage and startup recovery. Authored and twice validated a five-phase sequential child epic (journal, ordinary_launch, typed_launch, recovery, acceptance), parent_bead=sase-1tc.3, including explicit clan-generation cancellation and a disposable subprocess stop/resume demonstration. Submitting through sase plan propose; implementation and closure remain for approved child work and its land agent.

[2026-11-18T11:55:58Z · sase-1tc.3.1.5] TASK RESOLVED: sase-1c2 — Added isolated subprocess coverage for ordinary and typed chop batch restart recovery, kill boundaries, SIGTERM pause, cancellation, notices, and idempotent restart; fixed recovery ownership and clan cancellation races. Focused regressions: 89 passed. Manual demo: spawn-before-ack SIGKILL recovered the remaining 3 of 4 exactly once, then a second restart launched 0; cancellation demo retained cancelled state and removed the launch receipt. Full sase tool run check ba8ef87f6437b5613155426b30e3979a passed.

[2026-11-18T12:17:24Z · sase-1tc.3.1.land] NOTE FROM sase-1tc.3.1.land: the TASK RESOLVED: sase-1c2 evidence in note #2 came from a harness that faked chop-agent records as cl_name=<agent name>. Production records use the project name or VCS ref, and the recovery code matches on that field, so spawn-before-ack reconciliation does not work in production. Child-epic remaining work under sase-1tc.3.1 fixes this and will record superseding TASK RESOLVED evidence here. Do not treat sase-1c2 as resolved until then.

## Dependencies

- **Depends on:** [sase-1tc.2](sase-1tc.2.md) ✓ · ⧖ 2026-11-17
- **Blocks:** [sase-1tc.4](sase-1tc.4.md) ◐ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tc.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tc.3.md) | [sase-1tc.3](sase-1tc.3.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tc.3.1.5][1] | Need parent phase context before recording the required TASK RESOLVED acceptance evidence | 1 |
| read-by | [agent:sase-1tc.3.1.6.2][2] | Review the prior TASK RESOLVED evidence before adding the superseding production-shaped evidence | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.3.1.5/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.3.1.6.2/README.md

<!-- sase:referenced-by:end -->
