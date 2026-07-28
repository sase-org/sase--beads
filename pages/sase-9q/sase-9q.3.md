# Bead: sase-9q.3 — Unified prompt input plan and placeholder substitution

[Bead Pages](../README.md) / [sase-9q](README.md) / sase-9q.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9q.3` · **Size:** small
**Created:** 2026-07-26 10:06:55 UTC
**Plan:** [sase/repos/plans/202607/raw\_placeholder\_inputs.md](https://github.com/sase-org/sase--plans/blob/main/sase/repos/plans/202607/raw_placeholder_inputs.md)

## Description

'Phase plan' section: build the pure-logic PromptInputPlan that merges raw placeholders with declared frontmatter inputs and applies collected values to a prompt.

## Notes

Implemented src/sase/agent/prompt_placeholder_inputs.py with PromptInputPlan/PromptInputValues, body-only raw placeholder scanning, and placeholder substitution before declared-input rendering. Added tests for frontmatter exclusion, mixed placeholder + declared input, literal omission, no-declared Jinja literal values, multi-segment reuse, optional-only no-collection, and PromptInputError propagation. Updated Symvision epic-symbol entries: removed now-used raw placeholder facade allowances and added temporary allowances for the new plan API pending panel/submit consumers. Verification: just install passed; .venv/bin/pytest tests/agent/test_prompt_placeholder_inputs.py passed; just _lint-symvision passed. just check was run and passed lint/SASE validation/committed-plan stages, then failed in the full suite on unrelated tests; rerunning the exact failures showed the non-visual failures passed, retry visual passed, and only tests/ace/tui/visual/test_ace_png_snapshots_agents_families.py::test_renamed_generic_family_root_png_snapshot still has an unrelated neighbor-count PNG mismatch.

## Dependencies

- **Depends on:** [sase-9q.2](sase-9q.2.md) ✓
- **Blocks:** [sase-9q.4](sase-9q.4.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`73269f8`](https://github.com/sase-org/sase/commit/73269f8e47a788be43ec5d2c6f5ebd5768a6b345) | feat: add prompt input plan for raw placeholders (sase-9q.3) | [sase-9q.3](sase-9q.3.md) | 2026-07-26 11:38:49 |
