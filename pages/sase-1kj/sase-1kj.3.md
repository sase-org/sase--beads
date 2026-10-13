# Bead: sase-1kj.3 — Trim self-inflicted Agents-loader critical-path costs

[Bead Pages](../README.md) / [sase-1kj](README.md) / sase-1kj.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.102](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.102.md) · **Assignee:** `sase-1kj.3` · **Size:** small
**Created:** 2026-10-13 11:47:18 EDT · **Closed:** 2026-10-13 13:21:52 EDT
**Plan:** [202610/apollo\_tui\_startup.md](https://github.com/sase-org/sase--plans/blob/main/202610/apollo_tui_startup.md)

## Description

loader-path-trims: read the dismissed index without write transactions (which fixes its never-hitting cache), skip the repro-capture and update-receipt imports unless needed, and resolve artifact dirs only for running agents.

## Notes

[2026-10-13T17:21:38Z · sase-1kj.3] PROPOSED FOLLOW-UP: TUI app import budget remains 3518 modules vs the 3513 cap on clean base and is already tracked by sase-1ic; tools/tui_import_closure --diff clean-base reports +0 modules after this phase.

[2026-10-13T17:21:52Z · sase-1kj.3] Implemented read-only dismissed-index queries, lazy Agents repro/toast imports, and running-only artifact-dir resolution. just fmt passed; focused loader/index/toast and panel tests: 36 passed. Import closure is 3518 on clean base and current (+0); the clean-base budget failure is tracked by sase-1ic. just check completed 55,498 tests with one load-related panel timeout (passes focused rerun) and one KNOWN soak failure; epic-symbol check is clear.

## Dependencies

- **Blocks:** [sase-1kj.7](sase-1kj.7.md) ◐ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kj.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kj.3/README.md) | [sase-1kj.3](sase-1kj.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`099fcee`](https://github.com/sase-org/sase/commit/099fcee22102465e479348d817023a34fb40364b) | perf(ace): trim agents loader startup costs | [sase-1kj.3](sase-1kj.3.md) | 2026-10-13 13:23:04 EDT |
