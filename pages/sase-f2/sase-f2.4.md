# Bead: sase-f2.4 — Launch-time provenance capture removal

[Bead Pages](../README.md) / [sase-f2](README.md) / sase-f2.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ej.land.w2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ej.land.w2/README.md) · **Assignee:** `sase-f2.4` · **Size:** small
**Created:** 2026-08-03 14:48:41 EDT · **Closed:** 2026-08-03 16:20:28 EDT
**Plan:** [202608/revert\_stored\_prompt\_duality.md](https://github.com/sase-org/sase--plans/blob/main/202608/revert_stored_prompt_duality.md)

## Description

provenance: stop writing `xprompt_sources.json` at launch, reduce the source-collection and hosted-URL modules to exactly the definition-resolution surface `sase xprompt show` calls, and delete the record loading and link rewriting helpers that only the reverted stores used.

## Notes

[2026-08-03T20:20:28Z · sase-f2.4] Removed launch-time xprompt_sources.json capture (run_agent_runner_setup.py preprocess_prompt_xprompts no longer imports/calls write_xprompt_sources). Reduced xprompt/xprompt_sources.py to the collection surface sase xprompt show needs: renamed _collect_xprompt_sources -> public collect_xprompt_sources, deleted write_xprompt_sources and the now-unused json/os imports and _resolve_definition_line/_definition_file_for_source aliases, updated __all__ and docstrings. Updated the single call site in cli_show_resolve.py to use collect_xprompt_sources. Confirmed xprompt_links.py already had load_xprompt_source_records/rewrite_xprompt_source_links removed by the prior surfaces phase (sase-f2.3) and no require_rust_binding("prompt_xprompt_...") call sites remain anywhere in src/sase; reworded its module/class docstrings to drop launch-capture language. Reworked tests/test_xprompt_sources.py around the collector (dropped the JSON-artifact-serialization case), removed the provenance cases from tests/test_run_agent_runner_setup.py (including test_preprocess_prompt_xprompts_survives_provenance_failure), confirmed tests/test_xprompt_links.py and tests/xprompt/test_cli_show_resolve.py needed no further trimming. just install + just check green (fmt, ruff, mypy, pyscripts, changelog, symvision, toobig, SASE validation, committed plans, full test suite - one PNG visual snapshot failure on the first run was unrelated flaky sandbox contention, confirmed by a clean second just check run and isolated rerun). Verified by hand: sase xprompt show plan --format json and sase xprompt show bob_query --format json both still print correct hosted definition URLs (project-defined -> github.com/sase-org/sase, chezmoi-defined -> github.com/bbugyi200/dotfiles).

## Dependencies

- **Depends on:** [sase-f2.1](sase-f2.1.md) ✓
- **Depends on:** [sase-f2.2](sase-f2.2.md) ✓
- **Depends on:** [sase-f2.3](sase-f2.3.md) ✓
- **Blocks:** [sase-f2.5](sase-f2.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-f2.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-f2.4/README.md) | [sase-f2.4](sase-f2.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1a2040e`](https://github.com/sase-org/sase/commit/1a2040e73d351ec7c1c280bdc4c4d16dbda10f7e) | feat(xprompt)!: stop writing launch-time provenance JSON | [sase-f2.4](sase-f2.4.md) | 2026-08-03 16:21:16 EDT |
