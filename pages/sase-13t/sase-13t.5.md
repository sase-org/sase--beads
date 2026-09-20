# Bead: sase-13t.5 — Bound release cadence to a daily cut

[Bead Pages](../README.md) / [sase-13t](README.md) / sase-13t.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.11](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.11.md) · **Assignee:** `sase-13t.5` · **Size:** medium
**Created:** 2026-09-20 08:29:33 EDT · **Closed:** 2026-09-20 14:17:55 EDT
**Plan:** [202609/pypi\_quota\_and\_release\_publishing.md](https://github.com/sase-org/sase--plans/blob/main/202609/pypi_quota_and_release_publishing.md)

## Description

cadence: stop auto-merging the release PR on every master push, cut releases on one daily schedule instead, and keep the six-hourly heal plus a manual escape hatch for urgent floor bumps.

## Notes

[2026-09-20T18:17:55Z · sase-13t.5] sase-core release-plz.yml: added daily cut cron '41 7 * * *' beside the heal cron '23 */6 * * *'; release-plz-merge now runs only for that schedule or a workflow_dispatch with dry_run=false (pushes and the heal cron skip it), with a run-id-isolated concurrency group for non-cut runs; publish-plan/release-plz-release/release-plz-pr/build/publish gates untouched; all merge safety guards unchanged; header comment records the cadence decision. Added .github/scripts/test_release_cadence.py (14 tests, 6 fail against the old workflow) and a 'Release cadence' runbook section in docs/pypi-retention.md. Verified: workflow YAML parses, just check green in sase-core (fmt, clippy, cargo test, 51 script tests). NOT verified: live Actions behavior (a push updating but not merging the release PR, first daily cut) cannot run locally; it needs a real run after this lands, which sase-13t.6 should confirm. Change is uncommitted in the sase-core checkout pending the host finalizer.

## Dependencies

- **Depends on:** [sase-13t.4](sase-13t.4.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-13t.6](sase-13t.6.md) ◐ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-13t.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-13t.5/README.md) | [sase-13t.5](sase-13t.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@4987457`](https://github.com/sase-org/sase-core/commit/4987457d2d86f36d622223cedf009925a5e529ea) | ci(release): cut releases once a day instead of merging the release PR on every push | [sase-13t.5](sase-13t.5.md) | 2026-09-20 14:19:10 EDT |
