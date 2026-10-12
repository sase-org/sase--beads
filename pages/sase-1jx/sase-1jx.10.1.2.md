# Bead: sase-1jx.10.1.2 — Shared Projects init controller

[Bead Pages](../README.md) / [sase-1jx.10.1](sase-1jx.10.1.md) / sase-1jx.10.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jx.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.10.md) · **Assignee:** `sase-1jx.10.1.2` · **Size:** medium
**Created:** 2026-10-12 04:39:47 EDT · **Closed:** 2026-10-12 04:59:07 EDT
**Plan:** [202610/new\_project\_add\_existing.md](https://github.com/sase-org/sase--plans/blob/main/202610/new_project_add_existing.md)

## Description

init-flow: extract the Projects init check, preview, apply, and terminal flow into a controller the pane and the wizard share.

## Notes

[2026-10-12T08:58:54Z · sase-1jx.10.1.2] PROPOSED FOLLOW-UP: stale symvision epic-symbol rows block just check — sase-1jm.3.1(archive_read_only_context) and sase-1jx.7.1(journal_path, journal_lock_path, journal_lock) name closed beads; identical on clean base (same lines in HEAD Justfile), fails just _lint-symvision for every agent

[2026-10-12T08:59:07Z · sase-1jx.10.1.2] init-flow extracted: new projects_pane_init_flow.py owns check/preview/apply/terminal sequencing behind ProjectsInitHost; pane mixin is a thin adapter; run_project_init(host, InitScope.for_projects([key])) exported for apply-ready (allowlisted to sase-1jx.10.1.4). Verified: just fmt clean; ruff+ mypy clean on touched files; 48 init-flow/modal/inventory tests green incl. producer inventory with new paths; adjacent pane/gear-lanes/keymaps suites green (38); fake-host smoke of run_project_init check->modal->apply+cancel preserves argv/dedup keys/scopes/status. just _lint-symvision shows only pre-existing unrelated stales (recorded as PROPOSED FOLLOW-UP).

## Dependencies

- **Blocks:** [sase-1jx.10.1.4](sase-1jx.10.1.4.md) ◐ · ⧖ 2026-10-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.10.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.10.1.2/README.md) | [sase-1jx.10.1.2](sase-1jx.10.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`393d0a4`](https://github.com/sase-org/sase/commit/393d0a4a5a32ea0b4f59a8b0db119723ac2a0374) | feat(ace-tui): extract shared projects init controller into init flow module | [sase-1jx.10.1.2](sase-1jx.10.1.2.md) | 2026-10-12 05:13:02 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jx.10.1.2][1] | Need full phase scope notes history | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.10.1.2/README.md

<!-- sase:referenced-by:end -->
