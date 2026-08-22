# Bead: sase-s1.5 — Accept equivalent canonical PyPI registry spellings in the release ratchet

[Bead Pages](../README.md) / [sase-s1](README.md) / sase-s1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0al](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0al.md) · **Assignee:** `sase-s1.5` · **Size:** small
**Created:** 2026-08-22 12:30:22 UTC · **Closed:** 2026-08-22 13:16:56 UTC
**Plan:** [202608/restore\_github\_actions.md](https://github.com/sase-org/sase--plans/blob/main/202608/restore_github_actions.md)

## Description

release-lock-normalization: normalize only the trailing-slash-equivalent PyPI simple-index source and keep all non-PyPI lock rewrites fail-closed.

## Notes

[2026-08-22T12:57:03Z · sase-s1.5] PROPOSED FOLLOW-UP: Refresh generated SASE memory/provider shims — just check fails in SASE validation because init memory --check reports 7 managed memory/shim files out of sync; memory edits require explicit owner permission.

[2026-08-22T13:16:56Z · sase-s1.5] Implemented canonical PyPI source normalization for transitive lock refreshes. Verified .venv/bin/python -m pytest tests/test_ratchet_core_window_tool.py tests/test_ratchet_core_window_source_normalization.py (32 passed) and epic-symbols clean. just check passed lint/toobig gates but failed SASE validation on unrelated init memory --check drift; just test-scoped escalated to full suite and failed in other epic lanes (missing sase-xprompt-lsp, skills rendering drift, contract manifest), not in ratchet tests.

## Dependencies

- **Blocks:** [sase-s1.6](sase-s1.6.md) ◐ · ⧖ 2026-08-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-s1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s1.5/README.md) | [sase-s1.5](sase-s1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c718da9`](https://github.com/sase-org/sase/commit/c718da9119cf8dccf4a2719a8ce6717991f1ebd1) | fix(release): normalize canonical PyPI lock sources | [sase-s1.5](sase-s1.5.md) | 2026-08-22 13:22:48 UTC |
