# Bead: sase-v2.3 — Stop per-tick config-token thread churn and per-key token lookups

[Bead Pages](../README.md) / [sase-v2](README.md) / sase-v2.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0fe](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0fe.md) · **Assignee:** `sase-v2.3` · **Size:** small
**Created:** 2026-08-28 09:01:20 EDT
**Plan:** [202608/tui\_freeze\_regression.md](https://github.com/sase-org/sase--plans/blob/main/202608/tui_freeze_regression.md)

## Description

config_token: move the refresh-thread spawn out of the config-token cache lock, raise the revalidation interval above the tick cadence, and resolve tribe displays once per call instead of once per panel key.

## Dependencies

- **Blocks:** [sase-v2.6](sase-v2.6.md) ◐ · ⧖ 2026-08-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-v2.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-v2.3/README.md) | [sase-v2.3](sase-v2.3.md) | 0 |
