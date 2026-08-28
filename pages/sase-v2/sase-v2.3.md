# Bead: sase-v2.3 — Stop per-tick config-token thread churn and per-key token lookups

[Bead Pages](../README.md) / [sase-v2](README.md) / sase-v2.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0fe](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0fe.md) · **Assignee:** `sase-v2.3` · **Size:** small
**Created:** 2026-08-28 09:01:20 EDT · **Closed:** 2026-08-28 10:06:24 EDT
**Plan:** [202608/tui\_freeze\_regression.md](https://github.com/sase-org/sase--plans/blob/main/202608/tui_freeze_regression.md)

## Description

config_token: move the refresh-thread spawn out of the config-token cache lock, raise the revalidation interval above the tick cadence, and resolve tribe displays once per call instead of once per panel key.

## Notes

[2026-08-28T14:06:24Z · sase-v2.3] Verified .venv/bin/pytest tests/test_config_cache_token.py tests/ace/tui/models/test_tribe_display.py tests/ace/tui/test_agent_panel_collapse_isolation.py::test_panel_switch_skips_config_collapsed_panel; sase bead epic-symbols sase-v2.3 reported no entries; just check passed.

## Dependencies

- **Blocks:** [sase-v2.6](sase-v2.6.md) ◐ · ⧖ 2026-08-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-v2.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-v2.3/README.md) | [sase-v2.3](sase-v2.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9415b82`](https://github.com/sase-org/sase/commit/9415b82af119de673bcc47c9ee19e8464c098d61) | fix(config): reduce config token refresh churn | [sase-v2.3](sase-v2.3.md) | 2026-08-28 10:07:44 EDT |
