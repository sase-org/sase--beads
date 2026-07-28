# Bead: sase-ac.6 — Finish canonical xprompt project identity and land sase-ac

[Bead Pages](../README.md) / [sase-ac](README.md) / sase-ac.6

**Status:** ✓ closed · **Resolution:** done · **Type:** plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ac.6.land`
**Created:** 2026-07-28 13:13:40 UTC · **Closed:** 2026-07-28 15:20:20 UTC
**Plan:** [202607/xprompt\_identity\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202607/xprompt_identity_landing.md)

## Description

Every consumer of a project xprompt namespace uses the canonical user-facing project name, no surface advertises or resolves the ProjectSpec directory-key spelling, and epic sase-ac is closed with its plan file marked done.

## Notes

[2026-07-28T15:20:07Z · sase-ac.6.land] Landing audit for sase-ac.6. VERIFIED all four fix phases against source, not just bead notes: get_all_project_local_prompts() and resolve_source_to_file_path()/_source_definition_path() now go through known_project_namespaces()+canonical_xprompt_project() (6.1); _prompt_bar_requests.py canonicalizes the VCS-tag project before the namespace lookup (6.2); get_all_workflows()/_load_workflows_from_project_workspace() canonicalize and fall back to the registry with current-checkout skip (6.3); public invalidate_xprompt_project_identity() is wired through invalidate_project_display_snapshot() plus the alias, lifecycle, project-file, bare-repo, and workspace-dir mutation paths (6.4). Re-ran the outside-checkout probe from /tmp: get_all_project_local_prompts() yields only sase/{docs,gact,reads,remember,sync} with zero gh_* namespaces, canonical_xprompt_project('gh_sase-org__sase')=='sase', and project_local_config: resolves to the project sase.yml from BOTH the canonical and the directory-key spelling.

GAP FOUND AND FIXED (bead note not fully addressed by 6.1): the plan's browser_identity Tests section required confirming the load_browser_items() dict merge collapses to one row per file 'with a test rather than assuming it'. No such test existed. Added tests/test_project_local_xprompts.py::TestGetAllProjectLocalPrompts::test_browser_items_collapse_to_one_canonical_project_local_row and verified it fails (2 rows: widgets/docs plus gh_acme__widgets/docs) when get_all_project_local_prompts() is reverted to get_known_project_workspaces().

INTEGRATION: three sibling-phase test modules reintroduced the exact private-cache reach-in that 6.4 existed to eliminate (project_identity._identity_registry.cache_clear() / _canonical_xprompt_project.cache_clear()) in tests/test_workflow_loader_project.py, tests/test_project_local_xprompts.py, and tests/ace/tui/test_prompt_bar_xprompt_selector_requests.py. Swapped all of them onto the public invalidate_xprompt_project_identity(); no private reach-ins remain. Reviewed every non-epic commit landed since the epic's first commit (a0a2e4007): axe/lumberjack, sdd hosted_links + associations + plan_header_block, agents-sync, ace folding/wait-lanes, and the sase-core-rs 0.12.2 bump. None touch the xprompt namespace surface. Considered and deliberately rejected folding project_identity._identity_registry onto ProjectRefDisplaySnapshot (landed 09:13 in 4fb598060): load_project_alias_map() builds from include_home=False non-system records while ProjectRefDisplaySnapshot.from_records() builds from include_home=True, so it is not a behavior-preserving swap.

VERIFICATION: just install; just symvision clean (no sase-ac whitelist entries remain in the Justfile, so the close expires nothing); just fmt/lint all green; just test 23,051 passed with two known parallel-load flakes (test_suite_gate_integration, test_task_mirror) that both pass in isolation. just check remains blocked ONLY by a pre-existing, unrelated SDD failure that reproduces on a stashed clean tree: 202607/plan_header_provenance.md (epic sase-ag). Root cause isolated: sase.sdd.plan_header_block.parse_plan_header_block does not skip fenced code blocks, so that plan's own ```markdown grammar example is parsed as part of its header block; stripping the fence makes the same document parse canonical. That is sase-ag.1's contract to fix, not sase-ac's.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ac.6.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ac.6.land/README.md) | [sase-ac.6](sase-ac.6.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`01549ff`](https://github.com/sase-org/sase/commit/01549ff628d0fc96995e7cc11b04a44d2e7a6b52) | test(xprompt): cover browser row merge and drop cache reach-ins (sase-ac.6) | [sase-ac.6](sase-ac.6.md) | 2026-07-28 15:22:06 |
