# Bead: sase-52.3 — Phase 3: ACE Prompt Editing Behavior

[Bead Pages](../README.md) / [sase-52](README.md) / sase-52.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-52.3`
**Created:** 2026-06-20 18:31:24 UTC · **Closed:** 2026-06-20 19:45:28 UTC
**Plan:** [202606/alt\_brace\_syntax.md](https://github.com/sase-org/sase--plans/blob/main/202606/alt_brace_syntax.md)

## Description

Repo: sase workspace 10. Implement prompt input typing/deleting with pure helpers and Textual tests. Add src/sase/ace/tui/widgets/_alt_syntax_editing.py (detect cursor inside %{...}, directive-valid %{ openings, plan %{} auto-pair, paired {} deletion, | separator insertion). | insertion only inside live %{...}, normalize single spaces, cursor before }, normalize comma spacing so %{foo ,bar, and baz| -> %{foo, bar, and baz | }. Integrate into PromptTextAreaKeyHandlingMixin._on_key() and PromptTextAreaActionsMixin.action_delete_left()/action_delete_right(). No sync I/O on event loop. Add tests/ace/tui/widgets/test_prompt_alt_syntax_editing.py. Validation: pytest tests/ace/tui/widgets/test_prompt_alt_syntax_editing.py; pytest tests/ace/tui/widgets/test_directive_completion.py.

## Notes

COMMIT: 0f7b898a8

## Dependencies

- **Depends on:** [sase-52.1](sase-52.1.md) ✓
- **Blocks:** [sase-52.7](sase-52.7.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-52.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-52.3/README.md) | [sase-52.3](sase-52.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`2e5d157`](https://github.com/sase-org/sase/commit/2e5d1578bc4b4b154507414687354c059784c477) | feat(ace): add %{...} alt-shorthand prompt editing behavior (sase-52.3) | [sase-52.3](sase-52.3.md) | 2026-06-20 19:48:18 |
