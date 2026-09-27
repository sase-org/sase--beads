# Bead: sase-1bc.2 — sase-core agent tab model, directive contract, and typed units

[Bead Pages](../README.md) / [sase-1bc](README.md) / sase-1bc.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0t4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0t4.md) · **Assignee:** `sase-1bc.2` · **Size:** medium
**Created:** 2026-09-27 10:57:01 EDT · **Closed:** 2026-09-27 11:51:28 EDT
**Plan:** [202609/agents\_dynamic\_tabs.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_dynamic_tabs.md)

## Description

core-tab-model: add sase_core agent_tab.rs (name canonicalization, reserved names, tab keys, effective-tab resolution, catalog ordering), the `tab` directive contract entry with a Tab value role and completion, and typed-unit parsing, validation, re-emission, and digest coverage, plus Python bindings.

## Notes

[2026-09-27T15:51:28Z · sase-1bc.2] sase-core core-tab-model done, uncommitted in linked sase-core checkout (host-owned commit, suggested subject feat:). New agent_tab.rs (canonicalization, AgentTabKeyWire Default/Machine/UnresolvedMachine/Named, viewer-relative resolution, batched catalog with default/machine/named ordering, labels incl. local-remote disambiguation). tab directive entry (COLON_PAREN, Tab value role, examples/recipes/colon support) with kind-tab inventory completion plus main suggestion and LSP needs_agent_entries. Typed units: agent_tab field, duplicate-tab/invalid-tab/tab-on-proc/tab-mismatch codes, clan-generation agreement, re-emit after %hide, digest-covered. New agent_tab py domain with 3 bindings. sase tool run check passed in sase-core (4652 tests, 0 failed; one unrelated provider_priority concurrency flake passed in isolation). epic-symbols clean.

## Dependencies

- **Blocks:** [sase-1bc.3](sase-1bc.3.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bc.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bc.2/README.md) | [sase-1bc.2](sase-1bc.2.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bc.2][1] | Need phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bc.2/README.md

<!-- sase:referenced-by:end -->
