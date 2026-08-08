# Bead: sase-ha.3 — sase agent-cli install

[Bead Pages](../README.md) / [sase-ha](README.md) / sase-ha.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ve](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ve/README.md) · **Assignee:** `sase-ha.3` · **Size:** medium
**Created:** 2026-08-07 20:45:48 EDT
**Plan:** [202608/muse\_provider.md](https://github.com/sase-org/sase--plans/blob/main/202608/muse_provider.md)

## Description

cli_install: add a confirmed, shell-free `sase agent-cli install` subcommand that fetches a provider-declared installer over HTTPS, shows its digest before running it, and never edits the user's shell rc files.

## Notes

[2026-08-08T01:41:33Z · sase-ha.3] PROPOSED FOLLOW-UP: tests/test_multi_prompt_launcher_xprompt_groups.py::test_launcher_qualifies_research_swarm_per_dispatch failed once under the full parallel `just test-scoped` lane on 2026-08-07 but passes in isolation, with its own file, and against a clean tree — investigate as parallel/order-dependent flakiness unrelated to agent-CLI work.

## Dependencies

- **Depends on:** [sase-ha.1](sase-ha.1.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-ha.7](sase-ha.7.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ha.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ha.3/README.md) | [sase-ha.3](sase-ha.3.md) | 0 |
