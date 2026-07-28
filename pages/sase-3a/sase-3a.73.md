# Bead: sase-3a.73 — Remediate pyvision symbol: query\_wire\_to\_json\_dict

[Bead Pages](../README.md) / [sase-3a](README.md) / sase-3a.73

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-05-13 02:17:06 UTC
**Plan:** [sdd/plans/202605/pyvision\_test\_only\_public\_symbols\_cleanup.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202605/pyvision_test_only_public_symbols_cleanup.md)

## Description

The `query_wire_to_json_dict` symbol is either public when it is referenced but only in the file that it is defined (make the symbol private by adding a `_` prefix--note that usage with `__all__` does not count as a reference), public because it is referenced by external repos (add a `# pyvision: ` pragma that references an external repo), or unused (remove the symbol completely--do not forget to remove test references too). Can you help me analyze this symbol and perform the appropriate action / file change?

IMPORTANT: Make sure to run the `just pyvision` command after you have removed the corresponding `--epic-symbol` line in the Justfile.

## Notes

Privatized query_wire_to_json_dict as _query_wire_to_json_dict; updated export list and tests in test_core_query_golden_wire.py and _query_golden_corpus.py; removed Justfile epic-symbol entry; 
┌───────────────────────────────────────────────────────┐
│                RUNNING: just pyvision                 │
└───────────────────────────────────────────────────────┘ still reports unrelated private-function scope violations.

## Dependencies

- **Depends on:** [sase-3a.70](sase-3a.70.md) ✓
- **Blocks:** [sase-3a.76](sase-3a.76.md) ✓
