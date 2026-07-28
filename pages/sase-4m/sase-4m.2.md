# Bead: sase-4m.2 — Phase 2: Remove Sorting References From Pickers, Docs, And Leader Labels

[Bead Pages](../README.md) / [sase-4m](README.md) / sase-4m.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-4m.2`
**Created:** 2026-06-13 13:04:23 UTC · **Closed:** 2026-06-13 13:52:02 UTC
**Plan:** [202606/prompt\_history\_tui.md](https://github.com/sase-org/sase--plans/blob/main/202606/prompt_history_tui.md)

## Notes

COMMIT: 2ed96b403

[2026-07-27T21:34:06Z · sase-a1.land] [2026-06-13T13:49:57Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Completed Phase 2 prompt-history presentation cleanup: prompt history modal rows now show cancelled marker, last-used timestamp, and prompt preview only; modal filtering matches prompt text only; preview metadata no longer displays legacy branch/workspace context; CLI fzf picker uses recency-only history with a neutral recency header; VCS-dot reuse still replaces embedded VCS tags without sorting by VCS ref; leader/help/docs/blog references to CL/project-ranked prompt history and */~ markers were removed. Verification: just test tests/ace/tui/modals/test_prompt_history_modal.py tests/test_special_cases.py tests/test_command_catalog.py; just check.

## Dependencies

- **Depends on:** [sase-4m.1](sase-4m.1.md) ✓
- **Blocks:** [sase-4m.3](sase-4m.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-4m.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-4m.2/README.md) | [sase-4m.2](sase-4m.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`ac817e0`](https://github.com/sase-org/sase/commit/ac817e0c19098d2b3fda8f432094e69af1cb61ee) | fix(ace): remove prompt history sorting references (sase-4m.2) | [sase-4m.2](sase-4m.2.md) | 2026-06-13 13:52:42 |
