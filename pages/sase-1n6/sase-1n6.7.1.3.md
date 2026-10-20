# Bead: sase-1n6.7.1.3 — Read core, canary, and escalation evidence

[Bead Pages](../README.md) / [sase-1n6.7.1](sase-1n6.7.1.md) / sase-1n6.7.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1n6.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.7.md) · **Assignee:** `sase-1n6.7.1.3` · **Size:** medium
**Created:** 2026-10-19 19:56:23 EDT · **Closed:** 2026-10-20 00:06:24 EDT
**Plan:** [202610/release\_steward\_observe.md](https://github.com/sase-org/sase--plans/blob/main/202610/release_steward_observe.md)

## Description

health-facts: compose core-ensure, typed core-cut outcomes, scheduled install-canary results, and issue history into the complete per-tick snapshot.

## Notes

[2026-10-20T03:55:21Z · sase-1n6.7.1.3] PROPOSED FOLLOW-UP: Paginated year-long workflow histories exceed the 20s gh timeout live (master-gate returned 234 runs in 7d; full 365d slurp timed out twice via GithubTransport), so _workflow_run_rows/read_runs cannot complete a live tick; transport needs a paging/timeout budget

[2026-10-20T03:55:29Z · sase-1n6.7.1.3] PROPOSED FOLLOW-UP: _required_checks only reads legacy branch protection but sase master uses the active master-integrity ruleset, so the expected check set is always unreadable live and the merge path stays unreachable; needs ruleset-aware expected-check sourcing in the train reader

[2026-10-20T04:06:24Z · sase-1n6.7.1.3] health-facts done: new tools/_release_watch_health.py (core-ensure/core-CI/cuts/canary/issues/access/lineage + collect_health_snapshot), snapshot composition in tools/_release_watch_facts.py collect_snapshot, 37 tests in tests/test_release_watch_health.py incl. real sase_core_rs round trip (nothing_to_release, exit 0). sase tool run check green (f649092a). No epic-symbols. Live read-only probes verified tags/releases/canary/issues/access/jobs/pins. Also fixed 3 latent train-reader integration bugs found live (_git_file base64 wrap, _pages array flatten, repo trailing slash) with regression tests. Index holds intent-to-add entries for the 2 new files (no commit). Follow-ups recorded: paginated year histories exceed 20s transport timeout; ruleset-based expected checks unreadable (master-integrity ruleset, no legacy protection).

## Dependencies

- **Depends on:** [sase-1n6.7.1.1](sase-1n6.7.1.1.md) ✓ · ⧖ 2026-10-19
- **Depends on:** [sase-1n6.7.1.2](sase-1n6.7.1.2.md) ✓ · ⧖ 2026-10-19
- **Blocks:** [sase-1n6.7.1.4](sase-1n6.7.1.4.md) ✓ · ⧖ 2026-10-19
- **Blocks:** [sase-1n6.7.1.5](sase-1n6.7.1.5.md) ✓ · ⧖ 2026-10-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n6.7.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.7.1.3/README.md) | [sase-1n6.7.1.3](sase-1n6.7.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`112a5f4`](https://github.com/sase-org/sase/commit/112a5f47576af6ab294354339873e15047fe5156) | feat(release-watch): add health reader, snapshot composition, and tests | [sase-1n6.7.1.3](sase-1n6.7.1.3.md) | 2026-10-20 00:07:49 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1n6.7.1.3][1] | Need phase scope, parent decisions and design | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.7.1.3/README.md

<!-- sase:referenced-by:end -->
