# Bead: sase-1pt.6 — Host-owned background publication job

[Bead Pages](../README.md) / [sase-1pt](README.md) / sase-1pt.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.15z](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.15z.md) · **Assignee:** `sase-1pt.6` · **Size:** medium
**Created:** 2026-10-29 18:11:08 EDT · **Closed:** 2026-10-30 00:25:26 EDT
**Plan:** [202610/commit\_stage\_async\_publication.md](https://github.com/sase-org/sase--plans/blob/main/202610/commit_stage_async_publication.md)

## Description

publisher: add a doorbell-triggered scheduler job that drains agent-hood requests, hinted link-outbox agents, and unfenced referenced-by requests under the existing lock, plus a heartbeat and a real drain bound in the secret scanner.

## Notes

[2026-10-30T04:16:34Z · sase-1pt.6] PROPOSED FOLLOW-UP: Triage the existing scoped pytest failure signatures seen in ToolRun 276f775223952336bb2be21f65a708a0 — the run classified five as KNOWN with independent witness 7d5e13601cd011bbfc0951b64918e6d8 and two as FLAKY; no tracking task bead was surfaced.

[2026-10-30T04:25:26Z · sase-1pt.6] Implemented the doorbell-triggered publication job, durable hint and heartbeat handling, bounded prioritized drains, scheduler registration, timeout propagation, docs, and crash-recovery, liveness, and deferral coverage. just fix and git diff --check passed. The completed check ToolRun passed all non-test stages and triaged pytest as no-new-failures, with existing KNOWN and FLAKY signatures recorded for follow-up. epic-symbols reported no leftovers.

## Dependencies

- **Depends on:** [sase-1pt.1](sase-1pt.1.md) ✓ · ⧖ 2026-10-29
- **Blocks:** [sase-1pt.7](sase-1pt.7.md) ◐ · ⧖ 2026-10-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pt.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pt.6/README.md) | [sase-1pt.6](sase-1pt.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4356cff`](https://github.com/sase-org/sase/commit/4356cffaa1678646cab8a2d9c40375a90186a5fa) | feat(agents-sync): add background publication job | [sase-1pt.6](sase-1pt.6.md) | 2026-10-30 01:19:13 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pt.6][1] | Need the phase scope and design file | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pt.6/README.md

<!-- sase:referenced-by:end -->
