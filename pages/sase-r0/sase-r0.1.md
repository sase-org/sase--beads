# Bead: sase-r0.1 — tmux\_agent configuration section

[Bead Pages](../README.md) / [sase-r0](README.md) / sase-r0.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07y](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07y.md) · **Assignee:** `sase-r0.1` · **Size:** small
**Created:** 2026-08-19 11:56:59 EDT · **Closed:** 2026-08-19 13:21:17 EDT
**Plan:** [202608/tmux\_agent\_launcher.md](https://github.com/sase-org/sase--plans/blob/main/202608/tmux_agent_launcher.md)

## Description

config: add the `tmux_agent` config block, JSON schema entry, shipped defaults, and typed getters.

## Notes

[2026-08-19T17:20:43Z · sase-r0.1] PROPOSED FOLLOW-UP: tests/completion/test_snapshot.py fails on this tree even with no local CLI changes — just sync-completion-spec; just check escalates to the full suite when Justfile/schema/default_config.yml change and then hits this pre-existing drift.

[2026-08-19T17:21:00Z · sase-r0.1] PROPOSED FOLLOW-UP: re-keyed stale sase-qt.6 --epic-symbol entries to sase-qt.8 and whitelisted classify_flat_query_tokens on sase-qy.3 so just check lint passes — those later phases should drop the entries once the symbols are consumed or made private.

[2026-08-19T17:21:17Z · sase-r0.1] Added tmux_agent config section: shipped defaults in default_config.yml, schema with additionalProperties false at both levels, effort enum including off, per-provider bypass_permissions with no default, typed TmuxAgentConfig/TmuxAgentProviderConfig getters that fail-soft (invalid key dropped, unknown provider names kept). Verified: 29 tests in tests/test_config_tmux_agent.py plus test_default_config_matches_public_schema; ruff/mypy clean; sase bead epic-symbols sase-r0.1 empty. just check escalated (justfile/src-data-asset/core-identity) and the full suite hit pre-existing tests/completion/test_snapshot.py drift that also fails on a clean tree.

[2026-08-19T17:23:14Z · sase-r0.1] Added tmux_agent config section: shipped defaults in default_config.yml, schema with additionalProperties false at both levels, effort enum including off, per-provider bypass_permissions with no default, typed TmuxAgentConfig/TmuxAgentProviderConfig getters that fail-soft (invalid key dropped, unknown provider names kept). Verified: 29 tests in tests/test_config_tmux_agent.py plus test_default_config_matches_public_schema; ruff/mypy clean; sase bead epic-symbols sase-r0.1 empty. just check escalated (justfile/src-data-asset/core-identity) and the full suite hit pre-existing tests/completion/test_snapshot.py drift that also fails on a clean tree.

## Dependencies

- **Blocks:** [sase-r0.3](sase-r0.3.md) ◐ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-r0.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-r0.1/README.md) | [sase-r0.1](sase-r0.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`14204d6`](https://github.com/sase-org/sase/commit/14204d6a48a7188c4c12f66a4c2f55cfea21b093) | feat(config): add tmux\_agent configuration section | [sase-r0.1](sase-r0.1.md) | 2026-08-19 13:29:27 EDT |
