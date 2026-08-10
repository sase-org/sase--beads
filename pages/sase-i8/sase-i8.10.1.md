# Bead: sase-i8.10.1 — Stop pluggy from silently dropping optional VCS hook arguments

[Bead Pages](../README.md) / [sase-i8.10](sase-i8.10.md) / sase-i8.10.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-i8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i8.land/README.md) · **Assignee:** `sase-i8.10.1` · **Size:** medium
**Created:** 2026-08-10 08:26:10 EDT · **Closed:** 2026-08-10 08:47:04 EDT
**Plan:** [202608/merge\_visibility\_dispatch\_fix.md](https://github.com/sase-org/sase--plans/blob/main/202608/merge_visibility_dispatch_fix.md)

## Description

dispatch: make optional VCS hook parameters reach hook implementations by declaring them positional-or-keyword without defaults in both the hookspec and BareGitPlugin, add a structural guard test over every hookspec family, and re-point the optional-argument tests through VCSPluginManager so they can fail.

## Notes

[2026-08-10T12:45:29Z · sase-i8.10.1] PROPOSED FOLLOW-UP: Committed plan validation fails on 202608/new_task_recent_task_sweep.md — required tale field size is missing, so just check stops at validate_committed_plans.

[2026-08-10T12:47:04Z · sase-i8.10.1] Implemented VCS hookspec/BareGitPlugin positional no-default signatures and dispatch regression tests. Verified focused pytest tests/test_pluggy_hookspec_forwarding.py tests/test_vcs_provider_vcs_log.py tests/test_vcs_provider_contract.py::test_merge_visibility_keyword_is_optional_for_hookimpls: 138 passed; .venv/bin/sase vcs log -m only --limit 5 --format json returned five real merge commits (73f0ba57, 6aeb6e64, 6830cfb9, 2774571, d4451532b). just check passed through lint/SASE validation but failed at committed-plan validator on pre-existing 202608/new_task_recent_task_sweep.md missing required size; proposed follow-up recorded on this bead.

[2026-08-10T12:48:34Z · sase-i8.10.1] Verified focused pytest coverage for pluggy forwarding and VCS log behavior, runtime venv CLI merge-only log output, and just check through the unrelated committed-plan validation failure.

## Dependencies

- **Blocks:** [sase-i8.10.3](sase-i8.10.3.md) ◐ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i8.10.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i8.10.1/README.md) | [sase-i8.10.1](sase-i8.10.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6d131aa`](https://github.com/sase-org/sase/commit/6d131aa7b4df28d10211d4a6ee6df84ac173e9fc) | fix(vcs): forward optional VCS hook arguments | [sase-i8.10.1](sase-i8.10.1.md) | 2026-08-10 08:49:32 EDT |
