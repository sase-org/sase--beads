# Bead: sase-1tc.3.1.6.4 — Re-prove recovery with production-shaped evidence and record corrected acceptance

[Bead Pages](../README.md) / [sase-1tc.3.1.6](sase-1tc.3.1.6.md) / sase-1tc.3.1.6.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tc.3.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tc.3.1.land.md) · **Assignee:** `sase-1tc.3.1.6.4` · **Size:** medium
**Created:** 2026-11-18 07:19:04 EST · **Closed:** 2026-11-18 15:25:13 EST
**Plan:** [202611/chop\_recovery\_defects.md](https://github.com/sase-org/sase--plans/blob/main/202611/chop_recovery_defects.md)

## Description

acceptance: rerun the subprocess harness with real chop linkage records and name registry evidence, add the routine/manual race and crossing-cancel cases, repeat the disposable demonstration, and record corrected TASK RESOLVED evidence on sase-1tc.3. See Phase acceptance.

## Notes

[2026-11-18T20:25:01Z · sase-1tc.3.1.6.4] Acceptance evidence (same TASK RESOLVED record as on sase-1tc.3): 17/17 production-shaped subprocess scenarios green covering ordinary + typed k-of-n, SIGKILL windows, SIGTERM pause, second-restart-zero, routine/manual race, recovery-active crossing cancel, multi-clan, two-episode notices, typed kill/cancel/race. Product fixes: run-history backfill from durable linkage (ordinary) + resumed/reconstruct merge (typed); typed lost-ack replay for linkage-proven dispatching units; finish-notice-before-release ordering for exactly-once episode notices. Verified: focused suites 57+59+48+6 green; sase tool run check a070819049c2e7ea8a5669652cb2ff29 succeeded; demo repeated; epic-symbols clear; no Rust/pin changes.

[2026-11-18T20:25:13Z · sase-1tc.3.1.6.4] Verified: 17/17 production-shaped subprocess acceptance scenarios green (ordinary+typed k-of-n, SIGKILL windows, SIGTERM pause, second-restart-zero, routine/manual race with live-owner holdoff, recovery-active crossing settle, multi-clan, two-episode notices, typed kill/cancel/race); run history lists all n launches once; exactly-once episode notices incl. racing delivery; focused suites green; sase tool run check a070819049c2e7ea8a5669652cb2ff29 succeeded (lint+scoped lane); demo repeated; epic-symbols clear; corrected TASK RESOLVED recorded on sase-1tc.3 superseding its note #2.

## Dependencies

- **Depends on:** [sase-1tc.3.1.6.3](sase-1tc.3.1.6.3.md) ✓ · ⧖ 2026-11-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tc.3.1.6.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.3.1.6.4/README.md) | [sase-1tc.3.1.6.4](sase-1tc.3.1.6.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5b08952`](https://github.com/sase-org/sase/commit/5b08952c6d8dd69b6b1731989a3580c61b3d660e) | feat(axe): re-prove chop batch recovery with production-shaped acceptance evidence | [sase-1tc.3.1.6.4](sase-1tc.3.1.6.4.md) | 2026-11-18 15:27:35 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tc.3.1.6.2][1] | Need the epic decisions and sibling phase work before implementation | 1 |
| read-by | [agent:sase-1tc.3.1.6.3][2] | Need earlier phase landing evidence and current acceptance phase ownership to avoid overlap | 1 |
| read-by | [agent:sase-1tc.3.1.6.4][3] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.3.1.6.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.3.1.6.3/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.3.1.6.4/README.md

<!-- sase:referenced-by:end -->
