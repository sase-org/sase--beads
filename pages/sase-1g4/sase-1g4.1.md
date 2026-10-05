# Bead: sase-1g4.1 — One input-type vocabulary and strict enum declarations

[Bead Pages](../README.md) / [sase-1g4](README.md) / sase-1g4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0wj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0wj.md) · **Assignee:** `sase-1g4.1` · **Size:** large
**Created:** 2026-10-04 18:19:28 EDT · **Closed:** 2026-10-05 02:04:39 EDT
**Plan:** [202610/macro\_named\_input\_types.md](https://github.com/sase-org/sase--plans/blob/main/202610/macro_named_input_types.md)

## Description

vocab: add the sase-core macro_input_types module (type catalog, resolver, did-you-mean, choice value rules, PyYAML-parity quoting check, enum value check), move every Rust and Python type parser onto it, fix the seven existing enum defects, isolate bad macros, add the strict_macro_input_types sunset flag, generate the JSON schemas, add the config.macro_input_types doctor check, and make #pr's status a real enum.

## Notes

[2026-10-05T06:05:29Z · sase-1g4.1.1.land] Verified child epic sase-1g4.1.1 completed the phase scope: one shared catalog across Rust and Python parsers, strict_macro_input_types sunset flag, enum validation with per-macro isolation, generated schema and doctor check, and #pr status wip | draft | ready. Focused tests (159) and direct Symvision passed; feature schema sync passed. Full sase tool run check could not pass setup because the unchanged probe expects sase_content_layout schema 5 but clean pinned core 0279de6b returns 6 and its stats macro response shape is stale for the probe; details are on child epic note #2. No core edit or pin ratchet was made.

## Dependencies

- **Blocks:** [sase-1g4.2](sase-1g4.2.md) ◐ · ⧖ 2026-10-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1g4.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g4.1.md) | [sase-1g4.1](sase-1g4.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1g4.2.1.4][1] | Need the completed vocabulary dependency handoff | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g4.2.1.4/README.md

<!-- sase:referenced-by:end -->
