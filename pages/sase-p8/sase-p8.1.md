# Bead: sase-p8.1 — Shared in-process family-successor engine

[Bead Pages](../README.md) / [sase-p8](README.md) / sase-p8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05f](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05f.md) · **Assignee:** `sase-p8.1` · **Size:** medium
**Created:** 2026-08-17 19:00:59 EDT · **Closed:** 2026-08-17 20:05:14 EDT
**Plan:** [202608/agent\_pipe.md](https://github.com/sase-org/sase--plans/blob/main/202608/agent_pipe.md)

## Description

successor: extract the runner's repeated become-the-next-family-member dance into one engine and migrate the plan-approval coder hand-off and the questions follow-up onto it, behavior unchanged.

## Notes

[2026-08-18T00:04:51Z · sase-p8.1] PROPOSED FOLLOW-UP: just check fails on stale --epic-symbol entries for closed bead sase-p1.2 (GlossaryConflictError, GlossaryMutationError, GlossaryMutationOutcome, GlossaryValidationError, add_glossary_term, delete_glossary_term). Re-key those Justfile lines to still-open sase-p1 or sase-p1.6, or land a non-test consumer so the whitelist can drop.

[2026-08-18T00:05:14Z · sase-p8.1] Extracted continue_as_successor into src/sase/axe/run_agent_successor.py and migrated plan-accept coder hand-off plus questions follow-up onto it. Existing plan-accept and questions suites passed unmodified; new tests/axe/test_run_agent_successor.py pins explicit/allocated/unnamed suffix, one-shot step-2 promotion, model-meta write, and prompt-artifact recording. just test-scoped: 751 passed. ruff/mypy/fmt clean. sase bead epic-symbols sase-p8.1: no leftovers. just check's symvision still fails on pre-existing stale sase-p1.2 --epic-symbol entries (recorded as PROPOSED FOLLOW-UP).

[2026-08-18T00:06:22Z · sase-p8.1] Extracted continue_as_successor into src/sase/axe/run_agent_successor.py and migrated plan-accept coder hand-off plus questions follow-up onto it. Existing plan-accept and questions suites passed unmodified; new tests/axe/test_run_agent_successor.py pins explicit/allocated/unnamed suffix, one-shot step-2 promotion, model-meta write, and prompt-artifact recording. just test-scoped: 751 passed. ruff/mypy/fmt clean. sase bead epic-symbols sase-p8.1: no leftovers.

## Dependencies

- **Blocks:** [sase-p8.4](sase-p8.4.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p8.1/README.md) | [sase-p8.1](sase-p8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0b8bac8`](https://github.com/sase-org/sase/commit/0b8bac8376a5837f9d12c594be38367a108dc690) | refactor(axe): extract shared in-process family-successor engine | [sase-p8.1](sase-p8.1.md) | 2026-08-17 20:11:10 EDT |
