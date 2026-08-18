# Bead: sase-q0.5.2 — Refuse gh workflow steps that would prepare an occupied checkout

[Bead Pages](../README.md) / [sase-q0.5](sase-q0.5.md) / sase-q0.5.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-q0.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-q0.land.md) · **Assignee:** `sase-q0.5.2` · **Size:** medium
**Created:** 2026-08-18 17:40:17 EDT · **Closed:** 2026-08-18 18:22:51 EDT
**Plan:** [202608/gh\_plugin\_workspace\_exclusivity.md](https://github.com/sase-org/sase--plans/blob/main/202608/gh_plugin_workspace_exclusivity.md)

## Description

gh_guard: write the per-checkout occupant record when gh__setup takes a workspace, clear it on release, and require the occupancy decision before gh__prepare stashes, gh__checkout checks out, or the GitHub submit path checks out, so a conflicting occupant fails the run instead of losing another agent's work.

## Notes

[2026-08-18T22:22:51Z · sase-q0.5.2] gh_guard implemented in sase-github: gh_setup.py writes .sase/occupant.json for real numbered workspaces (workspace_num > 1, matching run_agent_phases.py's convention) and calls ensure_workspace_not_occupied before handing the checkout to prepare/checkout, on both the claimed and pre_allocated branches; ws_submit_changespec guards the submit checkout before provider.checkout(); gh.yml's release step clears the occupant record via clear_occupant_record(setup.workspace_dir) alongside the existing gh-release caller tag. Verified: rebuilt sase_core_rs locally (maturin develop --release against linked sase-core, since the installed wheel predated decide_workspace_occupant_conflict); full sase-github suite (219 tests, including 20 in test_gh_workspace_claims.py covering occupant-record writes, refusal on a live rival occupant, proceeding when the occupant is self or a dead pid, and the submit-path refusal) all pass; ruff check and mypy clean; no epic-symbol leftovers (sase bead epic-symbols reported none); sase doctor --check workspace.occupancy_conflicts OK.

## Dependencies

- **Depends on:** [sase-q0.5.1](sase-q0.5.1.md) ✓ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-q0.5.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-q0.5.2/README.md) | [sase-q0.5.2](sase-q0.5.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-github | [`sase-github@51347d4`](https://github.com/sase-org/sase-github/commit/51347d4f0a256c80785e7e2633fa589259073481) | feat(workspace): guard gh workflow steps against occupied checkouts | [sase-q0.5.2](sase-q0.5.2.md) | 2026-08-18 18:23:27 EDT |
