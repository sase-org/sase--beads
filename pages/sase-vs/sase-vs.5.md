# Bead: sase-vs.5 — \`sase plan approve --wait\`

[Bead Pages](../README.md) / [sase-vs](README.md) / sase-vs.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ga](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ga.md) · **Assignee:** `sase-vs.5` · **Size:** small
**Created:** 2026-08-30 07:22:01 EDT · **Closed:** 2026-08-30 09:37:42 EDT
**Plan:** [202608/approval\_wait\_argument.md](https://github.com/sase-org/sase--plans/blob/main/202608/approval_wait_argument.md)

## Description

plan_approve_cli: add a `-w/--wait` option to `sase plan approve` that validates the spec before anything is mutated and forwards it to the approval executor.

## Notes

[2026-08-30T13:37:42Z · sase-vs.5] Implemented sase plan approve -w/--wait parsing, early validation, executor forwarding, docs, and tests. Verified with .venv/bin/python -m pytest tests/main/test_parser_plan.py tests/test_plan_approve_cli.py -q, .venv/bin/python -m ruff check targeted files, just fmt, just check, and sase bead epic-symbols sase-vs.5 (no leftovers).

## Dependencies

- **Depends on:** [sase-vs.4](sase-vs.4.md) ✓ · ⧖ 2026-08-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-vs.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vs.5/README.md) | [sase-vs.5](sase-vs.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c507cea`](https://github.com/sase-org/sase/commit/c507ceab9b2334268aeefda9a6272c838e33d677) | feat(plan): add approval wait CLI | [sase-vs.5](sase-vs.5.md) | 2026-08-30 09:38:51 EDT |
