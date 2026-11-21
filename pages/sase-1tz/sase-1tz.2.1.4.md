# Bead: sase-1tz.2.1.4 — Give drain cleanup a budget it can finish and sweep stranded publisher scratch

[Bead Pages](../README.md) / [sase-1tz.2.1](sase-1tz.2.1.md) / sase-1tz.2.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.md) · **Assignee:** `sase-1tz.2.1.4` · **Size:** medium
**Created:** 2026-11-19 11:13:26 EST · **Closed:** 2026-11-19 16:24:53 EST
**Plan:** [202611/noise\_publication\_digests\_tui\_stalls.md](https://github.com/sase-org/sase--plans/blob/main/202611/noise_publication_digests_tui_stalls.md)

## Description

pub_cleanup: the drain reserves a cleanup window inside its timeout and records a verifiable cleanup result. Stale .sase-v2-stage/.sase-v2-backup scratch is swept under the publisher lock. Workspace retention stops treating agents-sync scratch in the machine-wide agents sidecar as a run's stranded work.

## Notes

[2026-11-19T16:46:39Z · sase-1tz.2.1.4] MEASUREMENT 2026-11-19 (read-only; no live repair). Cleanup cap raised 1.0s → 15.0s from athena ledger (payload_clean+cleanup n=1058, p50≈1.60s, p95≈2.10s, max≈11.76s). Live `cleanup_result` is absent on both hosts until this lands.

Athena: 2 stranded dirs under `~/.sase/projects/gh_sase-org__sase/repos/agents/` — `.sase-v2-backup-kyrs0ld1` and `.sase-v2-stage-6nhjyn0l` (both 2026-11-03 10:56). `sase notify list -a -j -l 10000 -q 'agents prompt archive'` = 27 (plan cited 28). Drain ledger 529 rows: no_requests=261 published=267 timeout=1. payload_clean n=529 p50=1.608 p95=2.221 max=10.000; cleanup n=529 p50=1.598 p95=2.024 max=11.762.

Apollo: 0 `.sase-v2-*` dirs. Same notify query = 3. Drain ledger 148 rows: no_requests=71 published=71 timeout=6. payload_clean n=148 p50=1.590 p95=4.555 max=18.443; cleanup n=148 p50=1.564 p95=2.923 max=38.686. The 38s cleanup and 15s “budget exhausted” rows are alarm-fired timeout/no_requests under the old 1s cap; one published payload_clean=18.4s sits inside the 120s work window, not the exception reserve. 15s therefore covers athena max with headroom; apollo exception overruns take the deferred next-pass path.

After-install (maxdepth 3 misses sidecar-root scratch at depth 4):
`find ~/.sase/projects -name '.sase-v2-*'; sase notify list -a -j -l 10000 -q 'agents prompt archive' | python3 -c 'import json,sys;print(len(json.load(sys.stdin)))'`
One-time live sweep of the Nov 3 pair is proposed via `/sase_gate`, not applied here.

[2026-11-19T21:23:43Z · sase-1tz.2.1.4--1] PROPOSED FOLLOW-UP: just check symvision stale_checkout for sase-1tz.2.1.2 axe_error_wire_schema_version/group_errors/normalize_error_signature — local HEAD 179495b93a inherits whitelist rows removed upstream afb07058; unrelated to pub_cleanup, integrate upstream cleanup and rerun

[2026-11-19T21:24:53Z · sase-1tz.2.1.4--1] pub_cleanup landed as c756511c11; 41 targeted tests green (publication_cleanup_policy, publication_scratch, commit_publication_bounded_drain, workspace_retention_agents_scratch, commit_finalizer_git_status); sase_core_rs.default_publication_cleanup_timeout()==15.0; epic-symbols clean; full check red only on unrelated symvision stale_checkout for sase-1tz.2.1.2 whitelist rows (recorded as PROPOSED FOLLOW-UP)

## Dependencies

- **Blocks:** [sase-1tz.2.1.5](sase-1tz.2.1.5.md) ✓ · ⧖ 2026-11-19
- **Blocks:** [sase-1tz.2.1.6](sase-1tz.2.1.6.md) ✓ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2.1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.1.4.md) | [sase-1tz.2.1.4](sase-1tz.2.1.4.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@5ad6013`](https://github.com/sase-org/sase-core/commit/5ad60139499e9149dbc6a1a3db01ec7f088134b0) | feat(publication): raise cleanup timeout to 15s | [sase-1tz.2.1.4](sase-1tz.2.1.4.md) | 2026-11-19 12:50:13 EST |
| sase | [`c756511`](https://github.com/sase-org/sase/commit/c756511c1113809840c79d5dda5d25d41b5c164a) | feat(agents-sync): reserve 15s for publisher drain cleanup | [sase-1tz.2.1.4](sase-1tz.2.1.4.md) | 2026-11-19 12:51:37 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tc.5.1.land][1] | Need causally related active scopes and runner-slot flake duplicate status | 1 |
| read-by | [agent:sase-1tz.2.1.4][2] | Need remaining notes, design path, and children after truncated first read | 4 |
| read-by | [agent:sase-1tz.2.1.5--2][3] | Need cleanup phase intent to determine whether the publication cleanup test failure is a regression | 1 |
| read-by | [agent:sase-1tz.2.1.9][4] | Verify existing phase/task tracking for the clean-base guard and publication cleanup failures | 1 |
| read-by | [agent:sase-1uj.land][5] | Confirm the reserve-cleanup test originated in this phase before routing the flake | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.5.1.land/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.1.4.md
[3]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.1.5.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.9/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1uj.land/README.md

<!-- sase:referenced-by:end -->
