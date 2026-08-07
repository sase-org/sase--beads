# Bead: sase-gt.2 — Move the declared width from 120 to 100 and reflow the repo

[Bead Pages](../README.md) / [sase-gt](README.md) / sase-gt.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.uj](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.uj/README.md) · **Assignee:** `sase-gt.2` · **Size:** medium
**Created:** 2026-08-07 08:37:43 EDT · **Closed:** 2026-08-07 09:30:06 EDT
**Plan:** [202608/prettier\_width\_100.md](https://github.com/sase-org/sase--plans/blob/main/202608/prettier_width_100.md)

## Description

flip: change the single width authority and the package.json mirror from 120 to 100, reflow every prettier-owned Markdown file, regenerate the derived memory shims, agent instruction files, and generated skill sources, and update the doc prose that names 120 explicitly.

## Notes

[2026-08-07T13:29:29Z · sase-gt.2] PROPOSED FOLLOW-UP: extend the prose-width guard test to inline widths — tests/test_markdown_print_width.py only scans module-level constants by name, so it missed the `width=118` and `> 120` literals inside _build_output() in src/sase/main/_init_skills_rendering.py, which this phase had to find via a failing golden instead.

[2026-08-07T13:29:44Z · sase-gt.2] PROPOSED FOLLOW-UP: `sase init skills` cannot run pre-land while src/sase/xprompts/skills/*.md are dirty, so `just check-full` reports init-skills drift for any change that touches skill sources — phase 3 (sase-gt.3) redeploys them at 100 after this lands.

[2026-08-07T13:30:06Z · sase-gt.2] Flipped MARKDOWN_PRINT_WIDTH and package.json prettier.printWidth 120 -> 100; reflowed 150 prettier-owned Markdown files; regenerated memory shims (sase memory init) and confirmed sase memory init --check is clean. Fixed an eighth width site the plan inventory missed: _build_output() in src/sase/main/_init_skills_rendering.py hardcoded 'width=118' and a '> 120' threshold, now derived from MARKDOWN_PRINT_WIDTH. Updated doc prose (docs/axe.md, docs/beads.md x2) and the hardcoded 120 in the 'sase bead show' argparse description (now interpolates DEFAULT_PROSE_WRAP_WIDTH). Made 6 test expectations width-agnostic instead of re-pinning 100 (test_init_skills_sources, test_init_skills_plan, test_init_memory_agent_docs, test_init_memory_formatting, test_init_memory_handler_outputs, test_parser_plan). Verified: full suite 26734 passed / 7 skipped; every lint gate green (fmt-py-check, fmt-md-check, keep-sorted, ruff, mypy, pyscripts, changelog, symvision, toobig, validate-committed-plans); just fmt-md is a fixpoint (twice clean); sase memory init --check and init repo/config/memory --check clean. Known and expected: 'init skills --check' still reports 86 chezmoi provider skill files needing redeploy — sase init skills refuses to deploy while the xprompt sources are uncommitted, so it resolves post-land via sase-gt.3.

[2026-08-07T13:30:50Z · sase-gt.2] Flipped MARKDOWN_PRINT_WIDTH and prettier printWidth to 100; regenerated derived markdown via just fmt-md and sase memory init; derived the hardcoded skill-frontmatter widths in _init_skills_rendering.py from the constant; updated prose in docs/axe.md, docs/beads.md and the sase bead show argparse description; made six width-pinned test expectations width-agnostic. Verified: full suite 26734 passed / 7 skipped, all lint gates green including fmt-md-check, just fmt-md is a fixpoint, sase memory init --check and init config/memory/repo --check clean. init skills --check still reports 86 chezmoi files at 120 by design; sase-gt.3 redeploys them post-land.

## Dependencies

- **Depends on:** [sase-gt.1](sase-gt.1.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-gt.3](sase-gt.3.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gt.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gt.2/README.md) | [sase-gt.2](sase-gt.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`57a045c`](https://github.com/sase-org/sase/commit/57a045cfc6a7f72308d71d0ec66fb1b39f9af13f) | refactor: narrow the declared prose width from 120 to 100 and reflow | [sase-gt.2](sase-gt.2.md) | 2026-08-07 09:31:51 EDT |
