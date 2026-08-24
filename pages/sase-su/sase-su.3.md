# Bead: sase-su.3 — Automatic drain on a usage-limit disable

[Bead Pages](../README.md) / [sase-su](README.md) / sase-su.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ce](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ce.md) · **Assignee:** `sase-su.3` · **Size:** medium
**Created:** 2026-08-24 10:29:14 EDT · **Closed:** 2026-08-24 13:16:30 EDT
**Plan:** [202608/provider\_drain.md](https://github.com/sase-org/sase--plans/blob/main/202608/provider_drain.md)

## Description

auto: gate the feature behind a beta flag, submit a drain proc when a usage-limit disable wins its first-writer window, and make that drain own the single enriched usage-limit notification.

## Notes

[2026-08-24T17:16:03Z · sase-su.3] PROPOSED FOLLOW-UP: tests/test_launch_proc_runtime.py (7 tests) and tests/test_direct_typed_launch.py::test_isolated_direct_bash_proc_settles_without_agent fail on this workspace with "proc supervisor died without acknowledging startup; command was not run" / a launched-count mismatch. Reproduces identically on a clean master checkout (git stash verified) and is unrelated to the provider-drain work in this epic, so it looks like environment flakiness (heavy concurrent agent load on this machine) rather than a code defect — but worth a flake/ci triage since it reproduced twice in a row.

[2026-08-24T17:16:30Z · sase-su.3] Gated automatic provider drain behind new beta flag provider_drain (bead sase-sx). Added llm_provider.usage_limit.relaunch/relaunch_limit config (default_config.yml, sase.schema.json, docs/configuration.md, docs/llms.md bullets). usage_limit_disable.py now submits a durable 'sase agent drain' proc (via sase.procs.submit_proc_request, operation=agent.drain) instead of notifying inline when the flag is on, relaunch is enabled, and the disable is hard; falls back to inline notify if submission raises or preconditions aren't met. sase agent drain's ops-layer dispatcher (_run_drain) now loads the operation request payload, settles the trigger agent via a bounded 60s wait_watch poll before planning, and owns sending the one enriched usage-limit notification (new _agent_drain_notify.py module) built from the same JSON envelope the CLI reports; notify_provider_usage_limit_disabled() gained an optional drain_notes param rendered by _drain_render.usage_limit_drain_report_notes(). Verified: just install; just check (all lint gates green, including symvision after removing 2 pre-existing stale --epic-symbol entries from a closed epic plus one my own change made stale); ruff/mypy clean; the full scoped test suite passed except 8 pre-existing failures in test_launch_proc_runtime.py/test_direct_typed_launch.py that reproduce identically on a clean master checkout (unrelated environment flake, noted as PROPOSED FOLLOW-UP); targeted re-run of every new/changed test file (106 tests) passed cleanly.

## Dependencies

- **Depends on:** [sase-su.2](sase-su.2.md) ✓ · ⧖ 2026-08-24
- **Blocks:** [sase-su.5](sase-su.5.md) ◐ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-su.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-su.3/README.md) | [sase-su.3](sase-su.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d06d268`](https://github.com/sase-org/sase/commit/d06d268ea6a49822adbe4bebd81518690c667431) | feat(llm): auto-drain a hard-disabled provider on a usage-limit trip | [sase-su.3](sase-su.3.md) | 2026-08-24 13:17:49 EDT |
