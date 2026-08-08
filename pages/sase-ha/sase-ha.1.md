# Bead: sase-ha.1 — Channel-versioned agent-CLI detection and update

[Bead Pages](../README.md) / [sase-ha](README.md) / sase-ha.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ve](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ve/README.md) · **Assignee:** `sase-ha.1` · **Size:** medium
**Created:** 2026-08-07 20:45:36 EDT · **Closed:** 2026-08-07 21:08:03 EDT
**Plan:** [202608/muse\_provider.md](https://github.com/sase-org/sase--plans/blob/main/202608/muse_provider.md)

## Description

cli_meta: teach agent-CLI detection, latest-version resolution, and update planning about CLIs distributed by a version channel instead of npm — a JSON-endpoint latest oracle, an exact version comparator, env-carrying self-update commands, and the `script` install manager.

## Notes

[2026-08-08T01:07:39Z · sase-ha.1] PROPOSED FOLLOW-UP: tests/test_gate_cli_show.py (4 tests) and tests/gate_conformance legacy_shared_input (cli+ace) fail on a clean master checkout at a1cc172d3 — verified via git stash, unrelated to sase-ha.1; likely fallout from "feat(notification-gates): surface declared and submitted gate input"

[2026-08-08T01:08:03Z · sase-ha.1] cli_meta implemented: LatestQuery record + HTTPS JSON-endpoint oracle (_fetch_url_latest_version) sharing one TTL cache (SCHEMA_VERSION 2, npm:/url: keys); InstallMethod.SCRIPT + install_manager/install_script_url/install_env/self_update_env/latest_version_url/latest_version_json_field/version_compare on AgentCliStatus; VersionCompare.EXACT comparator selected in collect_agent_cli_statuses (fixes is_newer returning False for 0.1.0-R709 vs 0.1.0-R708.1); run_command env_overlay threaded plan -> execute -> dry-run/JSON preview (and through both ACE task_runner closures); script install hint in detect and doctor setup_hint; new install-metadata keys passed through _registry_metadata and documented on the hookspec. Added 20 tests (latest URL oracle success/malformed/missing-field/non-HTTPS/offline/stale-cache/registry_unavailable, comparator selection incl. the PEP 440 regression, query selection + json field, env threading with a clean re-probe, script hints, registry normalization, runner overlay, CLI env display); no network in tests. just check: all lint gates green, scoped suite 27320 passed with 6 failures (test_gate_cli_show x4, gate_conformance legacy_shared_input x2) reproduced on a clean master stash and noted as pre-existing.

## Dependencies

- **Blocks:** [sase-ha.3](sase-ha.3.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ha.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ha.1/README.md) | [sase-ha.1](sase-ha.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`47b9f00`](https://github.com/sase-org/sase/commit/47b9f0017075f3efd54f8d5098abf77dbd39a2a5) | feat(agent-clis): support channel-versioned agent CLIs | [sase-ha.1](sase-ha.1.md) | 2026-08-07 21:09:24 EDT |
