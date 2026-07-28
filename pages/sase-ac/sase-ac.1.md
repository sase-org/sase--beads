# Bead: sase-ac.1 — Canonical project-identity resolver

[Bead Pages](../README.md) / [sase-ac](README.md) / sase-ac.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ac.1` · **Size:** small
**Created:** 2026-07-28 11:41:16 UTC · **Closed:** 2026-07-28 12:04:44 UTC
**Plan:** [202607/xprompt\_project\_identity.md](https://github.com/sase-org/sase--plans/blob/main/202607/xprompt_project_identity.md)

## Description

identity: add a single Python helper that normalizes any project spelling (directory key, PROJECT_NAME, alias) to the canonical user-facing namespace name, plus its unit tests.

## Notes

[2026-07-28T12:04:07Z · sase-ac.1] Implemented the Python xprompt project identity helper with canonical_xprompt_project() and known_project_namespaces(), added focused unit tests for directory key / PROJECT_NAME / alias / unknown / empty / no-PROJECT_NAME / failure behavior, and added temporary Symvision epic-symbols for the later sase-ac consumers. Verified with .venv/bin/pytest tests/test_xprompt_project_identity.py, just _lint-symvision, and just check.

## Dependencies

- **Blocks:** [sase-ac.2](sase-ac.2.md) ✓
- **Blocks:** [sase-ac.3](sase-ac.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ac.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ac.1/README.md) | [sase-ac.1](sase-ac.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`370f260`](https://github.com/sase-org/sase/commit/370f2607f684d68272b2416a313133c8d7058e59) | feat(xprompt): add canonical project identity helpers (sase-ac.1) | [sase-ac.1](sase-ac.1.md) | 2026-07-28 12:07:40 |
