# Bead: sase-12w.2 — Detached sudo answer path and finalize proc

[Bead Pages](../README.md) / [sase-12w](README.md) / sase-12w.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ms](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ms.md) · **Assignee:** `sase-12w.2` · **Size:** large
**Created:** 2026-09-18 08:50:39 EDT · **Closed:** 2026-09-18 11:33:34 EDT
**Plan:** [202609/sudo\_proc\_execution.md](https://github.com/sase-org/sase--plans/blob/main/202609/sudo_proc_execution.md)

## Description

cli: add an opt-in --detach path to `sase sudo answer` that runs the runner in auth-then-spawn mode, records a durable in-flight execution record, and submits a supervised finalize proc; add the internal `sase sudo finalize` subcommand that waits for the executor, validates the ledger, answers the gate, and settles the gate shell.

## Notes

[2026-09-18T15:33:34Z · sase-12w.2] Detached sudo answer and hidden finalize proc landed. Focused tests: tests/test_sudo_parser.py, tests/test_sudo_core.py, tests/test_sudo_runner.py, tests/test_sudo_execution.py, tests/test_sudo_detach.py, tests/test_sudo_gate.py, tests/test_sudo_acceptance.py, tests/completion/test_build.py, tests/test_agent_artifact_directory_operation_audit.py — 95 passed. just test-scoped: 7926 passed, 3 skipped. just check: failed only on pre-existing _lint-flags (closed flag bead sase-11u still has surviving agent_holds definition); fmt, ruff, mypy, pyscripts, waits, changelog, patch/stitch, symvision, toobig, and validate were green. sase bead epic-symbols sase-12w.2: no leftover --epic-symbol entries.

## Dependencies

- **Depends on:** [sase-12w.1](sase-12w.1.md) ✓ · ⧖ 2026-09-18
- **Blocks:** [sase-12w.3](sase-12w.3.md) ◐ · ⧖ 2026-09-18
- **Blocks:** [sase-12w.4](sase-12w.4.md) ◐ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-12w.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-12w.2.md) | [sase-12w.2](sase-12w.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`af8b7ec`](https://github.com/sase-org/sase/commit/af8b7ec14009c34ccac57c7879ec52329d53f4fa) | feat(sudo): add local detached answer path and finalize proc | [sase-12w.2](sase-12w.2.md) | 2026-09-18 11:35:39 EDT |
