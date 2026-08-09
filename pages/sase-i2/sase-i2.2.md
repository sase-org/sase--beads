# Bead: sase-i2.2 — Underline glossary semantic tokens in LSP-backed editors

[Bead Pages](../README.md) / [sase-i2](README.md) / sase-i2.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.w9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.w9/README.md) · **Assignee:** `sase-i2.2` · **Size:** medium
**Created:** 2026-08-09 07:49:54 EDT · **Closed:** 2026-08-09 08:16:02 EDT
**Plan:** [202608/glossary\_term\_underline.md](https://github.com/sase-org/sase--plans/blob/main/202608/glossary_term_underline.md)

## Description

editor: give sase-nvim an overridable `SaseGlossaryTerm` underline applied to the xprompt LSP's glossary semantic tokens through `LspTokenUpdate`, with a headless test, README coverage, and corrected editor/LSP documentation in the sase repo.

## Notes

[2026-08-09T12:14:45Z · sase-i2.2] PROPOSED FOLLOW-UP: investigate flaky plan approval full-suite failure — first just check escalated to the full suite and failed tests/test_plan_approval_actions.py::test_headless_epic_approval_submits_while_inflight_launch_holds_anchor once; isolated rerun passed and a second just check passed.

[2026-08-09T12:16:02Z · sase-i2.2] Implemented sase-nvim SaseGlossaryTerm LspTokenUpdate wiring, headless coverage, README docs, and SASE editor/xprompt docs. Verified nvim --headless tests/glossary_highlight.lua, nvim --headless tests/alt_highlight.lua, just install, just fmt, and just check on rerun; first full-suite flake was isolated and recorded as a proposed follow-up.

[2026-08-09T12:17:12Z · sase-i2.2] Verified nvim headless glossary_highlight and alt_highlight tests, just install, just fmt, and just check passing on rerun.

[2026-08-09T12:23:34Z · sase-i2.2] PROPOSED FOLLOW-UP: Investigate sase_git_commit publication resume failure — main and linked repo create_commit runs pushed their primary commits, but post-primary publication/resume failed with "No item with that key".

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i2.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i2.2/README.md) | [sase-i2.2](sase-i2.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a787f36`](https://github.com/sase-org/sase/commit/a787f36fa5024267cfafb75381ef89a3d574b810) | docs(editor): document glossary semantic token styling | [sase-i2.2](sase-i2.2.md) | 2026-08-09 08:18:32 EDT |
