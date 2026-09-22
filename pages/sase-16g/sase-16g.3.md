# Bead: sase-16g.3 — Last-known-good config keeps the host supervising

[Bead Pages](../README.md) / [sase-16g](README.md) / sase-16g.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pe](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pe.md) · **Assignee:** `sase-16g.3` · **Size:** medium
**Created:** 2026-09-22 12:59:09 EDT · **Closed:** 2026-09-22 14:56:02 EDT
**Plan:** [202609/services\_p0\_supervision.md](https://github.com/sase-org/sase--plans/blob/main/202609/services_p0_supervision.md)

## Description

config: keep the last composition that loaded, observe exits and stop children without reloading config, and publish the config error through the heartbeat and the status snapshot instead of going silently stale.

## Notes

[2026-09-22T18:56:02Z · sase-16g.3] Last-known-good config keeps the host supervising: _reconcile_once isolates config load, continues on _last_good_config with _config_error published via heartbeat and status host.error; _settle_exit/_observe_exits accept None composition (falls back to running.entry); _stop_child takes caller-held config/state without reloading and _stop_all_children isolates per-child errors; write_current_host_status never reloads a passed composition, prefers last-good, and synthesizes an empty composition for degraded startup. 3 new scenario tests pass; full tests/service (187) green; ruff+mypy clean. just check's remaining symvision flag (agent_env_refusal_reason in platform.py) pre-exists on clean HEAD from the env commit and is outside this phase.

## Dependencies

- **Depends on:** [sase-16g.2](sase-16g.2.md) ✓ · ⧖ 2026-09-22
- **Blocks:** [sase-16g.4](sase-16g.4.md) ◐ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16g.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16g.3/README.md) | [sase-16g.3](sase-16g.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5374c03`](https://github.com/sase-org/sase/commit/5374c03ab7b55c3843feef112df9c407495d941a) | feat(service): last-known-good config keeps the host supervising | [sase-16g.3](sase-16g.3.md) | 2026-09-22 14:59:40 EDT |
