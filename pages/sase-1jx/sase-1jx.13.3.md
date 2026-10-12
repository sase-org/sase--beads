# Bead: sase-1jx.13.3 — Fix CLI create and suggest gaps

[Bead Pages](../README.md) / [sase-1jx.13](sase-1jx.13.md) / sase-1jx.13.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jx.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.land.md) · **Assignee:** `sase-1jx.13.3` · **Size:** medium
**Created:** 2026-10-12 14:55:56 EDT · **Closed:** 2026-10-12 17:08:01 EDT
**Plan:** [202610/new\_project\_wizard\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202610/new_project_wizard_landing_repairs.md)

## Description

cli-repairs: in sase, make create apply_argv round-trip for every provider (prefixed bare-git refs, visibility only when the form has it), honor bare-git custom directories, report exists-without-evidence as a remote_exists blocker, stop suggest -o from failing providers without owners, make suggest and create tests hermetic, and fix the skill and workspace docs.

## Notes

[2026-10-12T20:07:39Z · sase-1jx.13.3] cli-repairs implemented: create apply_argv uses create_apply_ref (git:NAME) and emits --visibility only when the provider form has that field; _adopt_create_result carries parsed.ref/checkout/identity so custom bare_dir is not orphaned; checkout_dir was removed from the advertised bare-git creation form because ws_resolve_ref would not honor it (ws_create_repo still accepts it if passed); exists-without-evidence is StepBlocked with remote_exists and journal complete; suggest --owner skips providers with no namespaces and no account; hermetic suggest/create tests; skill proposes create via /sase_gate; docs/cli.md and docs/workspace.md updated.

[2026-10-12T21:07:42Z · sase-1jx.13.3] PROPOSED FOLLOW-UP: just check 0fdfdc2203d571246c1c96b582fc9c8d exited 1 with verdict no_new_failures (7 KNOWN TUI tests: stitches-timeline leak, agent jump revive legend/neighbors, project display fake vs my_project, workflow Project tmp vs sase, source hidden-count sidecar chip, TUI import 3517/3513). None are cli-repairs; they reproduce on the witnessed base tree.

[2026-10-12T21:08:01Z · sase-1jx.13.3] cli-repairs done. Verified: create apply_argv round-trips via create_apply_ref (git:NAME) and emits --visibility only when the form has that field (test_create_apply_argv_round_trips_github, test_bare_git_create_end_to_end); custom bare_dir is adopted via parsed.ref/checkout/identity (test_bare_git_create_honors_custom_bare_dir); checkout_dir was removed from the advertised bare-git creation form because ws_resolve_ref would not honor it (ws_create_repo still accepts it if passed); exists-without-evidence is StepBlocked with remote_exists and journal complete; suggest --owner skips providers with no namespaces and no account; hermetic suggest/create tests plus sorted-option and suggest --help tests; skill proposes create via /sase_gate; docs/cli.md and docs/workspace.md updated. Focused onboarding tests 123 passed. just check 0fdfdc2203d571246c1c96b582fc9c8d: no_new_failures (7 KNOWN TUI tests outside this phase). No --epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-1jx.13.1](sase-1jx.13.1.md) ✓ · ⧖ 2026-10-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.13.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.13.3/README.md) | [sase-1jx.13.3](sase-1jx.13.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`926645d`](https://github.com/sase-org/sase/commit/926645df890ea2ca6e11f381c0e355f45614d005) | fix(project): round-trip create apply\_argv and honor bare-git dirs | [sase-1jx.13.3](sase-1jx.13.3.md) | 2026-10-12 17:09:24 EDT |
