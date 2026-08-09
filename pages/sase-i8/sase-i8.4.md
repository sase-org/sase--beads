# Bead: sase-i8.4 — Collection models and the merges query key

[Bead Pages](../README.md) / [sase-i8](README.md) / sase-i8.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wl](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wl/README.md) · **Assignee:** `sase-i8.4` · **Size:** medium
**Created:** 2026-08-09 09:43:43 EDT · **Closed:** 2026-08-09 12:59:45 EDT
**Plan:** [202608/merge\_commit\_support.md](https://github.com/sase-org/sase--plans/blob/main/202608/merge_commit_support.md)

## Description

collect: carry merge visibility through the collection filters and the commit filter-query language, including the in-memory matcher, canonical tokens, completions, and snapshot-coverage rules that keep live preview honest.

## Notes

[2026-08-09T16:59:14Z · sase-i8.4] PROPOSED FOLLOW-UP: investigate intermittent full-suite failure in tests/test_vcs_provider_vcs_log.py::test_remote_log_ops_fetch_partition_and_union_log — one full fast-lane run failed once, then isolated and xdist reruns plus a final just check passed.

[2026-08-09T16:59:45Z · sase-i8.4] Implemented collection/query merge visibility; verified focused query/collection/Commits UI tests, Commits PNG visual snapshots, and final just check passing (scoped lane escalated to full suite).

[2026-08-09T17:07:05Z · sase-i8.4] PROPOSED FOLLOW-UP: investigate intermittent full-suite failure in tests/ace/tui/widgets/test_prompt_xprompt_highlight.py::test_xprompt_highlight_overlay_marks_spans_and_registers_styles — one full fast-lane run failed once, then direct and xdist isolated reruns passed.

[2026-08-09T17:15:38Z · sase-i8.4] Post-close verification: final just check passed on the current tree; scoped selection escalated to the full fast suite because src-data-asset changed.

[2026-08-09T17:16:38Z · sase-i8.4] Implemented merge visibility collection/query integration and verified with focused query/collection/UI tests, Commits visual snapshots, and final just check.

## Dependencies

- **Depends on:** [sase-i8.3](sase-i8.3.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-i8.5](sase-i8.5.md) ◐ · ⧖ 2026-08-09
- **Blocks:** [sase-i8.6](sase-i8.6.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i8.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i8.4/README.md) | [sase-i8.4](sase-i8.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8795cd2`](https://github.com/sase-org/sase/commit/8795cd2b2309c4d384a6f6ba40d727cee6e14e21) | feat(vcs-log): add merge visibility filters | [sase-i8.4](sase-i8.4.md) | 2026-08-09 13:18:14 EDT |
