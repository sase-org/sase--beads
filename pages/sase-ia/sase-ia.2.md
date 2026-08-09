# Bead: sase-ia.2 — Config schema, deprecation registry, and packaged defaults

[Bead Pages](../README.md) / [sase-ia](README.md) / sase-ia.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.we.f0.w1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.we.f0.w1/README.md) · **Assignee:** `sase-ia.2` · **Size:** small
**Created:** 2026-08-09 10:23:10 EDT · **Closed:** 2026-08-09 10:54:32 EDT
**Plan:** [202608/memory\_config\_section.md](https://github.com/sase-org/sase--plans/blob/main/202608/memory_config_section.md)

## Description

config-surface: add the `memory` object with `h1_title` and `glossary` to sase.schema.json, mark the two legacy top-level keys deprecated, register them in DEPRECATED_TOP_LEVEL_KEYS, restructure default_config.yml, and update the schema and inventory tests.

## Notes

[2026-08-09T14:54:32Z · sase-ia.2] Added memory{h1_title,glossary} object to sase.schema.json, marked legacy top-level amd_h1_title/glossary deprecated with pointer descriptions, registered both in DEPRECATED_TOP_LEVEL_KEYS (alphabetical), restructured default_config.yml's amd_h1_title/glossary example under memory:, and updated test_config_schema.py, test_config_schema_agent_experience.py, and test_config_inventory.py to cover the nested canonical paths, legacy fallback, deprecated flags, and memory additionalProperties rejection. Verified with just check-full (all lint gates + full test suite green) after just install rebuilt sase_core_rs from the linked sase-core checkout.

## Dependencies

- **Depends on:** [sase-ia.1](sase-ia.1.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-ia.4](sase-ia.4.md) ◐ · ⧖ 2026-08-09
- **Blocks:** [sase-ia.5](sase-ia.5.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ia.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ia.2/README.md) | [sase-ia.2](sase-ia.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`069d09c`](https://github.com/sase-org/sase/commit/069d09c90380d477a9a5bab6b84faadfcfa1815f) | feat(config): add memory.h1\_title and memory.glossary, deprecate legacy top-level keys | [sase-ia.2](sase-ia.2.md) | 2026-08-09 10:55:27 EDT |
