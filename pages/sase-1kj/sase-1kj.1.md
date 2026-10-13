# Bead: sase-1kj.1 — Memoize macro-plugin entry-point discovery

[Bead Pages](../README.md) / [sase-1kj](README.md) / sase-1kj.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.102](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.102.md) · **Assignee:** `sase-1kj.1` · **Size:** small
**Created:** 2026-10-13 11:47:18 EDT · **Closed:** 2026-10-13 13:09:43 EDT
**Plan:** [202610/apollo\_tui\_startup.md](https://github.com/sase-org/sase--plans/blob/main/202610/apollo_tui_startup.md)

## Description

plugin-discovery-memo: memoize macro-plugin entry-point discovery per process, keyed by a cheap install signature, so get_plugin_input_type_registry stops rescanning every entry point on every macro input it parses.

## Notes

[2026-10-13T17:09:30Z · sase-1kj.1--1] PROPOSED FOLLOW-UP: test_app_import_budget over cap (3518 vs 3513) reproduces identically on clean base tree (stashed src changes, same count, dataclasses already loaded) — duplicates tracked task sase-1ic; also observed tests/completion zsh sbd smoke and fakey gate-capacity failures outside this phase scope

[2026-10-13T17:09:43Z · sase-1kj.1--1] Memoized macro-plugin entry-point discovery per process keyed by install signature (src/sase/main/plugin_discovery.py) with single known-distribution pass (src/sase/macro/plugin_input_types.py); 28 phase tests pass, just lint clean, no epic-symbol leftovers. just check: full suite 55500 passed; sole NEW failure test_app_import_budget (3518 vs 3513 cap) reproduces identically on clean base and is tracked by sase-1ic.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kj.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kj.1.md) | [sase-1kj.1](sase-1kj.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ce1940f`](https://github.com/sase-org/sase/commit/ce1940f39fd733f5777f4142c2703042b2a8b82b) | feat(macro): add plugin discovery and plugin input types | [sase-1kj.1](sase-1kj.1.md) | 2026-10-13 13:11:33 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1kj.1--1][1] | Need phase scope after verify failure | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kj.1.md

<!-- sase:referenced-by:end -->
