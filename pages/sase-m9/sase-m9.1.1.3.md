# Bead: sase-m9.1.1.3 — Monitor agent CLI language and compatibility

[Bead Pages](../README.md) / [sase-m9.1.1](sase-m9.1.1.md) / sase-m9.1.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m9.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.1.md) · **Assignee:** `sase-m9.1.1.3` · **Size:** medium
**Created:** 2026-08-14 19:24:33 EDT · **Closed:** 2026-08-14 20:25:16 EDT
**Plan:** [202608/shell\_taxonomy.md](https://github.com/sase-org/sase--plans/blob/main/202608/shell_taxonomy.md)

## Description

monitor-agent-cli: rename monitor lane-facing language and filters to agent, use -a/--agent for start, retain -a/--all plus -l/--agent for list, accept deprecated --lane compatibility aliases without advertising them, and update handlers, completions, skill source, docs, errors, JSON scope compatibility, and focused tests while preserving monitor behavior.

## Notes

[2026-08-15T00:25:16Z · sase-m9.1.1.3] Renamed monitor CLI lane-facing language to agent: sase monitor start now exposes -a/--agent (was -l/--lane), sase monitor list keeps -a/--all and renames its filter to -l/--agent, and --lane is retained as a suppressed compatibility alias on both (dest shared, tested via new parser+handler tests). Updated handler error/scope text ('no agent given...', 'agent X has no active monitor', scope label), added a deprecated 'lane' key alongside the new 'agent' key in the list JSON scope for compatibility, renamed the CLI table/detail/markdown 'Lane' labels to 'Agent' (record JSON field 'lane' left untouched for historical-row compatibility), and updated src/sase/xprompts/skills/sase_monitor.md + docs/monitors.md flag references. Verified via: full focused monitor test suite (tests/main + tests/monitor, 1500 passed), live --help output for all four subcommands, a live --lane smoke test confirming the compatibility alias still filters, 'sase skill init --diff' showing only the intended skill-doc wording changes, and 'just check' (all lint gates + scoped test lane) green after 'just fmt' for markdown.

[2026-08-15T00:26:16Z · sase-m9.1.1.3] Verified: renamed monitor CLI lane-facing language to agent (start uses -a/--agent, list keeps -a/--all and -l/--agent, --lane retained as suppressed compat alias); updated handler error/scope text, list JSON scope compat key, CLI display labels, skill doc, and docs/monitors.md; full monitor test suite (tests/main + tests/monitor, 1500 tests) and just check (lint gates + scoped tests) pass.

## Dependencies

- **Depends on:** [sase-m9.1.1.1](sase-m9.1.1.1.md) ✓ · ⧖ 2026-08-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m9.1.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m9.1.1.3/README.md) | [sase-m9.1.1.3](sase-m9.1.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e923dcb`](https://github.com/sase-org/sase/commit/e923dcb5d104705db58ffdf402309b85aac160b5) | feat(monitor)!: rename monitor CLI lane-facing language to agent | [sase-m9.1.1.3](sase-m9.1.1.3.md) | 2026-08-14 20:27:09 EDT |
