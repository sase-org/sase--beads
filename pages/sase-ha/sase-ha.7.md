# Bead: sase-ha.7 — Documentation sweep

[Bead Pages](../README.md) / [sase-ha](README.md) / sase-ha.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ve](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ve/README.md) · **Assignee:** `sase-ha.7` · **Size:** medium
**Created:** 2026-08-07 20:46:12 EDT · **Closed:** 2026-08-07 22:29:12 EDT
**Plan:** [202608/muse\_provider.md](https://github.com/sase-org/sase--plans/blob/main/202608/muse_provider.md)

## Description

docs: add the Muse provider section and update every provider enumeration across the docs set and `default_config.yml` comments, including the new install/update and advisory behavior.

## Notes

[2026-08-08T02:28:45Z · sase-ha.7] PROPOSED FOLLOW-UP: 6 pre-existing test failures unrelated to this phase — tests/test_gate_cli_show.py (4) and tests/gate_conformance/test_gate_conformance.py[cli|ace-legacy_shared_input]; all fail on a clean HEAD (b9ac35d9e) with GateError "option 'audit' cannot be answered: no surface can submit a value its input_schema accepts ('reason' is a required property)", introduced by e1da6d1b7 feat(notification-gates).

[2026-08-08T02:29:12Z · sase-ha.7] Documentation sweep for the Muse provider. docs/llms.md: new Muse Code Integration section (selection/explicit-only, exact invocation, sandbox default + SASE_MUSE_SANDBOX=on, model catalog with pricing and the Contributor caveat, all-seven effort map incl. max->ultra, the five parser rules, tool-call capture with the tool-argument limitation stated plainly, session-log usage recovery and model identity, interrupts, skills/AGENTS.md, env vars, timer) plus a new Model Advisories section; updated the intro, TOC, source layout, entry points, autodetect note, config example, config-fields table, explicit %model syntax, auto-resolution table, short-alias table, effort matrix, env-var reference, token-usage section, and streaming mechanism. docs/agent_providers.md: new Muse Code install/auth/update section and full 'sase agent-cli install' semantics (HTTPS fetch, digest, no shell, --yes/--dry-run/--force, PATH reporting, never edits rc files) plus channel-endpoint/exact-comparison notes. docs/configuration.md: provider enum, Admin Center CLI list, env-var table, Muse invocation + advisory paragraph, skill-init providers, and the sase agent-cli subcommand table gained 'install'. docs/plugins.md: new 'LLM Provider Install Metadata and Advisories' subsection documenting all llm_install_metadata keys and the llm_model_advisories hook as optional. docs/ace.md: badge table, tool-call runtimes, model-picker advisory rendering. docs/xprompt.md, docs/cli.md, docs/getting_started.md, docs/commit_workflows.md, and src/sase/default_config.yml comments updated. Also fixed src/sase/llm_provider/muse.py to declare install_dir '~/.local/bin' + install_dir_env MUSE_INSTALL_DIR so the documented install target actually renders; verified with 'sase agent-cli install muse --dry-run --force' (target line now shows). Verified: just fmt clean, just docs-check builds with no broken anchors, just check lint gates all pass. 6 test failures (test_gate_cli_show, gate_conformance legacy_shared_input) are pre-existing on clean HEAD b9ac35d9e and unrelated; noted separately.

## Dependencies

- **Depends on:** [sase-ha.3](sase-ha.3.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-ha.4](sase-ha.4.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-ha.5](sase-ha.5.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-ha.6](sase-ha.6.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-ha.8](sase-ha.8.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ha.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ha.7/README.md) | [sase-ha.7](sase-ha.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1d5a8a7`](https://github.com/sase-org/sase/commit/1d5a8a70ff84a981f54b1eda0d9384fe687c1f14) | docs(llms): document the Muse Code provider end to end | [sase-ha.7](sase-ha.7.md) | 2026-08-07 22:30:14 EDT |
