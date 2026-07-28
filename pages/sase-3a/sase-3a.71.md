# Bead: sase-3a.71 — Remediate pyvision symbol: provider\_style\_for

[Bead Pages](../README.md) / [sase-3a](README.md) / sase-3a.71

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-05-13 02:16:52 UTC
**Plan:** [sdd/plans/202605/pyvision\_test\_only\_public\_symbols\_cleanup.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202605/pyvision_test_only_public_symbols_cleanup.md)

## Description

The `provider_style_for` symbol is either public when it is referenced but only in the file that it is defined (make the symbol private by adding a `_` prefix--note that usage with `__all__` does not count as a reference), public because it is referenced by external repos (add a `# pyvision: ` pragma that references an external repo), or unused (remove the symbol completely--do not forget to remove test references too). Can you help me analyze this symbol and perform the appropriate action / file change?

IMPORTANT: Make sure to run the `just pyvision` command after you have removed the corresponding `--epic-symbol` line in the Justfile.

## Notes

Privatized provider_style_for as _provider_style_for; updated in-module and tests in test_model_picker_modal.py; removed Justfile epic-symbol entry; 
┌───────────────────────────────────────────────────────┐
│                RUNNING: just pyvision                 │
└───────────────────────────────────────────────────────┘ now fails on unrelated existing private-symbol scope violations in agent_launch_facade, run_agent_helpers, directives, tui_activity, bead_mutation_facade, and git_query_facade.

## Dependencies

- **Depends on:** [sase-3a.68](sase-3a.68.md) ✓
- **Blocks:** [sase-3a.74](sase-3a.74.md) ✓
