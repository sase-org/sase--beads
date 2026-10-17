# Bead: sase-1m3.7.1.1 — Role policy, nonblank counter, and measurement contracts

[Bead Pages](../README.md) / [sase-1m3.7.1](sase-1m3.7.1.md) / sase-1m3.7.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1m3.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1m3.7.md) · **Assignee:** `sase-1m3.7.1.1` · **Size:** medium
**Created:** 2026-10-17 02:56:50 EDT · **Closed:** 2026-10-17 07:53:29 EDT
**Plan:** [202610/project\_stats\_code\_records.md](https://github.com/sase-org/sase--plans/blob/main/202610/project_stats_code_records.md)

## Description

counter-policy: implement pure nonblank counting and role classification, and finish the wire contracts needed by code and records snapshots.

## Notes

[2026-10-17T11:53:29Z · sase-1m3.7.1.1] Implemented nullable code/records snapshot contracts, typed role/exclusion rows, pure committed-attribute classification, bounded shebang language detection, and nonblank counting. Verified with just fmt, just test -p sase_core project_stats (69 passed, 1 ignored), just test -p sase_core_py project_stats (4 passed), sase tool run check (passed), and epic-symbol check (no entries).

## Dependencies

- **Blocks:** [sase-1m3.7.1.2](sase-1m3.7.1.2.md) ✓ · ⧖ 2026-10-17
- **Blocks:** [sase-1m3.7.1.3](sase-1m3.7.1.3.md) ✓ · ⧖ 2026-10-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1m3.7.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1m3.7.1.1/README.md) | [sase-1m3.7.1.1](sase-1m3.7.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@df833a0`](https://github.com/sase-org/sase-core/commit/df833a04beaa4205620a75f0b2a11c1fc89a9db4) | feat(project-stats): add classifier, nonblank counter, and wire contracts | [sase-1m3.7.1.1](sase-1m3.7.1.1.md) | 2026-10-17 07:54:34 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1m3.7.1.1][1] | Verify the assigned phase is closed with its verification note | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1m3.7.1.1/README.md

<!-- sase:referenced-by:end -->
