# Bead: sase-1vn.4.1.3 — Durable activation and recovery claims

[Bead Pages](../README.md) / [sase-1vn.4.1](sase-1vn.4.1.md) / sase-1vn.4.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1vn.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vn.4.md) · **Assignee:** `sase-1vn.4.1.3` · **Size:** medium
**Created:** 2026-11-27 20:17:45 EST · **Closed:** 2026-11-27 23:46:50 EST
**Plan:** [202611/zombie\_epic\_liveness.md](https://github.com/sase-org/sase--plans/blob/main/202611/zombie_epic_liveness.md)

## Description

recovery-claims: implement core-owned activation and recovery records and the machine publication adapter, including concurrent publisher and restart tests. Expose a verified claim to callers but do not submit any launch.

## Notes

[2026-11-28T04:46:30Z · sase-1vn.4.1.3] PROPOSED FOLLOW-UP: KNOWN scoped-check failure tests/ace/tui/test_refresh_warmup_gc.py::test_auto_refresh_merge_live_hints_and_warmup_release_obsolete_payloads (witness 207e3123deeb63f052eb1d7f3f587184, possible owner sase-1v2) — unrelated to recovery claims; close anyway per phase rules

[2026-11-28T04:46:50Z · sase-1vn.4.1.3] Verified core-owned recovery activation/claims (create-if-absent, SHA-256 keys, malformed disable, concurrent local winner) plus machine publication adapter (refresh/commit/push/replay; launch_permit only for published winner). sase-core check passed; sase check no_new_failures (1 KNOWN ACE TUI test owned by sase-1v2). No proc/agent submit; automatic recovery still disabled. Epic-symbols for this phase: none (later-phase rows keyed to sase-1vn.4.1.4 and sase-1vn.4.1.5).

## Dependencies

- **Depends on:** [sase-1vn.4.1.2](sase-1vn.4.1.2.md) ✓ · ⧖ 2026-11-27
- **Blocks:** [sase-1vn.4.1.4](sase-1vn.4.1.4.md) ◐ · ⧖ 2026-11-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vn.4.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vn.4.1.3/README.md) | [sase-1vn.4.1.3](sase-1vn.4.1.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@d741692`](https://github.com/sase-org/sase-core/commit/d7416921f526aac66c095674080607dfaa612fd2) | feat(bead): add durable recovery activation and claim records | [sase-1vn.4.1.3](sase-1vn.4.1.3.md) | 2026-11-27 23:48:00 EST |
| sase | [`21bdca5`](https://github.com/sase-org/sase/commit/21bdca56adcf459bbff96257f6a1e8365d64ea4f) | feat(bead): add machine-owned recovery claim publication adapter | [sase-1vn.4.1.3](sase-1vn.4.1.3.md) | 2026-11-27 23:49:10 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1vn.4.1.3][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vn.4.1.3/README.md

<!-- sase:referenced-by:end -->
