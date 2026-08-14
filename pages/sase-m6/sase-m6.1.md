# Bead: sase-m6.1 — Live defects, golden fixtures, and the conformance harness

[Bead Pages](../README.md) / [sase-m6](README.md) / sase-m6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.01u](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.01u.md) · **Assignee:** `sase-m6.1` · **Size:** medium
**Created:** 2026-08-14 17:05:24 EDT · **Closed:** 2026-08-14 17:49:44 EDT
**Plan:** [202608/artifacts\_pane\_contract.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_pane_contract.md)

## Description

foundation: make provider tabs deterministic and failure-visible, then freeze golden query/relation/persistence fixtures from current Patch behavior and stand up the conformance harness every later phase extends.

## Notes

[2026-08-14T21:49:10Z · sase-m6.1] PROPOSED FOLLOW-UP: App key `x` is still double-booked — kill_agent and toggle_hide_submitted share the default and both remain enabled on Agents, the Patch pane, and AXE, so first-binding-wins can hide submitted-toggle the same way `o` hid grouping.

[2026-08-14T21:49:23Z · sase-m6.1] PROPOSED FOLLOW-UP: Full-suite CLI/TUI pretty-print tests fail under FORCE_COLOR=1 because they assert unstyled substrings against ANSI-wrapped output; just check with NO_COLOR=1 passed.

[2026-08-14T21:49:44Z · sase-m6.1] Verified deterministic hash accents never write ARTIFACTS_ACCENTS; discovery failures and missing_ref_provider keep a named degraded tab; Patch o grouping is reachable via unbound mark_pr_origin + bang !o; golden query/relation/persistence fixtures and an extensible conformance harness are in tests/ace/tui/artifacts_contract/. just lint passed; just check passed after unsetting FORCE_COLOR (escalated full suite because default_config.yml is a src-data-asset).

[2026-08-14T21:50:59Z · sase-m6.1] Verified provider accents hash from ref_kind and skip built-ins; failed listings keep named degraded tabs; mark_pr_origin is bang-mode !o so o/O cycle Patch grouping; query/relation/persistence goldens and conformance harness pass; just install + just check passed with NO_COLOR=1 (FORCE_COLOR=1 fails unrelated CLI pretty-print asserts).

## Dependencies

- **Blocks:** [sase-m6.3](sase-m6.3.md) ◐ · ⧖ 2026-08-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m6.1/README.md) | [sase-m6.1](sase-m6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`191e9f2`](https://github.com/sase-org/sase/commit/191e9f2196830a547306d6de0f660a3cccf00235) | feat(ace): stabilize provider tabs and freeze Patch contract goldens | [sase-m6.1](sase-m6.1.md) | 2026-08-14 17:51:38 EDT |
