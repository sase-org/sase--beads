# Bead: sase-8v.3 — Identity-relative local persistence and registry compatibility

[Bead Pages](../README.md) / [sase-8v](README.md) / sase-8v.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `athena.sase-8v.3` · **Size:** large
**Created:** 2026-07-23 16:59:06 UTC
**Plan:** [202607/global\_agent\_hoods.md](https://github.com/sase-org/sase--plans/blob/main/202607/global_agent_hoods.md)

## Description

Stop adding the current machine hood to locally owned records, preserve explicit imported provenance, and keep legacy qualified records resolvable without mass-renaming history.

## Notes

COMMIT: 5bf430b67

FOLLOW-UP FIX (launch-blocking regression): local_entry_provenance() aborted the ENTIRE name-registry rebuild when a legacy artifact/dismissed-bundle name could not be globalized (e.g. '4x--epic.f-0', a fanout child of a family member). Because rebuild_name_registry() runs on every launch (via get_reserved_agent_names), ALL agent launches failed with 'ValueError: invalid family name ... expected a solo name or one terminal --<role> suffix'. Fix: compute canonical_global_name best-effort in src/sase/agent/names/_registry_entries.py, falling back to None for un-globalizable names (source_owner still recorded). This upholds this phase's 'keep legacy qualified records resolvable without mass-renaming history' goal. Regression test: tests/test_agent_name_registry.py::test_registry_rebuild_survives_un_globalizable_legacy_name.

## Dependencies

- **Depends on:** [sase-8v.1](sase-8v.1.md) ✓
- **Blocks:** [sase-8v.10](sase-8v.10.md) ✓
- **Depends on:** [sase-8v.2](sase-8v.2.md) ✓
- **Blocks:** [sase-8v.4](sase-8v.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-8v.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-8v.3/README.md) | [sase-8v.3](sase-8v.3.md) | 1 |
| [bbugyi200.athena.sase-8v.3--code](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-8v.3.md#member-code) | [sase-8v.3](sase-8v.3.md) | 0 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`5bf430b`](https://github.com/sase-org/sase/commit/5bf430b67eb42f61e5472f689e0cba4a0d276669) | feat(agent): persist local names relative to owner (sase-8v.3) | [sase-8v.3](sase-8v.3.md) | 2026-07-23 19:56:11 |
