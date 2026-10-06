# Bead: sase-1h8.3 — Hidden-clone gc and bead push-log retention

[Bead Pages](../README.md) / [sase-1h8](README.md) / sase-1h8.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3u.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3u.linker.w0.md) · **Assignee:** `sase-1h8.3` · **Size:** small
**Created:** 2026-10-06 18:59:32 EDT · **Closed:** 2026-10-06 19:40:05 EDT
**Plan:** [202610/bead\_store\_history\_independent\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202610/bead_store_history_independent_performance.md)

## Description

maintenance: make the sidecar gc pass reach the host-owned hidden beads clone, fix the stale projection-size comment, and add bounded retention for ~/.sase/bead_push_logs.

## Notes

[2026-10-06T23:11:15Z · sase-1h8.3] Acceptance: hidden-clone gc on athena for gh_sase-org__sase — beads clone before: count 2433, size 1.97 GiB, in-pack 142143, packs 37, size-pack 1.34 GiB; after maintain_hidden_sidecar_clones: count 0, packs 2, size-pack 258 MiB (4 clones gcd: agents/beads/plans/research). Push-log retention first pass: 126094 -> 52793 logs (73301 deleted, 30d/keep-200 defaults); recent_bead_sync_log_paths/latest_bead_sync_log still work (64 recent, latest sync-261006_190805 log resolvable).

[2026-10-06T23:38:55Z · sase-1h8.3--1] PROPOSED FOLLOW-UP: symvision lint flags private _runs import in src/sase/agents_sync/v2_snapshot_io.py and src/sase/ace/tui/widgets/decks/final/overview_card.py (triage KNOWN, witness 22778c601b3c983292d19516826709e8, no owner); both files untouched by sase-1h8.3, failure reproduces identically on clean base tree

[2026-10-06T23:39:49Z · sase-1h8.3--1] PROPOSED FOLLOW-UP (duplicate of sase-1h6): see +1 corroboration there; closing sase-1h8.3 anyway per base-tree-repro rule

[2026-10-06T23:40:05Z · sase-1h8.3--1] Hidden-clone gc + push-log retention verified: focused suites passed (test_store_maintenance, test_sync_log_retention, test_sync_diagnostics, test_axe_chop_sidecar_auto_sync); live acceptance: hidden beads clone 2433 loose/1.97GiB/37packs to 0 loose/2packs/258MiB, push logs 126094 to 52793; full check red only on 2 KNOWN symvision _runs findings untouched by this diff, tracked by sase-1h6 (+1 corroborated); no epic-symbol leftovers

## Dependencies

- **Blocks:** [sase-1h8.14](sase-1h8.14.md) ◐ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.3.md) | [sase-1h8.3](sase-1h8.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`69ecdac`](https://github.com/sase-org/sase/commit/69ecdace02734e279daa201590722a5f4209ff5b) | feat(bead): hidden-clone gc and bead push-log retention (sase-1h8.3) | [sase-1h8.3](sase-1h8.3.md) | 2026-10-06 19:41:20 EDT |
