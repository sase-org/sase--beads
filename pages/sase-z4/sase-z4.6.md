# Bead: sase-z4.6 — Complete weighted capacity ownership, presentation, and release acceptance

[Bead Pages](../README.md) / [sase-z4](README.md) / sase-z4.6

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-z4.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-z4.land.md) · **Assignee:** `sase-z4.6.land`
**Created:** 2026-09-10 08:15:39 EDT
**Plan:** [202609/weighted\_capacity\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/weighted_capacity_landing_repairs.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/weighted_capacity_landing_repairs.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/weighted_capacity_landing_repairs.md

<!-- sase:links:end -->

## Description

Repair the remaining sase-z4 acceptance failures and integrate weighted capacity with the newer fleet UI so its parent landing can resume.

## Notes

[2026-09-10T21:58:24Z · 0ix.f0--4] DISCOVERED ISSUE: tests/fakey/test_runner_slots_e2e.py::test_installed_research_swarm_quarter_weights_fill_one_fakey_capacity_unit fails on current master, reproduced 2026-09-10 in workspace sase_21 while verifying an unrelated usage-limit provider diff (no fakey/queue/xprompt files touched). Confirmed pre-existing two ways: (1) reran with the diff fully stashed out (git stash -u) and it failed identically; (2) reran in a throwaway git worktree checked out at origin/master tip (4a862d6ea, this workspace's remote HEAD) using the same venv, and it still fails identically, so this is not explained by this workspace being behind origin.

Failure: plan_typed_launch_units(expand_prompt_for_typed_launch('#research_swarm:: weighted queue acceptance'), selected_project='sase') raises ValueError('%wait(priority=...) has moved to %queue. Use %queue(priority=N) or %q(p=N), and keep dependencies on %wait.') from the Rust binding (src/sase/core/agent_launch_facade.py:192). The installed sase-core-rs wheel (0.33.0, matches the >=0.33.0,<0.34.0 pin) already rejects %wait(priority=...), but the research_swarm xprompt / test fixture still emits the old %wait(priority=...) syntax instead of %queue(priority=N).

Routing here rather than filing a new CI task bead because the %wait→%queue migration is this epic's weighted-queue-capacity surface (flag sase-z5, created by this epic's phase .2).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-z4.6.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-z4.6.land.md) | [sase-z4.6](sase-z4.6.md) | 0 |
