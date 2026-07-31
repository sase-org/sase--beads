# Bead: sase-bg.6 — Remove bd/next, rewire capture, add bd/work\_task

[Bead Pages](../README.md) / [sase-bg](README.md) / sase-bg.6

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-bg.6` · **Size:** medium
**Created:** 2026-07-30 22:55:41 UTC · **Closed:** 2026-07-30 23:10:21 UTC
**Plan:** [202607/task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202607/task_beads.md)

## Description

xprompts: delete the bd/next xprompt and its doc/test references, redirect bd/work_phase_bead to PROPOSED FOLLOW-UP notes, teach bd/land_epic to file ready task beads, and add the bd/work_task xprompt with its tag, resolver, and tests.

## Notes

[2026-07-30T23:09:52Z · sase-bg.6] PROPOSED FOLLOW-UP: Remove stale sase-bf Symvision whitelist entries and clean up coerce_var_value/decode_var_value — just check reports sase-bf is already closed; this is unrelated to the xprompt phase.

[2026-07-30T23:10:21Z · sase-bg.6] Implemented bd/next removal; phase and land follow-up capture; bd/work_task plus work_task_bead resolver/tag; docs and tests. Verified focused xprompt tests: 39 passed; full just test: 24,578 passed and 7 skipped; formatting, keep-sorted, Ruff, mypy, pyscripts, changelog, toobig, and committed-plan validation passed. Full just check reaches unrelated stale sase-bf Symvision whitelist entries; recorded that cleanup as a PROPOSED FOLLOW-UP note. sase validate also reports pre-existing provider-skill drift and unrelated plan-link errors.

[2026-07-30T23:10:58Z · sase-bg.6] Verified focused xprompt tests (39 passed), full test suite (24,578 passed, 7 skipped), and formatting/static checks; remaining Symvision and sase validate findings are unrelated pre-existing drift.

## Dependencies

- **Blocks:** [sase-bg.7](sase-bg.7.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-bg.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-bg.6/README.md) | [sase-bg.6](sase-bg.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`cf4088f`](https://github.com/sase-org/sase/commit/cf4088f751c30827fb016c17d3697bbc02fb6cdc) | feat!: replace bd/next with task bead workflow | [sase-bg.6](sase-bg.6.md) | 2026-07-30 23:11:54 |
