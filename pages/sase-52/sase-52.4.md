# Bead: sase-52.4 — Phase 4: ACE Prompt Syntax Highlighting

[Bead Pages](../README.md) / [sase-52](README.md) / sase-52.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-52.4`
**Created:** 2026-06-20 18:32:05 UTC · **Closed:** 2026-06-20 19:36:39 UTC
**Plan:** [202606/alt\_brace\_syntax.md](https://github.com/sase-org/sase--plans/blob/main/202606/alt_brace_syntax.md)

## Description

Repo: sase workspace 10. Add visual treatment for %{...} in the prompt input widget. Extend the existing overlay approach (not a separate highlighter). Add spans for %{ opener and } closer, top-level | separators, optional branch names before top-level =, and unmatched opener/closer as warning/error spans. Keep the _jinja_highlight.py size guards (_MAX_OVERLAY_BYTES, _MAX_OVERLAY_LINES). Register theme styles via current app theme. Add tests proving alt highlighting coexists with Jinja and search overlays. Validation: pytest tests/ace/tui/widgets/test_prompt_alt_syntax_highlight.py; pytest tests/ace/tui/widgets/test_prompt_search_highlight.py; if visual snapshots affected run just test-visual and inspect diffs.

## Notes

COMMIT: e34d8e91b

## Dependencies

- **Depends on:** [sase-52.1](sase-52.1.md) ✓
- **Blocks:** [sase-52.7](sase-52.7.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-52.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-52.4/README.md) | [sase-52.4](sase-52.4.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`57e9fd6`](https://github.com/sase-org/sase/commit/57e9fd6f35f9ef2f197d65ffe97a6dd422b426df) | feat(tui): highlight %{...} alt shorthand in ACE prompt input (sase-52.4) | [sase-52.4](sase-52.4.md) | 2026-06-20 19:37:49 |
