# Bead: sase-m9.2.1.3 — Named proc-shell addressing and CLI

[Bead Pages](../README.md) / [sase-m9.2.1](sase-m9.2.1.md) / sase-m9.2.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m9.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.2.md) · **Assignee:** `sase-m9.2.1.3` · **Size:** small
**Created:** 2026-08-15 06:14:55 EDT · **Closed:** 2026-08-15 08:10:41 EDT
**Plan:** [202608/unified\_proc\_shell\_platform\_1.md](https://github.com/sase-org/sase--plans/blob/main/202608/unified_proc_shell_platform_1.md)

## Description

named-proc-shell-cli: add -N/--shell to proc run and list, resolve show/kill references by exact fully qualified shell name before exact id and unique id prefix, and derive bare names beneath the calling sase agent. Validate names against slash, proc-id ambiguity, invalid agent components, and malformed qualification; map each shell name to its distinct namespaced concurrency key without conflating the fields; scope active uniqueness by project and allow reuse only after settlement. Update filtering, JSON and rich renderers, help, completions, and tests using “named proc shell” language while preserving historical name visibility and avoiding a top-level sase shell command.

## Notes

[2026-08-15T12:09:54Z · sase-m9.2.1.3] PROPOSED FOLLOW-UP: just check escalates via core-identity-changed / blocked_unpublished because the declared sase-core-rs floor is 0.27.2 while reserve_proc, claim_proc_supervisor, request_proc_stop, begin_proc_settlement, and finish_proc first appear in published 0.27.3 (6d7000a). Land should raise the Python floor after the core release is the installed default.

[2026-08-15T12:10:07Z · sase-m9.2.1.3] PROPOSED FOLLOW-UP: 116 unrelated CLI/TUI tests fail on this tree because captured stdout now includes Rich ANSI bold around numbers and brackets (smallest repro: tests/test_output.py::test_escape_markup_in_log_fn). Not caused by named proc-shell CLI; just check escalated to the full suite via core-identity-changed.

[2026-08-15T12:10:21Z · sase-m9.2.1.3] PROPOSED FOLLOW-UP: tests/test_procs_service.py::test_settlement_resumes_after_an_injected_crash timed out once in the escalated full suite (TimeoutError waiting for proc) but passed in isolation (1.58s). Looks like full-suite load flake from the supervisor phase, not named-shell addressing.

[2026-08-15T12:10:41Z · sase-m9.2.1.3] Added -N/--shell to proc run and list, resolve show/kill by exact FQ named proc shell then exact id then unique prefix, and derive bare names beneath the calling sase agent. Validated slash, proc-id ambiguity, invalid agent components, and malformed qualification; mapped each name to a distinct namespaced concurrency key without writing it into concurrency_keys; scoped active uniqueness by project and reused only after settlement. Updated filtering, JSON/rich renderers, help, completions, and tests using named proc shell language, kept historical names visible, and did not add a top-level sase shell command. Verified with just install, focused proc/CLI suites (all new tests passed), just check lint (fmt/ruff/mypy/symvision passed), and the escalated full pytest lane (30181 passed; 116 unrelated Rich-ANSI CLI failures plus one isolated-passing supervisor flake recorded as follow-up).

[2026-08-15T12:11:35Z · sase-m9.2.1.3] Added -N/--shell to proc run and list, resolve show/kill by exact FQ named proc shell then exact id then unique prefix, and derive bare names beneath the calling sase agent. Validated slash, proc-id ambiguity, invalid agent components, and malformed qualification; mapped each name to a distinct namespaced concurrency key without writing it into concurrency_keys; scoped active uniqueness by project and reused only after settlement. Updated filtering, JSON/rich renderers, help, completions, and tests using named proc shell language, kept historical names visible, and did not add a top-level sase shell command. Verified with just install, focused proc/CLI suites (all new tests passed), just check lint (fmt/ruff/mypy/symvision passed), and the escalated full pytest lane (30181 passed; 116 unrelated Rich-ANSI CLI failures plus one isolated-passing supervisor flake recorded as follow-up).

## Dependencies

- **Depends on:** [sase-m9.2.1.2](sase-m9.2.1.2.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-m9.2.1.4](sase-m9.2.1.4.md) ✓ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m9.2.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m9.2.1.3/README.md) | [sase-m9.2.1.3](sase-m9.2.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1e242aa`](https://github.com/sase-org/sase/commit/1e242aa8b9e8c6c4bc4213fa84526378ec3512a2) | feat(procs): address named proc shells from the CLI | [sase-m9.2.1.3](sase-m9.2.1.3.md) | 2026-08-15 08:12:12 EDT |
