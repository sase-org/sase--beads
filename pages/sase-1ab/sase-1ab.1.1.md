# Bead: sase-1ab.1.1 — sase-core additive sase-turn rename (core-expand)

[Bead Pages](../README.md) / [sase-1ab.1](sase-1ab.1.md) / sase-1ab.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ab.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.1.md) · **Assignee:** `sase-1ab.1.1.land`
**Created:** 2026-09-26 00:28:13 EDT · **Closed:** 2026-09-26 03:08:14 EDT
**Plan:** [202609/sase\_core\_turn\_expand.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_core_turn_expand.md)

## Description

sase-core names the former sase-shell concept with turn and named-proc vocabulary in Rust modules, types, functions, constants, tests, comments, and messages, and registers the two new pyo3 binding names next to the legacy ones. Every renamed input accepts the old and new spellings. Serialized output, schema versions, the SQLite gate_shell_id column, and goldens stay byte-identical, so a sase tree pinned to the previous core, and a sase workspace rebuilt against this core, still passes sase tool run check with no sase source changes.

## Notes

[2026-09-26T07:08:14Z · sase-1ab.1.1.land] Verified all four closed phase scopes and notes against core commits c2c2f94, 4a04cea, 20deb1b, and 6953a96 and current source: turn/named-proc Rust names, dual Python bindings, new-input aliases, legacy serialized output, unchanged parity JSON, fleet golden, SQLite column, and schema versions. Linked core sase tool run check passed (ddb92ef0468dc96df33324dcd38e43ed); phase-4 sase check runs 03cb6e7e07e238c5e73e32f5d725e and 6aa0d222d39496a8c1b42b64a33137f3 passed on unchanged sase HEAD. Integration review found no non-epic commit after the first phase commit in core and no new origin/master commit in sase; later release/core-pin commits are unmerged side branches, with final pin work already assigned to parent phase sase-1ab.8. Proposal outcomes: .1#2 contract-flip -> active parent phase sase-1ab.7; .1#3 fleet-runtime -> completed by .3; .2#2 contract-flip -> .7; .3#2 contract-flip -> .7; .4#1 contract-flip -> .7; .4#2 wire-cutover -> active parent phase sase-1ab.2; .4#3 runtime-cutover -> active parent phase sase-1ab.3. No new task bead: every proposal is completed here or explicitly scoped to the active parent epic. epic-symbols was empty.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ab.1.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ab.1.1.land/README.md) | [sase-1ab.1.1](sase-1ab.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@9aa7bc7`](https://github.com/sase-org/sase--plans/commit/9aa7bc779863f292b23347f0ff42ef74c3209376) | chore(plan): mark sase-core turn expansion complete | [sase-1ab.1.1](sase-1ab.1.1.md) | 2026-09-26 03:23:34 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ab.1.1.land][1] | Need the epic scope, children, and linked plan file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ab.1.1.land/README.md

<!-- sase:referenced-by:end -->
