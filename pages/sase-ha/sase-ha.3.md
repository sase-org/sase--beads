# Bead: sase-ha.3 — sase agent-cli install

[Bead Pages](../README.md) / [sase-ha](README.md) / sase-ha.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ve](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ve/README.md) · **Assignee:** `sase-ha.3` · **Size:** medium
**Created:** 2026-08-07 20:45:48 EDT · **Closed:** 2026-08-07 21:54:37 EDT
**Plan:** [202608/muse\_provider.md](https://github.com/sase-org/sase--plans/blob/main/202608/muse_provider.md)

## Description

cli_install: add a confirmed, shell-free `sase agent-cli install` subcommand that fetches a provider-declared installer over HTTPS, shows its digest before running it, and never edits the user's shell rc files.

## Notes

[2026-08-08T01:41:33Z · sase-ha.3] PROPOSED FOLLOW-UP: tests/test_multi_prompt_launcher_xprompt_groups.py::test_launcher_qualifies_research_swarm_per_dispatch failed once under the full parallel `just test-scoped` lane on 2026-08-07 but passes in isolation, with its own file, and against a clean tree — investigate as parallel/order-dependent flakiness unrelated to agent-CLI work.

[2026-08-08T01:42:17Z · sase-ha.3] PROPOSED FOLLOW-UP: every sase CLI invocation warns "Skipping invalid file hook 'research-highlights' from config layer 'user': 'globs' was renamed to 'path_globs'" — the user-layer config in chezmoi was not migrated with the 6ef7d14d5 file-hooks rename, so that hook is silently disabled.

[2026-08-08T01:53:19Z · sase-ha.3] PROPOSED FOLLOW-UP: 6 pre-existing test failures on master (47b9f0017), unrelated to this phase — tests/test_gate_cli_show.py (4 tests) and tests/gate_conformance/test_gate_conformance.py[cli|ace-legacy_shared_input] all raise GateError "option 'audit' cannot be answered: no surface can submit a value its input_schema accepts ('reason' is a required property)" from src/sase/notification_gates/kind_validation/custom.py:52; the legacy shared-input fixtures were not migrated with commit a1cc172d3.

[2026-08-08T01:54:37Z · sase-ha.3] Added sase agent-cli install: a new install.py (HTTPS-only fetch with redirect-downgrade rejection, size cap, 0o600 temp file, SHA-256 digest, shell-free 'bash <tmpfile>' through run_command with the provider's install_env, post-install re-probe and PATH reporting, guaranteed temp cleanup via plan.cleanup() in a finally) and cli_install.py (Rich panel + versioned JSON envelope, exit 2 for usage/unknown-name/unconfirmed, exit 1 for failures). Registered the subcommand in parser_agent_cli.py and agent_cli_handler.py (metavar {install,list,update}, alphabetical, every long option given a short alias per cli_rules). Confirmation is mandatory: --yes or an interactive prompt; --dry-run prints URL, digest, command, env, and target and executes nothing. Added install_dir/install_dir_env install-metadata keys (hookspec, _registry_metadata, detect, AgentCliStatus) so the target directory is knowable before the run, and AgentCliOperation + script_digest so installs journal into the same durable history as updates (old records without those fields still decode). Promoted find_agent_cli_status/reason_with_docs/command_output_tail in operations.py and command_text/render_reason in cli_update.py instead of duplicating them. Verified: 34 new tests in tests/agent_clis/test_install.py and test_cli_install.py plus extended detect/history/registry tests, all 146 agent-cli/provider/doctor tests green, no network in tests; 'just check' lint gates all pass (ruff, mypy, symvision, keep-sorted, toobig, changelog); live smoke of 'sase agent-cli install codex --offline --json' (npm skip), '--dry-run' and unknown-name paths, and --help output. The scoped test lane reported 6 failures in tests/test_gate_cli_show.py and tests/gate_conformance (GateError on legacy shared-input fixtures) which I confirmed reproduce on a clean master checkout, plus one order-dependent flake in test_multi_prompt_launcher_xprompt_groups.py; both are noted as PROPOSED FOLLOW-UPs and are unrelated to this phase.

[2026-08-08T01:55:42Z · sase-ha.3] Verified: install/cli_install implemented with HTTPS-only fetch + redirect recheck, digest shown before run, shell-free execution, mandatory confirmation, no rc-file edits; 34 new tests + extended detect/history/registry tests green; just check lint gates pass.

## Dependencies

- **Depends on:** [sase-ha.1](sase-ha.1.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-ha.7](sase-ha.7.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ha.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ha.3/README.md) | [sase-ha.3](sase-ha.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`85d1261`](https://github.com/sase-org/sase/commit/85d12614e2ae2ab6acc5b4455bba095e91bdb297) | feat(agent-clis): add a confirmed, shell-free \`sase agent-cli install\` | [sase-ha.3](sase-ha.3.md) | 2026-08-07 21:56:50 EDT |
