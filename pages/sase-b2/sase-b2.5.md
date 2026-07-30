# Bead: sase-b2.5 — Prompt expansion and \`sase artifact\` support

[Bead Pages](../README.md) / [sase-b2](README.md) / sase-b2.5

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b2.5` · **Size:** small
**Created:** 2026-07-30 01:33:33 UTC · **Closed:** 2026-07-30 02:36:12 UTC
**Plan:** [202607/bead\_and\_agent\_artifact\_refs.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_and_agent_artifact_refs.md)

## Description

py_cli: expand `@bead:`/`@agent:` to their page paths at launch, make `sase artifact show/path/open` accept the new kinds, and add publication-aware hints to unresolved-reference errors.

## Notes

[2026-07-30T02:36:12Z · sase-b2.5] Implemented bead/agent prompt expansion and artifact CLI filesystem support; verified focused tests with .venv/bin/python -m pytest tests/test_artifact_ref_preprocessing.py tests/main/test_artifact_cli_references.py -q (37 passed). Ran just check: code format/lint passed through symvision/toobig, then SASE validation failed on existing missing plan prompt links in 202607 plans.

[2026-07-30T02:37:22Z · sase-b2.5] Verified focused tests passed (37 passed) and just check progressed through format/lint/mypy before failing on pre-existing 202607 plan-link validation errors.

## Dependencies

- **Depends on:** [sase-b2.4](sase-b2.4.md) ✓
- **Blocks:** [sase-b2.8](sase-b2.8.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b2.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b2.5/README.md) | [sase-b2.5](sase-b2.5.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`278e169`](https://github.com/sase-org/sase/commit/278e16952b95de02025a6f21f438db530362bc7d) | feat: support entity artifact references in prompt paths | [sase-b2.5](sase-b2.5.md) | 2026-07-30 02:38:21 |
