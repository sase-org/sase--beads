# Bead: sase-1ef.1 — One version identity model, honest numbering, and reliable attachment

[Bead Pages](../README.md) / [sase-1ef](README.md) / sase-1ef.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0v2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0v2.md) · **Assignee:** `sase-1ef.1` · **Size:** medium
**Created:** 2026-10-01 15:31:46 EDT · **Closed:** 2026-10-01 17:02:36 EDT
**Plan:** [202610/pager\_version\_clarity.md](https://github.com/sase-org/sase--plans/blob/main/202610/pager_version_clarity.md)

## Description

identity: add the pure VersionMoment model and step function that every surface reads; number versions as absolute vK of N; treat a clean now as the newest version so the first `(` never shows a byte-identical copy; fix bare-selector and stale-entry-point attachment failures.

## Notes

[2026-10-01T20:05:59Z · sase-1ef.1] PROPOSED FOLLOW-UP: visual goldens drift on clean tree too (26 timeband/history-diff goldens: stale footers missing =/@ verbs since picker commit; -diff states leak the real provider through installed entry points) — needs triage, badge phase owns history/timeband regen

[2026-10-01T20:06:14Z · sase-1ef.1] PROPOSED FOLLOW-UP: timeband past/cause goldens still show the interim chip age from identity phase until the badge-phase pill replaces the chip and regenerates goldens

[2026-10-01T21:02:36Z · sase-1ef.1--2] identity phase done: VersionMoment model + step/canonical/boundary, absolute vK-of-N chip, clean-now skips identical vN, bare-selector and stale-entry-point attachment fixed. Verified: mypy 5442 files clean, ruff clean, 62 tests pass (test_history_moment, test_app_history, test_history_pager_provider), history tombstone/past/dirty PNG goldens pass (tombstone regen for fixed fixture time + formatted banner). past-diff/dirty-diff goldens fail identically on clean base (pre-existing, badge phase owns per note #1); 8 unrelated full-suite failures pass in isolation. epic-symbols clean.

## Dependencies

- **Blocks:** [sase-1ef.2](sase-1ef.2.md) ◐ · ⧖ 2026-10-01

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ef.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ef.1.md) | [sase-1ef.1](sase-1ef.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`45ece4f`](https://github.com/sase-org/sase/commit/45ece4f1d001c0793f44ca6f71c4b303361ed108) | feat(pager): version identity model with honest numbering and reliable attachment | [sase-1ef.1](sase-1ef.1.md) | 2026-10-01 17:04:46 EDT |
