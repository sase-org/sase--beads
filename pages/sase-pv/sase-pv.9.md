# Bead: sase-pv.9 — Memory notes, generated instructions, and documentation

[Bead Pages](../README.md) / [sase-pv](README.md) / sase-pv.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.06a](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.06a.md) · **Assignee:** `sase-pv.9` · **Size:** medium
**Created:** 2026-08-18 11:26:07 EDT · **Closed:** 2026-08-18 20:57:05 EDT
**Plan:** [202608/flag\_task\_type.md](https://github.com/sase-org/sase--plans/blob/main/202608/flag_task_type.md)

## Description

docs: rewrite the two feature-flag memory notes, regenerate the instruction files and catalog snapshot, and update every doc page that still describes a flag bead type.

## Notes

[2026-08-19T00:56:06Z · sase-pv.9] PROPOSED FOLLOW-UP: flake in tests/ace/tui/modals/test_project_inventory_subtabs.py::test_cross_navigation_and_escape_surface_disabled_workspaces — escalated just check failed once with assert project_filter == "alpha" got "beta"; serial rerun on the same tree passed in 0.97s. Unrelated to flag docs; another agent was already looping this test.

[2026-08-19T00:57:05Z · sase-pv.9] Rewrote sase/memory/sase_flags.md and feature_flags.md around two kinds, the Off-branch removal rule, the seven fields, sase flag new, -b/--remove-by, and FlagTriage D2 answers. Ran sase memory init --no-commit; AGENTS.md/provider shims/memory README regenerated; task_types.md still omits flag (agent_creatable: false). Updated docs/beads.md, notifications.md, axe.md, cli.md, configuration.md, sase.yml glossary, and the bead_task_triage chop description. Verified plugins/completion/commit_workflows/xprompt incidental flag prose. Confirmed sase flag list, sase flag show prettier_enabled, sase bead show sase-qe (sase-nw reminted in sase-pv.7), and sase bead task-type show flag. just check escalated to the full suite (33832 passed, 12 skipped); one unrelated flake recorded as PROPOSED FOLLOW-UP. epic-symbols: none.

## Dependencies

- **Depends on:** [sase-pv.8](sase-pv.8.md) ✓ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pv.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pv.9/README.md) | [sase-pv.9](sase-pv.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`281f3c1`](https://github.com/sase-org/sase/commit/281f3c1976767bf33b68dbd2fddf9e3dc44fef6b) | docs(flags): treat flag beads as task(flag), not a fourth issue type | [sase-pv.9](sase-pv.9.md) | 2026-08-18 20:59:32 EDT |
