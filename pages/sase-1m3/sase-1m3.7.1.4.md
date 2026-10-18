# Bead: sase-1m3.7.1.4 — Code facet dispatch, coverage, and deduplicated aggregates

[Bead Pages](../README.md) / [sase-1m3.7.1](sase-1m3.7.1.md) / sase-1m3.7.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1m3.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1m3.7.md) · **Assignee:** `sase-1m3.7.1.4` · **Size:** medium
**Created:** 2026-10-17 02:56:52 EDT · **Closed:** 2026-10-18 08:41:13 EDT
**Plan:** [202610/project\_stats\_code\_records.md](https://github.com/sase-org/sase--plans/blob/main/202610/project_stats_code_records.md)

## Description

query-integration: populate project, repository, and portfolio code results, attach records summaries, avoid unrelated facet work, and verify the public Python binding.

## Notes

[2026-10-18T12:41:13Z · sase-1m3.7.1.4] query-integration: Code facet dispatch, identity-deduplicated aggregates, metadata-only records snapshots, and fingerprint tokens. just test -p sase_core project_stats: 121 passed, 2 ignored. just test -p sase_core_py project_stats: 7 passed (code-only, combined+records, unavailable+zero). sase tool run check in sase-core succeeded (bf961099c9a0f8e3e73209be665ef1b8). sase bead epic-symbols sase-1m3.7.1.4: no leftover --epic-symbol entries. sase consumers already accept nullable Code; no sase tree change.

## Dependencies

- **Depends on:** [sase-1m3.7.1.2](sase-1m3.7.1.2.md) ✓ · ⧖ 2026-10-17
- **Depends on:** [sase-1m3.7.1.3](sase-1m3.7.1.3.md) ✓ · ⧖ 2026-10-17
- **Blocks:** [sase-1m3.7.1.5](sase-1m3.7.1.5.md) ◐ · ⧖ 2026-10-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1m3.7.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1m3.7.1.4/README.md) | [sase-1m3.7.1.4](sase-1m3.7.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@99b10bd`](https://github.com/sase-org/sase-core/commit/99b10bd06212cb2e00d5e78433d0140591cd8cc5) | feat(stats): populate Code facet with identity-deduplicated snapshots | [sase-1m3.7.1.4](sase-1m3.7.1.4.md) | 2026-10-18 08:42:53 EDT |
