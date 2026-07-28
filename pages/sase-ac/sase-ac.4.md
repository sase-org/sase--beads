# Bead: sase-ac.4 — Normalize the ACE completion project boundary

[Bead Pages](../README.md) / [sase-ac](README.md) / sase-ac.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ac.4` · **Size:** small
**Created:** 2026-07-28 11:41:42 UTC · **Closed:** 2026-07-28 12:56:49 UTC
**Plan:** [202607/xprompt\_project\_identity.md](https://github.com/sase-org/sase--plans/blob/main/202607/xprompt_project_identity.md)

## Description

tui: normalize the project identity the ACE prompt bar derives from the VCS tag and the prompt context, and add the end-to-end regression test for the reported completion failure.

## Notes

[2026-07-28T12:56:20Z · sase-ac.4] Normalized the ACE completion project boundary: _xprompt_arg_assist_project_from_text() now routes both the VCS-tag name and the PromptContext directory key through canonical_xprompt_project(), and prompt_catalog._project_xprompt_dirs() canonicalizes before building per-project token/watch paths. Regression tests added: tests/ace/tui/widgets/test_auto_xprompt_completion.py (menu for '#git:proj #proj/' offers #proj/reads + #proj/sync, directory-key namespace offers nothing, prompt-context key path normalizes) and tests/ace/tui/widgets/test_prompt_live_completion.py (ctrl+l soft completion agrees). Both new normalization tests fail with the src change reverted. Verified: just install, just lint/fmt/symvision green, just test 22929 passed. 'just check' still fails at the pre-existing SDD plan-link validation stage (229 errors across plans back to 202602, none in files touched here).

## Dependencies

- **Depends on:** [sase-ac.2](sase-ac.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ac.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ac.4/README.md) | [sase-ac.4](sase-ac.4.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`b449b8a`](https://github.com/sase-org/sase/commit/b449b8a4b5a133ded4771fa07e22307bf97620cb) | fix(xprompt): normalize ACE completion project identity (sase-ac.4) | [sase-ac.4](sase-ac.4.md) | 2026-07-28 12:58:11 |
