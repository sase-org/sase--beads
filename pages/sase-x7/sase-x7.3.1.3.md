# Bead: sase-x7.3.1.3 — Canonicalize plugin prompts and callers

[Bead Pages](../README.md) / [sase-x7.3.1](sase-x7.3.1.md) / sase-x7.3.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-x7.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-x7.3.md) · **Assignee:** `sase-x7.3.1.3` · **Size:** medium
**Created:** 2026-09-06 09:14:54 EDT · **Closed:** 2026-09-06 10:19:34 EDT
**Plan:** [202609/canonical\_producers.md](https://github.com/sase-org/sase--plans/blob/main/202609/canonical_producers.md)

## Description

plugin-producers: remove available plugin prompt and import facades while preserving later bridge-owned wire and persisted-data readers.

## Notes

[2026-09-06T14:19:02Z · sase-x7.3.1.3] PROPOSED FOLLOW-UP: sase-telegram tests/test_custom_gates.py, tests/test_gate_shell_settlement.py, and tests/test_inbound.py::TestHandleQuestionFlow::test_neutral_question_callback_uses_shared_executor fail to import against the current host: sase.plan_gate.create_plan_approval_gate and sase.user_question_actions.create_user_question_gate no longer exist there (host now exposes build_plan_approval_gate_spec and a differently-named question-gate builder). Reproduced via git stash (pre-existing, unrelated to ChangeSpec/Patch canonicalization, not touched by this phase) -- 3 tests/2 files fail collection; the rest of the suite (554 tests) passes.

[2026-09-06T14:19:34Z · sase-x7.3.1.3] plugin-producers landed: sase-github (workspace_plugin.py, scripts/new_pr_desc_get_context.py) and sase-telegram (scripts/sase_tg_inbound.py) now import sase.ace.patch / sase.integrations.patch_tags unconditionally, dropping the sase.ace.changespec ImportError facades and the dead _list_changespec_xprompt_tags/_format_changespec_skipped_note wrappers; both plugins' pyproject.toml floors bumped sase>=0.11.0/0.1.0 -> sase>=0.17.0 (the release that introduced sase.ace.patch), matching the fleet census (athena/mac/apollo all on 0.17.1) and sase-research-artifacts' existing floor. Removed the redundant wraps_all: true from sase-github's gh.yml xprompt (tags: vcs already implies it per workflow_loader_definition.py). Left all bridge-owned items untouched: sase-github's ws_prepare_mail/ws_submit changespec_name/changespec_parent/changespec_file hookimpl argument names (frozen host hookspec contract) and sase-telegram's agent_format.py changespec_name wire-compat getattr plus its test fixtures (historical agent-status field, owned by a later bridge phase) were not renamed. sase-research-artifacts audited end-to-end: no legacy producer found, verified no-op, no changes made. Verified: sase-github just check (lint+mypy+pytest) 230/230 passed, including 2 new tests added for new_pr_desc_get_context.py's canonical Patch lookup; sase-telegram ruff+mypy clean and pytest 554/554 passed excluding 3 pre-existing unrelated failures (gate-API rename skew, reproduced without my changes via git stash, recorded as PROPOSED FOLLOW-UP), including 3 new tests added for _project_spec_path and _list_patch_xprompt_tags exercising the canonical import paths directly. sase bead epic-symbols sase-x7.3.1.3 reports no leftover --epic-symbol entries.

## Dependencies

- **Depends on:** [sase-x7.3.1.1](sase-x7.3.1.1.md) ✓ · ⧖ 2026-09-06
- **Blocks:** [sase-x7.3.1.4](sase-x7.3.1.4.md) ✓ · ⧖ 2026-09-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-x7.3.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.3.1.3/README.md) | [sase-x7.3.1.3](sase-x7.3.1.3.md) | 0 |
