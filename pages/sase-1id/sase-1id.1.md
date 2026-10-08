# Bead: sase-1id.1 — Fail-closed %auto grammar in sase-core and Python

[Bead Pages](../README.md) / [sase-1id](README.md) / sase-1id.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0yg](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0yg.md) · **Assignee:** `sase-1id.1` · **Size:** medium
**Created:** 2026-10-08 13:39:30 EDT
**Plan:** [202610/auto\_p0\_safety\_tales.md](https://github.com/sase-org/sase--plans/blob/main/202610/auto_p0_safety_tales.md)

## Description

grammar: add one sase-core classifier for %auto spellings and use it in the Rust typed launch extractor, editor metadata, editor/LSP diagnostics, and the Python extractor, so named arguments, parenthesized forms, extra positionals, and unknown colon values fail at launch, and :manual/:off mean Manual. Commit sase-core and sase in the same turn so the host moves the core pin. Close task bead sase-1hg when done.

## Notes

[2026-10-08T18:30:05Z · sase-1id.1] PROPOSED FOLLOW-UP: tests/test_plan_gates_execution.py::test_shared_host_executor_handles_feedback_rejection_and_races fails identically on the clean base tree (verified via git stash of src changes); option_results mismatch on feedback flow with no %auto involved, no duplicate task bead found

## Dependencies

- **Blocks:** [sase-1id.5](sase-1id.5.md) ◐ · ⧖ 2026-10-08
- **Blocks:** [sase-1id.6](sase-1id.6.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1id.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1id.1.md) | [sase-1id.1](sase-1id.1.md) | 0 |
