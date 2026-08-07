# Bead: sase-gy.2 — Flip the shipped default from 100 to 88

[Bead Pages](../README.md) / [sase-gy](README.md) / sase-gy.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-gt.land.f1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gt.land.f1/README.md) · **Assignee:** `sase-gy.2` · **Size:** medium
**Created:** 2026-08-07 10:25:49 EDT · **Closed:** 2026-08-07 11:47:33 EDT
**Plan:** [202608/configurable\_markdown\_print\_width.md](https://github.com/sase-org/sase--plans/blob/main/202608/configurable_markdown_print_width.md)

## Description

default-88: change the default constant, `default_config.yml`, the schema default, and the `package.json` prettier mirror to 88, then reflow the repo's Markdown, regenerate every SASE-generated artifact, and correct the prose and tables that name 100 as the width.

## Notes

[2026-08-07T15:46:51Z · sase-gy.2] PROPOSED FOLLOW-UP: tests/ace/tui/util/test_stall_watchdog.py::test_watchdog_keeps_hitch_and_stall_state_machines_independent is load-flaky — it failed once during a full `just test` run under heavy parallel load and passes reliably in isolation; the timing thresholds should be made load-tolerant.

[2026-08-07T15:47:33Z · sase-gy.2] Flipped the shipped Markdown prose width default from 100 to 88 in all four declarations (DEFAULT_MARKDOWN_PRINT_WIDTH, default_config.yml, sase.schema.json default, package.json prettier printWidth); reflowed 140 repo Markdown files via just fmt-md; regenerated SASE artifacts with sase memory init to a fixpoint; corrected prose/tables in docs/axe.md, docs/beads.md, docs/configuration.md to name markdown.print_width (88) instead of a bare 100. Verified: full 'just test' suite (26916 passed) after fixing 5 wrap-sensitive assertions in tests/test_sdd_file_writes.py, tests/main/test_init_memory_handler_repo_access.py, and tests/main/test_init_skills_sources.py to compare whitespace-collapsed text; all 'just check' lint gates green (fmt-py, fmt-md, keep-sorted, ruff, mypy, pyscripts, changelog, symvision, toobig). Known/out-of-scope: 'sase validate' still fails on 'init memory --check' and 'init skills --check' drift, but every reported file lives under ~/.local/share/chezmoi/home/ (chezmoi repo), which phase sase-gy.3 aligns; no in-repo generated artifact is stale.

## Dependencies

- **Depends on:** [sase-gy.1](sase-gy.1.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-gy.3](sase-gy.3.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gy.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gy.2/README.md) | [sase-gy.2](sase-gy.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`86c9b31`](https://github.com/sase-org/sase/commit/86c9b3181e8b959b7fa58c373ef0684be43897d1) | feat(markdown)!: default the Markdown prose width to 88 | [sase-gy.2](sase-gy.2.md) | 2026-08-07 11:49:23 EDT |
