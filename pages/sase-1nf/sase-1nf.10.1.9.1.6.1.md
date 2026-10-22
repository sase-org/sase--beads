# Bead: sase-1nf.10.1.9.1.6.1 — Remove the quadratic name scan and the cached-snapshot digest regression

[Bead Pages](../README.md) / [sase-1nf.10.1.9.1.6](sase-1nf.10.1.9.1.6.md) / sase-1nf.10.1.9.1.6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nf.10.1.9.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.10.1.9.1.land.md) · **Assignee:** `sase-1nf.10.1.9.1.6.1` · **Size:** medium
**Created:** 2026-10-21 10:45:30 EDT · **Closed:** 2026-10-21 11:17:55 EDT
**Plan:** [202610/publication\_blockers\_acceptance.md](https://github.com/sase-org/sase--plans/blob/main/202610/publication_blockers_acceptance.md)

## Description

drain-bound: compute reserved agent-session names once per registry snapshot during inventory builds, digest reused validation snapshots by their on-disk bytes, add regressions, and measure scoped drains on athena.

## Notes

[2026-10-21T15:17:35Z · sase-1nf.10.1.9.1.6.1] PROPOSED FOLLOW-UP: tests/ace/tui/test_app_import_budget.py fails on clean master (3529 modules vs 3527 cap), unrelated to drain-bound; bump cap or defer new edges

[2026-10-21T15:17:46Z · sase-1nf.10.1.9.1.6.1] drain-bound evidence: post-fix scoped profiles on athena 🔒 profile-one-hood.json 🔒 profile-two-hood.json. One hood (sase-1nf): inventory 23.19s, planning 7.16s, 25 git ops, 0 digest mismatches (baseline inventory 106-148s production / 268.5s cProfile). Two hoods (sase-1nf,12r): inventory 22.64s, planning 5.93s, 26 git ops, 0 digest mismatches. cProfile of scoped build: historical_associations 3.38s total (was ~229s of scan), top costs now index queries + dismissed bundles (legit I/O). src: load_validated_publication verifies reused snapshots against on-disk bytes; _cached_previous_snapshot falls back to on-disk bytes for non-canonical snapshots; historical_associations builds the reserved agent-session set once per build and passes it to sase_agent_ref_for_name. Regressions: test_targeted_reuses_non_canonical_foreign_snapshot, test_targeted_rejects_tampered_cached_snapshot, test_historical_associations_builds_reserved_set_once (all fail pre-fix, pass post-fix). sase tool run check bb4ae891e78a6aa721610040eecb136e: all lint gates pass, 57179 tests pass; only failure is the pre-existing TUI import-budget cap recorded as PROPOSED FOLLOW-UP.

[2026-10-21T15:17:55Z · sase-1nf.10.1.9.1.6.1] drain-bound done and verified: quadratic reserved-name scan removed (one set per inventory build; scoped inventory 110s to 23s, total drain ~30s vs 120s bound), cached-snapshot digest now verifies on-disk bytes (multi-hood transactions pass, tampering fails closed). 3 new regressions fail pre-fix/pass post-fix; focused files 18/18 pass; sase tool run check clean except pre-existing TUI import-budget failure reproduced on base (PROPOSED FOLLOW-UP recorded). No epic-symbol leftovers.

## Attachments

- 🔒 profile-one-hood.json · application/json · 745 bytes (private attachment)
- 🔒 profile-two-hood.json · application/json · 775 bytes (private attachment)

## Dependencies

- **Blocks:** [sase-1nf.10.1.9.1.6.3](sase-1nf.10.1.9.1.6.3.md) ✓ · ⧖ 2026-10-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.10.1.9.1.6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.9.1.6.1/README.md) | [sase-1nf.10.1.9.1.6.1](sase-1nf.10.1.9.1.6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`54779b6`](https://github.com/sase-org/sase/commit/54779b62f57805fbec295240f4de7201c87a4376) | perf(agents-sync): fix quadratic reserved-session scan and snapshot digest regression | [sase-1nf.10.1.9.1.6.1](sase-1nf.10.1.9.1.6.1.md) | 2026-10-21 11:19:30 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nf.10.1.9.1.6.1][1] | Need the phase scope and design file | 2 |
| read-by | [agent:sase-1nf.10.1.9.1.6.5][2] | Review the parent epic, phase evidence, and remaining acceptance scope before doing acceptance work | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.9.1.6.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.9.1.6.5/README.md

<!-- sase:referenced-by:end -->
