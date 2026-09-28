# Bead: sase-1ca.5 — Quitting the TUI stashes an open prompt draft

[Bead Pages](../README.md) / [sase-1ca](README.md) / sase-1ca.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tt.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tt.w0.md) · **Assignee:** `sase-1ca.5` · **Size:** small
**Created:** 2026-09-28 17:30:15 EDT · **Closed:** 2026-09-28 18:31:07 EDT
**Plan:** [202609/never\_lose\_stashed\_prompts.md](https://github.com/sase-org/sase--plans/blob/main/202609/never_lose_stashed_prompts.md)

## Description

quit-preserves-draft: generalize the pre-restart stash helper and call it on explicit quit paths (source=quit), cancel the exit if the stash write fails, mention the draft in the quit-confirm impact, with tests.

## Notes

[2026-09-28T22:30:48Z · sase-1ca.5--1] PROPOSED FOLLOW-UP: just check lint (feature flags) failed transiently on rule 7 (closed flag bead sase-1be still had surviving agent_tabs definition); unrelated to this bead (diff touches no agent_tabs lines) and sase-1be has since been reopened — tools/check_feature_flags now exits 0

[2026-09-28T22:31:07Z · sase-1ca.5--1] quit-preserves-draft done: quit paths stash open draft with source=quit, exit cancelled on stash-write failure, draft mentioned in quit-confirm impact; 8 new tests in tests/ace/tui/test_quit_prompt_stash.py pass plus 36 related stash tests (44 total); ruff/mypy/fmt passed in monitored just check; flags-lint failure was transient sase-1be state, now exits 0; no epic-symbol leftovers

## Dependencies

- **Depends on:** [sase-1ca.4](sase-1ca.4.md) ✓ · ⧖ 2026-09-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ca.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ca.5.md) | [sase-1ca.5](sase-1ca.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`67f4a1d`](https://github.com/sase-org/sase/commit/67f4a1d1ec72670cfe936f587b200eb1766c71fa) | feat(ace): stash open prompt draft on TUI quit paths | [sase-1ca.5](sase-1ca.5.md) | 2026-09-28 18:32:25 EDT |
