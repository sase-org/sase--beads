# Bead: sase-1t3.11.1.3 — Restrict touch queries to exact actors and session aliases

[Bead Pages](../README.md) / [sase-1t3.11.1](sase-1t3.11.1.md) / sase-1t3.11.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t3.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.11.md) · **Assignee:** `sase-1t3.11.1.3` · **Size:** medium
**Created:** 2026-11-17 12:30:56 EST · **Closed:** 2026-11-17 19:57:08 EST
**Plan:** [202611/bounded\_log\_queries.md](https://github.com/sase-org/sase--plans/blob/main/202611/bounded_log_queries.md)

## Description

bead_touches: identify the surviving touch owner, push actor matching into Rust, remove full touch/view snapshots, and preserve legacy-view and session attribution.

## Notes

[2026-11-18T00:38:21Z · sase-1t3.11.1.3] Surviving touch owners identified: (1) `_bead_touches_snapshot_cache` retained a full tuple[BeadTouch] per project and the census undercounted it because `_lru_cache_census` counts attr `events` while the entry stores `touches` (always reported 0); (2) `_bead_views_snapshot_cache` retained full tuple[BeadViewEvent] per project and was never probed by `known_cache_census` at all. Both caches are now removed; only the two bounded 128-entry/50-row result caches remain. Probe: 20,003-row index materialized 20,003 Python BeadTouch objects per full query; after the change 20k unrelated touches + 5k unrelated views yield exactly 1 retained BeadTouch (cold 102ms, warm cache-hit 0.2ms).

[2026-11-18T00:38:37Z · sase-1t3.11.1.3] PROPOSED FOLLOW-UP: sase tool run check test (scoped) shows two KNOWN failures with multi-agent witnesses predating this phase (5 distinct agents, 3 workspaces, first seen 2026-11-16): test_app_import_stays_under_startup_budget and test_tracked_marker_mutation_sites_are_reviewed. Both reproduce without this phase's files touched; no new task bead filed since triage already tracks them as KNOWN.

[2026-11-18T00:57:08Z · sase-1t3.11.1.3] Done. Touch index + legacy views are queried in Rust for the context's ordered member selectors; both full-project snapshot caches are removed.

Verified: sase `sase tool run check` — all lint gates green (ruff, mypy, symvision, keep-sorted, etc.), scoped tests green except 2 KNOWN pre-existing failures recorded as PROPOSED FOLLOW-UP (multi-agent witnesses predate this phase); sase-core `sase tool run check` green; 135 touched-area tests pass against the locally built core; 20k-unrelated-touches + 5k-unrelated-views probe retains exactly 1 BeadTouch (cold 102ms, warm 0.2ms); `sase bead epic-symbols` clean. Matching parity (exact/local/legacy-bare, whitespace, email + foreign-dotted rejection, member precedence, trailing unlabeled session alias, durable-first merge, view fold counts/ties, tranche/incomplete handling) covered by new Rust unit + binding + facade + loader + session-alias tests.

Both repos changed, uncommitted for the host: sase (14 files) + linked sase-core (5 modified, 1 new). Host commits core first, then ratchets sase-core-revision.txt past the core commit before the sase commit. Incidental: one-token clippy-drift fix in audit_query.rs (matches!(1|2|3) -> 1..=3), proven failing on the untouched base with the floating stable toolchain.

## Dependencies

- **Depends on:** [sase-1t3.11.1.2](sase-1t3.11.1.2.md) ✓ · ⧖ 2026-11-17
- **Blocks:** [sase-1t3.11.1.4](sase-1t3.11.1.4.md) ✓ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.11.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.11.1.3/README.md) | [sase-1t3.11.1.3](sase-1t3.11.1.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@9f9341e`](https://github.com/sase-org/sase-core/commit/9f9341e55169216ecb63ab34e0bd384ff32b4126) | feat(bead): add member-targeted touch index query with streaming views fold | [sase-1t3.11.1.3](sase-1t3.11.1.3.md) | 2026-11-17 20:00:08 EST |
| sase | [`4894d41`](https://github.com/sase-org/sase/commit/4894d4199101499cf69fa519881a909fb2825217) | feat(bead): route touch and legacy view queries through targeted Rust member queries | [sase-1t3.11.1.3](sase-1t3.11.1.3.md) | 2026-11-17 20:02:02 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1t3.11.1.3][1] | check phase notes for prior work remainder | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.11.1.3/README.md

<!-- sase:referenced-by:end -->
