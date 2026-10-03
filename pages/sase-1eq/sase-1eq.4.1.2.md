# Bead: sase-1eq.4.1.2 — Canonical config and local macro frontmatter

[Bead Pages](../README.md) / [sase-1eq.4.1](sase-1eq.4.1.md) / sase-1eq.4.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.4.md) · **Assignee:** `sase-1eq.4.1.2` · **Size:** medium
**Created:** 2026-10-03 05:59:59 EDT · **Closed:** 2026-10-03 08:44:04 EDT
**Plan:** [202610/macro\_syntax\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202610/macro_syntax_cutover.md)

## Description

config-frontmatter: normalize each authored layer before merging, migrate schemas and consumers to macro keys, update local helper parsing and canonical writers, and test collisions and flag-off errors.

## Notes

[2026-10-03T12:43:07Z · sase-1eq.4.1.2--1] PROPOSED FOLLOW-UP: test_dev_extension_exposes_every_collected_name fails identically on clean base (SHA 3c1f5c313e): installed sase_core_rs lacks plan_publication_payload_batches binding required by src/sase/core/publication_payload_facade.py; focused repro: pytest tests/test_check_sase_core_rs_bindings_tool.py::test_dev_extension_exposes_every_collected_name

[2026-10-03T12:43:19Z · sase-1eq.4.1.2--1] PROPOSED FOLLOW-UP: symvision unused PublicationPayloadFile/plan_publication_payload_batches in src/sase/core/publication_payload_facade.py reproduces on clean base; triage witness 06ecb699efedf8d4d1b407d10ddb83dd tracks as KNOWN

[2026-10-03T12:44:04Z · sase-1eq.4.1.2--1] config-frontmatter done: per-layer normalization, canonical schema/writers, frontmatter gating, collision/flag-off errors. Fixed monitor NEW failures: TUI frontmatter panel canonical-macros alias (fixes RepresenterError crashes), updated stale canonical-output expectations to macros/macro_aliases (alias, unresolved, schema, config-insert, save, stack, stash). Verified: 205 TUI+alias focused tests pass, 84 alias/schema/insert/markdown pass, 106 phase/schema/save/terminology pass, ruff+mypy clean, epic-symbols clean. Remaining just-check failures reproduce on clean base SHA 3c1f5c313e (missing plan_publication_payload_batches binding, symvision KNOWN witness 06ecb699) recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-1eq.4.1.1](sase-1eq.4.1.1.md) ✓ · ⧖ 2026-10-03
- **Blocks:** [sase-1eq.4.1.3](sase-1eq.4.1.3.md) ✓ · ⧖ 2026-10-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.4.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.4.1.2.md) | [sase-1eq.4.1.2](sase-1eq.4.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6eaa8df`](https://github.com/sase-org/sase/commit/6eaa8df521cc3b336278e2439b1cb49dafb8364a) | feat!: canonical config and local macro frontmatter (sase-1eq.4.1.2) | [sase-1eq.4.1.2](sase-1eq.4.1.2.md) | 2026-10-03 08:45:40 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.4.1.2--1][1] | Need phase notes for handoff | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.4.1.2.md

<!-- sase:referenced-by:end -->
