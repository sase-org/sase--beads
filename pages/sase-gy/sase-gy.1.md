# Bead: sase-gy.1 — Runtime-resolved \`markdown.print\_width\` config field

[Bead Pages](../README.md) / [sase-gy](README.md) / sase-gy.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-gt.land.f1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gt.land.f1/README.md) · **Assignee:** `sase-gy.1` · **Size:** medium
**Created:** 2026-08-07 10:25:23 EDT · **Closed:** 2026-08-07 10:54:07 EDT
**Plan:** [202608/configurable\_markdown\_print\_width.md](https://github.com/sase-org/sase--plans/blob/main/202608/configurable_markdown_print_width.md)

## Description

config-field: add the `markdown.print_width` schema/default/getter, turn `sase.markdown_width` into a runtime accessor instead of an import-time constant, migrate every consumer and test off the frozen constants, and extend the width guard suite to catch import-time snapshots. Effective width stays 100, so no Markdown reflows.

## Notes

[2026-08-07T14:54:07Z · sase-gy.1] Added markdown.print_width config field (default 100) to schema + default_config.yml with get_markdown_print_width() fail-open getter floored at MIN_PROSE_WRAP_WIDTH; converted sase.markdown_width to a runtime accessor (DEFAULT_MARKDOWN_PRINT_WIDTH + markdown_print_width()); deleted the frozen constants in markdown_wrap and file_references and migrated notes.py, init_memory/formatting.py, _init_skills_rendering.py, parser_bead_queries.py, parser_plan.py, cli_query.py; extended the width guard suite with import-time-snapshot and parameter-default guards plus a three-way default/schema contract; documented the field in docs/configuration.md. Verified: all 9 'just check' lint gates pass (fmt py+md, keep-sorted, ruff, mypy, pyscripts, changelog, symvision, toobig); just test-scoped 26878 passed / 7 skipped; targeted width/prettier/wrap/parser suites 124 passed. Effective width is unchanged at 100 and fmt-md-check is clean, so no Markdown reflows. The only 'sase validate' failure is init skills --check drift on 5 sase_gate SKILL.md files, confirmed byte-identical on a stashed clean tree and therefore pre-existing and unrelated.

## Dependencies

- **Blocks:** [sase-gy.2](sase-gy.2.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gy.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gy.1/README.md) | [sase-gy.1](sase-gy.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0bea680`](https://github.com/sase-org/sase/commit/0bea6801eace98ffcd0dd839434173d556633bda) | feat(config): add a runtime-resolved markdown.print\_width config field | [sase-gy.1](sase-gy.1.md) | 2026-08-07 10:55:17 EDT |
