# Bead: sase-1g4.1.1.1 — Rust input-type catalog, resolver, and Python bindings

[Bead Pages](../README.md) / [sase-1g4.1.1](sase-1g4.1.1.md) / sase-1g4.1.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1g4.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g4.1.md) · **Assignee:** `sase-1g4.1.1.1` · **Size:** medium
**Created:** 2026-10-04 18:33:15 EDT · **Closed:** 2026-10-04 19:10:16 EDT
**Plan:** [202610/macro\_input\_type\_vocab.md](https://github.com/sase-org/sase--plans/blob/main/202610/macro_input_type_vocab.md)

## Description

core: add the macro_input_types catalog, resolver, did-you-mean, choice and PyYAML checks, and Python bindings, leaving the existing parsers in place.

## Notes

[2026-10-04T23:10:16Z · sase-1g4.1.1.1] Added sase-core macro_input_types catalog, resolver, suggest_closest, validate_enum_choices, pyyaml_plain_scalar_is_non_string, and check_input_value, plus sase_core_py bindings. Verified contract tests (enmu→enum, builtin@word/WORD, string→line deprecated, agent named_type/value_role, plugin not-installed and declares-no-input-type, PyYAML vector, choice rules, breif→brief). sase tool run check in sase-core passed (ad5c0f56881469ad7f876fd9af1c7d86). epic-symbols: no leftovers.

## Dependencies

- **Blocks:** [sase-1g4.1.1.2](sase-1g4.1.1.2.md) ◐ · ⧖ 2026-10-04
- **Blocks:** [sase-1g4.1.1.3](sase-1g4.1.1.3.md) ◐ · ⧖ 2026-10-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1g4.1.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g4.1.1.1/README.md) | [sase-1g4.1.1.1](sase-1g4.1.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@2838c7e`](https://github.com/sase-org/sase-core/commit/2838c7eb181521c81e16a29c293f52bfd10d6d3e) | feat: add macro input-type catalog, resolver, and Python bindings | [sase-1g4.1.1.1](sase-1g4.1.1.1.md) | 2026-10-04 19:12:13 EDT |
