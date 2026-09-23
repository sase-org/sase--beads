# Bead: sase-171.1 — Shared installer learns npm-packaged CLIs

[Bead Pages](../README.md) / [sase-171](README.md) / sase-171.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0q6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0q6.md) · **Assignee:** `sase-171.1` · **Size:** medium
**Created:** 2026-09-23 11:58:15 EDT · **Closed:** 2026-09-23 13:21:05 EDT
**Plan:** [202609/updates\_tab\_agent\_cli\_install.md](https://github.com/sase-org/sase--plans/blob/main/202609/updates_tab_agent_cli_install.md)

## Description

npm-installs: add a pure install-route classifier, npm-package install planning with npm/PATH/writability checks, plan-time PATH status, and a per-entry progress hook in sase.agent_clis; update `sase agent-cli install` rendering, JSON, help, hints, and docs.

## Notes

[2026-09-23T17:20:25Z · sase-171.1] PROPOSED FOLLOW-UP: Pre-existing master failures outside this phase — symvision flags ExpandedLaunchSegments and 15 tests/test_bead work-rendering tests fail on the pristine tree

[2026-09-23T17:21:05Z · sase-171.1] npm-installs done: InstallRoute + pure describe_agent_cli_install, npm plan branch (npm/PATH/writability checks, plan-time PATH status), progress_fn, CLI npm rendering/JSON/help, parser + hookspec + docs updates. Verified: 92 agent_clis tests pass, all lint gates pass except pre-existing symvision hit, live dry-runs show qwen npm preview with target/PATH, agy manual skip, Muse unchanged; scoped lane 45575 passed with only pre-existing test_bead failures (confirmed identical on pristine tree)

## Dependencies

- **Blocks:** [sase-171.2](sase-171.2.md) ◐ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-171.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-171.1/README.md) | [sase-171.1](sase-171.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bc128b6`](https://github.com/sase-org/sase/commit/bc128b655a563be39596a0a3b0d6ec746181458d) | feat(agent-cli): shared installer learns npm-packaged CLIs | [sase-171.1](sase-171.1.md) | 2026-09-23 13:23:08 EDT |
