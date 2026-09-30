# Bead: sase-1d8.2 — Record each submission's canonical text once

[Bead Pages](../README.md) / [sase-1d8](README.md) / sase-1d8.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ud](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ud.md) · **Assignee:** `sase-1d8.2` · **Size:** medium
**Created:** 2026-09-30 07:44:49 EDT · **Closed:** 2026-09-30 10:02:40 EDT
**Plan:** [202609/prompt\_history\_human\_only.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompt_history_human_only.md)

## Description

canonical-text: add an ingress-owned history_text to the launcher so single-slot swarms, %r:N, force-reuse and launch_units launches record the submitted text exactly once; teach sase run the history_text and history_origin payload keys.

## Notes

[2026-09-30T14:02:06Z · sase-1d8.2] PROPOSED FOLLOW-UP: symvision fails identically on the clean base tree (HEAD ad7f3a19a3): private `_run` flagged in 29 untouched src/sase/scripts/* files; reproduced via a read-only worktree at HEAD with output identical apart from paths

[2026-09-30T14:02:40Z · sase-1d8.2] canonical-text done: ingress-owned history_text on launcher (single-slot swarm records invocation, %r:N parent-once with generated slots, launch_units+history_text one row, force-reuse pre-rewrite via sase run) plus history_text/history_origin payload keys (downgrade-only). Verified: 7 new tests/history/test_prompt_canonical_text.py pass, 7 new sase-run ingress tests pass, 50 tests across origin/ingress/launcher-origin-AST/project-tag suites pass, 510 tests across history+launch-guard suites pass; ruff+format+mypy clean. Full just check stalled in setup rust rebuild (shared build lock, run 935aa396395c8652e3be192b09b15782); symvision scripts/_run failure reproduces identically on clean HEAD worktree, recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-1d8.1](sase-1d8.1.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1d8.3](sase-1d8.3.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d8.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d8.2/README.md) | [sase-1d8.2](sase-1d8.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ce0f618`](https://github.com/sase-org/sase/commit/ce0f61846ca3489bec69d4d40fe4b65a7ea0e048) | feat(history): record each submission's canonical text once | [sase-1d8.2](sase-1d8.2.md) | 2026-09-30 10:04:56 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1d8.2][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d8.2/README.md

<!-- sase:referenced-by:end -->
