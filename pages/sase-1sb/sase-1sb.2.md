# Bead: sase-1sb.2 — Trust-gate command-bearing project-local config

[Bead Pages](../README.md) / [sase-1sb](README.md) / sase-1sb.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bk](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bk.md) · **Assignee:** `sase-1sb.2` · **Size:** large
**Created:** 2026-11-11 17:38:53 EST · **Closed:** 2026-11-12 16:52:26 EST
**Plan:** [202611/security\_bug\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/security_bug_audit_fixes.md)

## Description

SASE merges project-local config (`sase/sase.yml` found by walking up from cwd to
the nearest VCS root: src/sase/config/core.py `load_merged_config`, ~lines
562-604, local layer via `get_local_config_path` /
`discover_project_root` in src/sase/content_layout.py) with the same authority as
the user's own ~/.config/sase/sase.yml. Command-bearing keys from that local layer
are executed with `shell=True` by host-side (not permission-gated) processes:

- commit hooks: src/sase/workflows/commit/command_hooks.py:176 (`Popen(cmd,
  shell=True)`), fed from `load_merged_config()["commit_hooks"]["before"/"after"]`
- rebase gate: src/sase/workflows/commit/rebase_gate_process.py:58, fed from
  `commit_hooks.after_rebase` via `load_merged_config_for_local_path`
- file hooks: src/sase/file_hooks/runner.py:188, commands from
  `file_hooks[].command` across `load_config_layers()` including the local layer
  (src/sase/config/file_hooks.py)
- workflows/macros are also loadable from the local layer (config/core.py
  `load_macros_by_source`), and macro workflow bash steps execute at expansion
  time.

Consequence: a hostile repo adopted as a project, or an agent editing its own
workspace's sase/sase.yml, injects commands that the host-owned commit finalizer
runs with no gate — defeating the "Completion Is Host-Owned" boundary (agents must
not be able to escalate a plain file write into host-side execution).

Implement per the epic's `local_config_commands` decision. For `digest_trust`
(default): execute command-bearing local-layer config (commit_hooks,
file_hooks[].command, local-layer macro/workflow definitions that contain bash or
python steps) only when the user has acknowledged that project's current
command-bearing content, pinned to a content digest; any change requires
re-acknowledgment (direnv-style allow model). Untrusted state must not block
non-command config (display names, aliases, etc.). Design the trust store
location, the acknowledgment UX (a CLI command and/or gate prompt — never
agent-answerable), and the refusal diagnostics as part of this phase's planning.
For `user_layers_only`: stop honoring command-bearing keys from the local layer
entirely and document the migration (hooks move to user config/overlays).

This deprecates user-reaching behavior, so before implementing read the memory
notes sase/memory/sase_flags.md (a `sunset` flag is mandatory: old
run-local-commands-untrusted branch stays reachable while migrating; create it
with `sase flag new`, never by hand) and the gotchas core note (update
src/sase/default_config.yml if config keys are added). Tests must cover both flag
states, trusted/untrusted/digest-changed projects, and that an untrusted local
layer still merges its non-command keys.

## Notes

[2026-11-12T10:30:48Z · sase-1sb.2.1.land] LANDING BLOCKER: Child epic sase-1sb.2.1 remains open after source review and safe reproductions showed snapshot/provenance, revocation, cache, embedded-execution, and sparse-composition gaps. Evidence file:explicit:f7ff68994727a64108f4cdd2 and full audit/follow-up disposition are on the child. A validated medium tale will repair these and close the child and this delegated phase in its final implementation turn. Do not mark this phase complete before those checks and symbol cleanup. The separate edit-lock ownership race was routed to containing epic sase-1sb.

[2026-11-12T21:52:45Z · sase-1sb.2.1.land] PHASE VERIFIED COMPLETE (sase-1sb.2.1 final lander): child epic sase-1sb.2.1 closed after verification; the store auto-closed this phase on that close. Delegated scope met: digest_trust decision implemented (no user_layers_only branch); command-bearing local commit_hooks, file_hooks (literal+template), and local macro/workflow definitions (incl. nested/parallel/embedded and sparse overrides) execute only with a current human acknowledgment pinned to a SHA-256 digest of the canonical command-bearing projection; any change or revoke blocks until re-acknowledged; non-command local config still merges; acknowledgment is CLI-only (sase config trust allow/status/revoke), refuses agents/monitors and requires a terminal; skip diagnostics name the config path and allow command. Mandatory sunset flag local_config_command_trust created via sase flag new (On default, Off compatibility); both states tested. Evidence: sase tool run check fffa4e1a3a43c60a1170ee3e2eeedcdd pass; 200 focused tests pass; epic-symbols empty. Containing epic sase-1sb left to its own land agent.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sb.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sb.2.md) | [sase-1sb.2](sase-1sb.2.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1sb.2.1.land--3][1] | Need parent phase scope and notes before closeout | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sb.2.1.land.md

<!-- sase:referenced-by:end -->
