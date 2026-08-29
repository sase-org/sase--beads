# Bead: sase-vd.3 — One workspace identity per runner

[Bead Pages](../README.md) / [sase-vd](README.md) / sase-vd.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ft](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ft.md) · **Assignee:** `sase-vd.3` · **Size:** medium
**Created:** 2026-08-28 18:06:19 EDT · **Closed:** 2026-08-28 20:17:31 EDT
**Plan:** [202608/one\_workspace\_per\_agent\_family.md](https://github.com/sase-org/sase--plans/blob/main/202608/one_workspace_per_agent_family.md)

## Description

single-workspace-identity: when a VCS workflow legitimately allocates a workspace for a runner that had none (deferred/`#0` launches), rebind the runner's own workspace identity to it so `done.json`, the checkout occupant record, monitor start, and shell member meta all name the directory the agent actually works in, rather than leaving `workspace_num` pointing at the launcher's slot while only `step_output.meta_workspace` knows the truth.

## Notes

[2026-08-29T00:17:05Z · sase-vd.3] PROPOSED FOLLOW-UP: investigate intermittent full-suite test flakes during verification — normal just check failed twice on different isolated-passing tests before passing on the third normal run

[2026-08-29T00:17:31Z · sase-vd.3] Implemented runner-bound workspace identity rebind; verified with focused pytest for running_field/git_setup/workflow_executor/run_agent_workspace_identity, linked sase-github gh_setup pytest, linked sase-core transfer tests, and normal just check passing after isolated-passing unrelated full-suite flakes.

## Dependencies

- **Depends on:** [sase-vd.1](sase-vd.1.md) ✓ · ⧖ 2026-08-28
- **Blocks:** [sase-vd.4](sase-vd.4.md) ◐ · ⧖ 2026-08-28
- **Blocks:** [sase-vd.5](sase-vd.5.md) ◐ · ⧖ 2026-08-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-vd.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vd.3/README.md) | [sase-vd.3](sase-vd.3.md) | 3 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b7fcee9`](https://github.com/sase-org/sase/commit/b7fcee9db595cebb6b5fcbc474898fab8c6595e8) | feat(agent): rebind runner workspace identity | [sase-vd.3](sase-vd.3.md) | 2026-08-28 20:19:02 EDT |
| sase-core | [`sase-core@4f16434`](https://github.com/sase-org/sase-core/commit/4f16434b5a5be70711d4617ef9a164c4efa28905) | fix(agent-launch): transfer workspace claim names | [sase-vd.3](sase-vd.3.md) | 2026-08-28 20:21:21 EDT |
| sase-github | [`sase-github@f4663ae`](https://github.com/sase-org/sase-github/commit/f4663ae526929b23378372005662c20b495bd0f7) | feat(gh): mark runner-bound workspace allocations | [sase-vd.3](sase-vd.3.md) | 2026-08-28 20:23:10 EDT |
