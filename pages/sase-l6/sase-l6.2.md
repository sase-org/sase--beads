# Bead: sase-l6.2 — One parse per store change, not per agent

[Bead Pages](../README.md) / [sase-l6](README.md) / sase-l6.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zw](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zw.md) · **Assignee:** `sase-l6.2` · **Size:** medium
**Created:** 2026-08-13 15:24:05 EDT · **Closed:** 2026-08-13 16:20:59 EDT
**Plan:** [202608/sase\_context\_incremental.md](https://github.com/sase-org/sase--plans/blob/main/202608/sase_context_incremental.md)

## Description

stores: give the artifact-file index, the memory-read log, and the skill-use log process-wide revalidating snapshot caches so N agents share one parse instead of paying a full re-read each, and invalidate them from the write paths.

## Notes

[2026-08-13T20:18:27Z · sase-l6.2] PROPOSED FOLLOW-UP: symvision unused public function — just check currently fails lint (symvision) on stream_and_parse_messages_json_output in src/sase/llm_provider/_subprocess_claude.py; this phase did not touch that file.

[2026-08-13T20:20:59Z · sase-l6.2] Implemented process-wide revalidating caches for artifact-file index reads plus memory-read and skill-use log snapshots; verified .venv/bin/pytest tests/ace/tui/test_memory_reads_loader.py tests/ace/tui/test_skill_uses_loader.py tests/artifact_file_facade/test_storage.py passed 37 tests, and .venv/bin/python tests/perf/bench_detail_header_summary.py --include-home --count 20 --runs 2 completed with home artifact_file_paths warm p50 5.2 ms. Ran just check after just install; it passed fmt, ruff, mypy, and earlier lint gates, then failed on unrelated symvision unused public stream_and_parse_messages_json_output in src/sase/llm_provider/_subprocess_claude.py; recorded that as a PROPOSED FOLLOW-UP on this phase.

[2026-08-13T20:22:27Z · sase-l6.2] Verified focused pytest for memory, skill, and artifact cache tests; ran benchmark_detail_header_summary live-home first-20-agent shape; just check passed until unrelated existing symvision unused-public-function failure, recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-l6.1](sase-l6.1.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-l6.6](sase-l6.6.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-l6.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-l6.2/README.md) | [sase-l6.2](sase-l6.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`093088a`](https://github.com/sase-org/sase/commit/093088abb9ed95e592b190778f420d654374b1b8) | perf: cache shared store snapshots | [sase-l6.2](sase-l6.2.md) | 2026-08-13 16:23:25 EDT |
