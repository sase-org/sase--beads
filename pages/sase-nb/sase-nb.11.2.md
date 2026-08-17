# Bead: sase-nb.11.2 — Stop the feature-flag checker tests leaking sys.path

[Bead Pages](../README.md) / [sase-nb.11](sase-nb.11.md) / sase-nb.11.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-nb.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-nb.land.md) · **Assignee:** `sase-nb.11.2` · **Size:** small
**Created:** 2026-08-16 21:04:25 EDT · **Closed:** 2026-08-16 21:24:11 EDT
**Plan:** [202608/feature\_flags\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/feature_flags_landing.md)

## Description

test: restore sys.path around every tools/check_feature_flags import so the blocking global-state leak gate stops reporting 25 poisoning changes.

## Notes

[2026-08-17T01:24:11Z · sase-nb.11.2] Fixed the sys.path leak by adding an autouse monkeypatch.syspath_prepend fixture in tests/test_check_feature_flags_tool.py, per the plan's leak phase. Verified: (1) .venv/bin/python -m pytest -q -p tests._global_state_leak_detector --sase-detect-global-leaks --sase-fail-on-global-leaks tests/test_check_feature_flags_tool.py -p no:randomly now passes 26/26 with 0 poisoning changes (was 25); (2) .venv/bin/python tools/check_feature_flags still runs standalone from a clean shell, exit 0; (3) just check passed clean (all lint gates + scoped test lane, exit 0).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-nb.11.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-nb.11.2/README.md) | [sase-nb.11.2](sase-nb.11.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8873e64`](https://github.com/sase-org/sase/commit/8873e64c451cf24368c278f3faf9dc92c9349317) | test: restore sys.path around every check\_feature\_flags tool load | [sase-nb.11.2](sase-nb.11.2.md) | 2026-08-16 21:25:01 EDT |
