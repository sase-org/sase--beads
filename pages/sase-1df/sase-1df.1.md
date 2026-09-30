# Bead: sase-1df.1 — Rust Jinja catalog and wire types

[Bead Pages](../README.md) / [sase-1df](README.md) / sase-1df.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3g](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3g.md) · **Assignee:** `sase-1df.1` · **Size:** small
**Created:** 2026-09-30 08:47:15 EDT · **Closed:** 2026-09-30 09:14:47 EDT
**Plan:** [202609/jinja\_variable\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/jinja_variable_completion.md)

## Description

catalog: add a static, documented catalog to sase-core covering sase's built-in Jinja variables and their availability rules, Jinja globals, filters, tests, statement keywords, and namespace members, plus the request/response wire types the engine will return.

## Notes

[2026-09-30T13:14:14Z · sase-1df.1] PROPOSED FOLLOW-UP: sase-core `sase tool run check` clippy gate fails on clean base too (9 pre-existing errors from newer clippy: nonminimal_bool/collapsible_match/manual_range_contains in agent_runtime, agent_scan, finalizer, fleet_owner_facts, provider_usage, tool_run) — none in editor/jinja; verify with git stash + ./scripts/check.sh clippy

[2026-09-30T13:14:47Z · sase-1df.1] sase-core editor/jinja module added (mod.rs facade, wire.rs snake_case wires + JINJA_CATALOG_WIRE_SCHEMA_VERSION=1, catalog.rs with 14 variables incl. loop/wait members, 57 filters, 33 tests, 6 globals, 24 statements); pub mod jinja registered, lib.rs untouched. Verified: 5 new catalog tests + full editor suite (336 tests) pass; catalog filter/test names match live Jinja 3.1.2 exactly; clippy clean for new files (full-check clippy failure is pre-existing on clean base, recorded as PROPOSED FOLLOW-UP).

## Dependencies

- **Blocks:** [sase-1df.3](sase-1df.3.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1df.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1df.1/README.md) | [sase-1df.1](sase-1df.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@8f06984`](https://github.com/sase-org/sase-core/commit/8f0698476b50b3b6f571ab9e8537a79152118e7a) | feat(editor): add Rust Jinja catalog and wire types | [sase-1df.1](sase-1df.1.md) | 2026-09-30 09:18:04 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1df.1][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1df.2][2] | Check catalog phase status for scan dependency | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1df.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1df.2/README.md

<!-- sase:referenced-by:end -->
