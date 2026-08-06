# Bead: sase-fr.9.2 — Adopt the release and prove close history end to end

[Bead Pages](../README.md) / [sase-fr.9](sase-fr.9.md) / sase-fr.9.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-fr.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fr.land/README.md) · **Assignee:** `sase-fr.9.2` · **Size:** small
**Created:** 2026-08-06 00:19:33 EDT · **Closed:** 2026-08-06 07:15:32 EDT
**Plan:** [202608/close\_history\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/close_history_landing.md)

## Previously Closed

> ↺ Closed 2026-08-06T10:55:21Z · done
>
> (none)
>
> Reopened 2026-08-06T11:00:51Z by `sase bead open`

## Description

adopt: raise the sase-core-rs window to the release from core-search, refresh uv.lock and the declared-minimum assertion, replace the end-to-end test's skip guard with a hard assertion, and add real CLI coverage for searching an archived close reason and for the history entry a reopen writes.

## Notes

[2026-08-06T11:01:07Z · sase-fr.9.3] LAND VERIFICATION (sase-fr.9.3, discrepancy found): reopened this bead — it was marked CLOSED but its described work was never committed to master. pyproject.toml still pinned sase-core-rs>=0.18.2,<0.19.0, tests/test_sase_core_rs_telemetry_smoke_tool.py still asserted the declared minimum as 0.18.2, tests/test_bead/test_close_history_end_to_end.py still carried the pytest.skip guard, and no CLI-level search/history coverage existed. Verified via git log --all (no matching commit), git log -p on pyproject.toml (no bump past 0.18.2), and gh pr list --repo sase-org/sase (no merged PR touching sase-core-rs floor since PR #86 merged in sase-core). Completing the adopt work now as part of sase-fr.9.3's land verification since the epic cannot be honestly closed without it.

[2026-08-06T11:15:32Z · sase-fr.9.3] Adopt work verified complete during sase-fr.9.3's land pass: pyproject.toml raised to sase-core-rs>=0.18.3,<0.19.0 (the published PyPI release carrying the close_history reducer + search fix from sase-fr.9.1's core-search phase), uv.lock refreshed, and the declared-minimum assertion in tests/test_sase_core_rs_telemetry_smoke_tool.py updated to 0.18.3. tests/test_bead/test_close_history_end_to_end.py's pytest.skip guard removed; it now asserts against the real installed reducer and passes. Added tests/test_bead/test_close_history_cli_integration.py with real-BeadProject CLI coverage: 'sase bead search' finds an archived close reason with close_history in matched_fields, and 'sase bead history' reports the close_history field transition. All 6 targeted tests pass with sase-core-rs 0.18.3 installed from PyPI (not a local dev build). Manually verified live (scratch bead store): 'sase bead show' renders the [↺1] badge and PREVIOUSLY CLOSED section, and --format json carries both close_history and reopened_bead. just check (all lint gates + scoped tests) is green.

## Dependencies

- **Depends on:** [sase-fr.9.1](sase-fr.9.1.md) ✓ · ⧖ 2026-08-06
- **Blocks:** [sase-fr.9.3](sase-fr.9.3.md) ✓ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fr.9.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-fr.9.2.md) | [sase-fr.9.2](sase-fr.9.2.md) | 0 |
