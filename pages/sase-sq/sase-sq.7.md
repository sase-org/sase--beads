# Bead: sase-sq.7 — Glossary migration to a core web

[Bead Pages](../README.md) / [sase-sq](README.md) / sase-sq.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0cb](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0cb.md) · **Assignee:** `sase-sq.7` · **Size:** large
**Created:** 2026-08-24 09:32:18 EDT · **Closed:** 2026-08-24 23:00:59 EDT
**Plan:** [202608/memory\_webs.md](https://github.com/sase-org/sase--plans/blob/main/202608/memory_webs.md)

## Description

glossary: generalize the Rust glossary source wire to file-backed strands, add the one-shot config-to-strand migration, fail closed on dual truth, and migrate the sase and bob-cli glossaries.

## Notes

[2026-08-25T03:01:34Z · sase-sq.7.1.land] LAND VERIFICATION (sase-sq.7.1.land). This phase closed automatically when its child epic sase-sq.7.1 closed; recording what was checked against this phase's own description. Every clause of 'generalize the Rust glossary source wire to file-backed strands, add the one-shot config-to-strand migration, fail closed on dual truth, and migrate the sase and bob-cli glossaries' is satisfied on master df956212b: sase-core declares GLOSSARY_WIRE_SCHEMA_VERSION = 2 with source_path/key_path/keyword_range/body_range plus v1 serde aliases (151a37d, released v0.32.3); sase memory web migrate glossary exists in src/sase/memory/web/migrate.py and cli_migrate.py and refuses a second run; the dual-truth rule is one predicate, glossary_dual_source_diagnostic, consumed by editor_glossary_catalog_for_project, load_project_glossary_terms, and the doctor webs check; this repo carries 39 strands under sase/memory/glossary/ with no memory.glossary in sase/sase.yml, and bob-cli carries 4 on origin/master as 79b5dba, both with byte-identical roster lines. See the full verification and follow-up dispositions in sase-sq.7.1's close note. Leaving epic sase-sq to its own land agent; note that this phase blocks sase-sq.8 (retire the config glossary), which is now unblocked and inherits the docs, package deletion, and skill redeploy that this plan explicitly listed as non-goals.

## Dependencies

- **Depends on:** [sase-sq.5](sase-sq.5.md) ✓ · ⧖ 2026-08-24
- **Blocks:** [sase-sq.8](sase-sq.8.md) ✓ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sq.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-sq.7.md) | [sase-sq.7](sase-sq.7.md) | 0 |
