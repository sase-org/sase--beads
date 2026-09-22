# Bead: sase-165.5 — Dev extension rebuilds when linked sase-core source changes

[Bead Pages](../README.md) / [sase-165](README.md) / sase-165.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0p2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0p2.md) · **Assignee:** `sase-165.5` · **Size:** medium
**Created:** 2026-09-22 08:18:26 EDT · **Closed:** 2026-09-22 09:52:41 EDT
**Plan:** [202609/sase\_core\_p0\_agent\_maintainability.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_core_p0_agent_maintainability.md)

## Description

extension-freshness: rust-install stamps the source identity (HEAD plus a dirty digest) it built from. validate_test_environment compares it with the linked checkout and flags a rebuild through a new status bit and fingerprint bucket, _setup rebuilds on that bit, and the stale-extension flake-baseline entry is retired.

## Notes

[2026-09-22T13:33:00Z · sase-165.5] Design note: _setup-visual and _setup-terminal-smoke need no bit-32 handling — they invoke validate without --check-core (group-only), so bits 2/32 can never be set there; they run after _setup which already rebuilt. Only _setup handles bits 2+32.

[2026-09-22T13:51:56Z · sase-165.5] PROPOSED FOLLOW-UP: just check escalated to full suite with 15 failures in files this phase never touched (test_commit_bead_hooks x3, test_cli_at_path_values, test_usage_config x4, plugins_browser_pane_install, test_shards drift, fakey monitor capacity, epic panel frames, launch proc runtime, session reporter, ace testing leaks) — triage as pre-existing/infra debt

[2026-09-22T13:52:41Z · sase-165.5] Extension freshness done and verified: rust-install stamps source identity to .venv/.sase-core-rs-source.json (shared helper tools/_sase_core_source_identity.py, also feeds wheel-cache INPUT_PATHS); validate gains CORE_SOURCE_STALE=32 plus core-source fingerprint bucket (not escalating, schema untouched); _setup rebuilds on bit 32 with reason line; flake-baseline node retired via fixed-at 2026-09-22T13:25:12Z; docs sentence added. Verified: 6 new validator tests + full file (18) pass, wheel-cache (5) + selection suites (41) pass, lint ruff/mypy/symvision pass, live probe exit 34 pre-rebuild then 0 post-rebuild with stamp matching HEAD 231b5e5. just check escalated to full suite: 44701 passed, 15 failures all in untouched files recorded as PROPOSED FOLLOW-UP.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-165.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-165.5/README.md) | [sase-165.5](sase-165.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e8d2386`](https://github.com/sase-org/sase/commit/e8d238688ff9b75edec510d3a8b56aec9e6c77d9) | feat(dev): rebuild extension when linked sase-core source changes | [sase-165.5](sase-165.5.md) | 2026-09-22 09:54:45 EDT |
