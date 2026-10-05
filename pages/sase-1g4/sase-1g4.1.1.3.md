# Bead: sase-1g4.1.1.3 — Python loaders, isolation, handoff, and the sunset flag

[Bead Pages](../README.md) / [sase-1g4.1.1](sase-1g4.1.1.md) / sase-1g4.1.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1g4.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g4.1.md) · **Assignee:** `sase-1g4.1.1.3` · **Size:** medium
**Created:** 2026-10-04 18:33:18 EDT · **Closed:** 2026-10-04 19:27:26 EDT
**Plan:** [202610/macro\_input\_type\_vocab.md](https://github.com/sase-org/sase--plans/blob/main/202610/macro_input_type_vocab.md)

## Description

loaders: move every Python type parser onto the resolver, validate choices and defaults at load, isolate a bad macro, round-trip handoff fields, and add the strict_macro_input_types sunset flag.

## Notes

[2026-10-04T23:21:33Z · sase-1g4.1.1.3] Corpus scan: checked 13 definitions across this project and home macro roots plus both installed plugin macro resources (sase_github and sase_research_artifacts); found zero choices declarations. Enum choice and default validation can therefore be unconditional.

[2026-10-04T23:26:01Z · sase-1g4.1.1.3] PROPOSED FOLLOW-UP: Ratchet sase-core-revision.txt to include 2838c7eb181521c81e16a29c293f52bfd10d6d3e so the pinned extension exposes macro_input_types; current pin 2f16dc4 and installed sase_core_rs lack resolve_input_type, validate_enum_choices, and check_input_value, while the linked checkout contains them.

[2026-10-04T23:26:59Z · sase-1g4.1.1.3] PROPOSED FOLLOW-UP: Resume the loader integration after the macro_input_types bindings are present in the pinned extension; wire and register strict_macro_input_types (flag bead sase-1g9), choice validation, per-macro isolation, and handoff fields through the resolver.

[2026-10-04T23:27:26Z · sase-1g4.1.1.3] Verified 13 project/home macro definitions and both installed plugin macro resources contain no choices declarations; epic-symbol audit found no entries. The pinned core revision 2f16dc4 and installed extension lack macro_input_types bindings, while linked core commit 2838c7e contains them. Recorded the pin and loader integration as PROPOSED FOLLOW-UPs; no core files or unrelated beads were changed.

## Dependencies

- **Depends on:** [sase-1g4.1.1.1](sase-1g4.1.1.1.md) ✓ · ⧖ 2026-10-04
- **Blocks:** [sase-1g4.1.1.4](sase-1g4.1.1.4.md) ◐ · ⧖ 2026-10-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1g4.1.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g4.1.1.3/README.md) | [sase-1g4.1.1.3](sase-1g4.1.1.3.md) | 0 |
