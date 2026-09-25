# Bead: sase-17m.4.1.7 — Agent query dialect, CLI help, JSON output, and editor bridge

[Bead Pages](../README.md) / [sase-17m.4.1](sase-17m.4.1.md) / sase-17m.4.1.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.4.md) · **Assignee:** `sase-17m.4.1.7` · **Size:** medium
**Created:** 2026-09-24 13:32:37 EDT
**Plan:** [202609/agent\_session\_runtime\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_runtime_cutover.md)

## Description

query-cli-json: make agent query session:/kind:session canonical, with flag-gated family:/kind:family aliases. Update the CLI help text and flip the JSON output of sase agent list/search/index/wait -j and the sase editor bridge to agent_session keys and session kinds. Refresh the cli_spec snapshot, confirm sase-nvim does not branch on the old editor kinds, and declare a feat! breaking change.

## Dependencies

- **Depends on:** [sase-17m.4.1.6](sase-17m.4.1.6.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17m.4.1.8](sase-17m.4.1.8.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.4.1.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.7/README.md) | [sase-17m.4.1.7](sase-17m.4.1.7.md) | 0 |
