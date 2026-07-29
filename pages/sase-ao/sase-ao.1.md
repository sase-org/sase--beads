# Bead: sase-ao.1 — Fix the \`@\` alias gate in the prompt-input directive grammar

[Bead Pages](../README.md) / [sase-ao](README.md) / sase-ao.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ao.1` · **Size:** small
**Created:** 2026-07-29 11:46:22 UTC · **Closed:** 2026-07-29 11:54:26 UTC
**Plan:** [202607/model\_alias\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202607/model_alias_completion.md)

## Description

gate: make a leading `@` in a `%model:` value stay in model-argument context instead of being read as an `@effort` suffix, matching the already-correct sase-core grammar.

## Notes

[2026-07-29T11:54:26Z · sase-ao.1] Implemented leading-@ %model alias gate fix. Verified .venv/bin/pytest tests/ace/tui/widgets/test_directive_arg_extraction.py tests/ace/tui/widgets/test_directive_arg_completion.py passed (32 tests). Ran just check: fmt, ruff, mypy, symvision, and toobig passed; SASE validation failed on pre-existing init skills drift and missing SDD plan/prompt links for 202607/model_alias_completion.md.

## Dependencies

- **Blocks:** [sase-ao.3](sase-ao.3.md) ◐
