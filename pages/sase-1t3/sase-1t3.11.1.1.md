# Bead: sase-1t3.11.1.1 — Stream artifact-file queries before Python conversion

[Bead Pages](../README.md) / [sase-1t3.11.1](sase-1t3.11.1.md) / sase-1t3.11.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t3.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.11.md) · **Assignee:** `sase-1t3.11.1.1` · **Size:** medium
**Created:** 2026-11-17 12:30:56 EST · **Closed:** 2026-11-17 14:33:32 EST
**Plan:** [202611/bounded\_log\_queries.md](https://github.com/sase-org/sase--plans/blob/main/202611/bounded_log_queries.md)

## Description

artifact_files: replace the persistent full artifact-file index cache with targeted Rust association queries, preserve full-reader compatibility, and prove retention and result parity.

## Notes

[2026-11-17T19:33:32Z · sase-1t3.11.1.1] Targeted Rust association queries replace the persistent full artifact-file index cache. sase-core streams JSONL with matches_association (exact agent_artifacts_dir OR non-null equal project+raw_timestamp), keeps full-reader compatibility, and proved schema 1/2, VCS rows, explicit_only, 50k unrelated, missing-index, and binding handshake. Python listing uses a bounded targeted cache (128 entries, 0.5s throttle, inode/dev/mtime_ns/size identity, writer invalidation, 1024-row/256KiB skip) and converts via artifact_file_from_dict. Deleted unused Python matches_association. Verified: sase-core just check (prior run), sase tool run check a9e9f49aea5409ef35918f7eea28a221 (fmt, ruff, mypy, symvision, scoped tests), epic-symbols empty.

## Dependencies

- **Blocks:** [sase-1t3.11.1.2](sase-1t3.11.1.2.md) ◐ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.11.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.11.1.1/README.md) | [sase-1t3.11.1.1](sase-1t3.11.1.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@19b89ac`](https://github.com/sase-org/sase-core/commit/19b89ac9dd45fe27546e600926915a88e4dcd27f) | feat(artifact-file): add targeted association query over JSONL index | [sase-1t3.11.1.1](sase-1t3.11.1.1.md) | 2026-11-17 14:34:57 EST |
| sase | [`8a64510`](https://github.com/sase-org/sase/commit/8a6451068e2be0c4bc407484b7c43708adbd289f) | feat(artifact-file): query associations instead of caching the full index | [sase-1t3.11.1.1](sase-1t3.11.1.1.md) | 2026-11-17 14:37:11 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1t3.11.1.1][1] | Need the phase scope, design file, notes, and DECISIONS before continuing implementation | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.11.1.1/README.md

<!-- sase:referenced-by:end -->
