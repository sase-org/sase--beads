# Bead: sase-17x.3 — Value-kind coverage and ratchet

[Bead Pages](../README.md) / [sase-17x](README.md) / sase-17x.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qs](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qs.md) · **Assignee:** `sase-17x.3` · **Size:** medium
**Created:** 2026-09-24 11:29:21 EDT · **Closed:** 2026-09-24 12:35:01 EDT
**Plan:** [202609/command\_line\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_panel.md)

## Description

kind-coverage: add GATE, TOOL_RUN and TASK_TYPE value kinds with providers, annotate the unkinded entity slots, and add a coverage ratchet test. The test requires every non-hidden value slot to be kinded, to have choices, or to carry a free-form value_hint.

## Notes

[2026-09-24T16:34:43Z · sase-17x.3] PROPOSED FOLLOW-UP: Full just check could not run end-to-end in-turn (Rust extension rebuild exceeds the synchronous limit); component gates verified instead — land agent should run sase tool run check

[2026-09-24T16:35:01Z · sase-17x.3] Kind-coverage done: GATE/TOOL_RUN/TASK_TYPE kinds with read-only prompt-free providers, entity+path kind tables and a declarative value_hint table cover all 569 previously-unkinded slots (verified 0 uncovered); ratchet test tests/completion/test_kind_coverage.py added; cli_spec snapshot regenerated. Verified: 121 completion tests pass, ruff format+check clean, mypy clean (4920 files).

## Dependencies

- **Blocks:** [sase-17x.12](sase-17x.12.md) ◐ · ⧖ 2026-09-24
- **Depends on:** [sase-17x.2](sase-17x.2.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.3/README.md) | [sase-17x.3](sase-17x.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`79a16ca`](https://github.com/sase-org/sase/commit/79a16ca7712fca793714e92d9c884aca86da1fc5) | feat(completion): add GATE, TOOL\_RUN, TASK\_TYPE kinds with entity candidates and kind-coverage ratchet | [sase-17x.3](sase-17x.3.md) | 2026-09-24 12:37:08 EDT |
