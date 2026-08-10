# Bead: sase-i8.10 — Make merge visibility work through the real provider dispatch path

[Bead Pages](../README.md) / [sase-i8](README.md) / sase-i8.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-i8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i8.land/README.md) · **Assignee:** `sase-i8.10.land`
**Created:** 2026-08-10 08:25:56 EDT · **Closed:** 2026-08-10 10:46:34 EDT
**Plan:** [202608/merge\_visibility\_dispatch\_fix.md](https://github.com/sase-org/sase--plans/blob/main/202608/merge_visibility_dispatch_fix.md)

## Description

`sase vcs log --merges hide|show|only` and the ACE Commits merge cycle actually re-slice history at runtime, the partition law holds against a real repository, the epic's own test-isolation flake is gone, and epic sase-i8 lands with recorded acceptance evidence.

## Notes

[2026-08-10T14:46:34Z · sase-i8.10.land] Landing verification on integrated master 1417de7db: reviewed the epic, all four child beads, every child and epic note/history entry, the complete linked plan, source, and both epic commits 6d131aa7b and e9e414e2f. Current source retains positional no-default hookspec and BareGitPlugin parameters while VCSPluginManager keeps caller defaults and passes every value explicitly; structural forwarding coverage spans VCS, workspace, and LLM hook families; provider-path tests cover author/time/revision/timeout/ref-name filters, merge hide/show/only, the partition law, legacy hook omission, and isolated per-test bare remotes. Focused dispatch/provider/contract suite passed 138 tests. Real integrated history produced hide=11999 with 0 merges, only=101 with 101 merges, show=12100 with 101 merges, so hide plus only equals show and the sets are partitioned; six sampled only-mode commits each had two parents. The core schema probe passed. Post-start non-epic commits were reviewed: none overlaps the VCS dispatch or remote fixture implementation; 90912ad7d already refreshed the contract manifest, 884951057 addressed the Tasks-pane race, and 1417de7db updated the cost-mode contract. Current focused resolved-item suite passed 5 tests, and just check passed every lint/validation gate plus the scoped test lane. Follow-up outcomes via sase_new_task: created ready large task sase-iw for normal-gate typing of extensionless tools after reproducing three union-attr errors; duplicate-corroborated the launcher, xprompt-highlight, and VCS-tag xdist reports from proposing beads sase-i8.3, sase-i8.4, and sase-i8.6 on ready umbrella sase-ct; duplicate-corroborated the known_mtime report from proposing bead sase-i8.7 on exact task sase-ii. Routed vcs_repo_stats merge-count drift and incoming_commits merge-unaware counting from proposing bead sase-i8.10.4 as two DISCOVERED ISSUE notes on causally related active parent epic sase-i8, so no standalone tasks were created. Declined new tasks for the duplicated xdist and Tasks-pane proposals because exact trackers exist; for the tale-size proposal from sase-i8.10.1 and .2 because new_task_recent_task_sweep.md now has size medium and committed-plan validation passes; and for cost-mode drift from sase-i8.10.3 and .4 because 1417de7db renamed the contract to require both recorders and the current test passes. Also confirmed the 0.23.0 core floor, markdown formatting, generated-memory check, and contract manifest are clean. No unresolved issue caused by sase-i8.10 remains.

[2026-08-10T14:49:07Z · sase-i8.10.land] Verified all four child phases and their notes against the linked plan, implementation source, and epic commits; confirmed the merge-visibility history partition and two-parent merge fixtures; audited post-start non-epic commits for integration overlap; resolved or routed every proposed follow-up; passed focused VCS and integration tests, just check, strict plan validation, and post-close Symvision; marked the linked plan done.

[2026-08-10T14:49:51Z · sase-i8.10.land] Verified all four child phases and their notes against the linked plan, implementation source, and epic commits; confirmed the merge-visibility history partition and two-parent merge fixtures; audited post-start non-epic commits for integration overlap; resolved or routed every proposed follow-up; passed focused VCS and integration tests, just check, strict plan validation, and post-close Symvision; marked the linked plan done.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i8.10.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i8.10.land/README.md) | [sase-i8.10](sase-i8.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@e1205bb`](https://github.com/sase-org/sase--plans/commit/e1205bb419d139babc47bdde2e213dcdc5e58edf) | docs(plan): mark sase-i8.10 complete | [sase-i8.10](sase-i8.10.md) | 2026-08-10 10:50:53 EDT |
