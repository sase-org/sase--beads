# Bead: sase-1nf.9 — Instrument and measure agent-hood publication drains

[Bead Pages](../README.md) / [sase-1nf](README.md) / sase-1nf.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.12i](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.12i.md) · **Assignee:** `sase-1nf.9` · **Size:** medium
**Created:** 2026-10-20 13:36:15 EDT · **Closed:** 2026-10-20 15:15:47 EDT
**Plan:** [202610/athena\_apollo\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/athena_apollo_audit_fixes.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:1332edd16fbe66b228322d62 | attached via sase artifact create --bead |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

<!-- sase:links:end -->

## Description

pub-measure: supersede the stalled sase-11o epic, add permanent stage timing, a sync-lock holder record, and richer outbox doctor output, then measure one representative drain on athena and inspect apollo's wedged clone read-only, and publish the findings as a research report.

## Notes

[2026-10-20T18:43:36Z · sase-1nf.9] HANDOFF: all pub-measure work is done (sase-11o/11o.2 superseded; drain-timing JSONL; lock-holder record; doctor histogram/age/sidecar; tools/agents_publication_profile; athena measurement ~210s inventory + ~14s plan_hoods; apollo RO inspection; report sase/repos/research/202610/pub_drain_measurement.md attached as file:explicit:1332edd16fbe66b228322d62). just check is still running as ToolRun 8975926dd9d8ba2622576004678f15c7; 72 targeted tests already pass. Remaining: read the verdict, run epic-symbols (currently clean), close this bead.

[2026-10-20T19:15:47Z · sase-1nf.9--2] pub-measure done and verified: sase-11o superseded, drain-timing JSONL (publication_timing), lock-holder record + lock_holder_diagnostic (git_sync_ops), doctor histogram/oldest-age/sidecar states, profiling harness tools/agents_publication_profile (docs-referenced for pyscripts Rule 1), athena measurement + apollo RO inspection, research report attached as file:explicit:1332edd16fbe66b228322d62. Fixed 5 NEW symvision unused-public findings by privatizing in-file-only helpers (_SyncLockHolder, _read/_write/_clear_lock_holder, _drain_log_path); public lock_holder_diagnostic kept (used by commit_publication). sase tool run check 80bda70f026a3b811a63c9743073e2a5 verdict pass (all lint incl. symvision + 328-file scoped tests green); targeted test_publication_drain_measure 28 passed, mypy clean. No epic-symbol entries.

## Dependencies

- **Blocks:** [sase-1nf.10](sase-1nf.10.md) ◐ · ⧖ 2026-10-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.9.md) | [sase-1nf.9](sase-1nf.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1325078`](https://github.com/sase-org/sase/commit/1325078a8edd30df84eaa6356863a8fd35f63c80) | feat(agents-sync): instrument and measure publication drains (sase-1nf.9) | [sase-1nf.9](sase-1nf.9.md) | 2026-10-20 15:17:08 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nf.9--2][1] | Need phase scope and design file for pub-measure closeout | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.9.md

<!-- sase:referenced-by:end -->
