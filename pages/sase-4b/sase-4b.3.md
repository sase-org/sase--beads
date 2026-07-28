# Bead: sase-4b.3 — Phase 3: Refactor xprompts/reads.md to Use Dataview

[Bead Pages](../README.md) / [sase-4b](README.md) / sase-4b.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-4b.3`
**Created:** 2026-06-03 19:57:38 UTC · **Closed:** 2026-06-03 20:34:38 UTC
**Plan:** [202606/bob\_dataview\_reads.md](https://github.com/sase-org/sase--plans/blob/main/202606/bob_dataview_reads.md)

## Notes

COMMIT: b8695c980

[2026-07-27T19:12:47Z · sase-a1.6] [2026-06-03T20:33:09Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Refactored xprompts/reads.md from notes to reference_query with the default #ai/reference Dataview table query. Research agents now use /bob_dataview before web search, and the final segment refers to the query/table exclusion source. Updated local-helper tests. Verification: .venv/bin/pytest tests/test_multi_agent_xprompt_local_helpers.py tests/test_multi_agent_xprompt_expansion.py; sase xprompt explain/list for sase/reads; just check.

[2026-07-27T19:12:58Z · sase-a1.6] [2026-06-03T20:35:00Z · bryanbugyi34@gmail.com] (restored 2026-07-27) COMMIT: f331cab83

## Dependencies

- **Depends on:** [sase-4b.2](sase-4b.2.md) ✓
- **Blocks:** [sase-4b.4](sase-4b.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-4b.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-4b.3/README.md) | [sase-4b.3](sase-4b.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`b8695c9`](https://github.com/sase-org/sase/commit/b8695c980a0137552c331b85b3d5fef246cd11ec) | feat: use Dataview references in reads xprompt (sase-4b.3) | [sase-4b.3](sase-4b.3.md) | 2026-06-03 20:35:07 |
