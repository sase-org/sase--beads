# Bead: sase-51.2 — Phase 2: Runtime Call-Site Migration In SASE

[Bead Pages](../README.md) / [sase-51](README.md) / sase-51.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-51.2`
**Created:** 2026-06-20 17:52:27 UTC · **Closed:** 2026-06-20 19:01:09 UTC
**Plan:** [202606/linked\_repos\_rename\_codex.md](https://github.com/sase-org/sase--plans/blob/main/202606/linked_repos_rename_codex.md)

## Notes

COMMIT: 56031ddb9

[2026-07-27T21:36:12Z · sase-a1.land] [2026-06-20T18:54:39Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Phase 2 runtime call-site migration complete. Migrated launch_spawn, run_agent_phases (claim_deferred_workspace), run_agent_runner_setup (refresh_linked_repos_for_workspace), run_agent_directives, commit_finalizer_state/prompting, and workspace_handler_list/context from sase.sibling_repos to canonical sase.linked_repos. agent_meta.json now stores canonical linked_repos plus sibling_repos alias. Finalizer prefers SASE_LINKED_REPOS_JSON/opened_linked_workspaces.json, falls back to legacy sibling env+marker; follow-up prompt wording now says 'linked repo'. Legacy PROJECT_STATE: sibling lifecycle and internal finalizer symbols retained. Updated targeted tests + chop-agents resolver patch; added canonical-env/marker and legacy-only-marker compat tests. just check green.

[2026-07-27T21:36:15Z · sase-a1.land] [2026-06-20T19:01:56Z · bryanbugyi34@gmail.com] (restored 2026-07-27) COMMIT: 3e7afa4d7

## Dependencies

- **Depends on:** [sase-51.1](sase-51.1.md) ✓
- **Blocks:** [sase-51.3](sase-51.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-51.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-51.2/README.md) | [sase-51.2](sase-51.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`56031dd`](https://github.com/sase-org/sase/commit/56031ddb995c4454c250e8f48e8af42943393cfa) | refactor(linked\_repos): migrate runtime call-sites to canonical module (sase-51.2) | [sase-51.2](sase-51.2.md) | 2026-06-20 19:02:39 |
