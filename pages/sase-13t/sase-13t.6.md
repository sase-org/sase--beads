# Bead: sase-13t.6 — End-to-end verification and downstream unblock

[Bead Pages](../README.md) / [sase-13t](README.md) / sase-13t.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.11](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.11.md) · **Assignee:** `sase-13t.6` · **Size:** small
**Created:** 2026-09-20 08:29:35 EDT · **Closed:** 2026-09-20 14:52:31 EDT
**Plan:** [202609/pypi\_quota\_and\_release\_publishing.md](https://github.com/sase-org/sase--plans/blob/main/202609/pypi_quota_and_release_publishing.md)

## Description

verify: prove a complete five-file release lands through the changed path, record measured headroom, and corroborate the downstream beads that were blocked on published core.

## Notes

[2026-09-20T18:51:44Z · sase-13t.6] PROPOSED FOLLOW-UP: the daily cut (cron 41 7 * * *) and the quota-guard step summary have not run on a scheduled trigger yet - first daily cut is 2026-09-21 07:41 UTC; check that run merges exactly one release PR and that the step summary shows headroom. Also note the push run 35528672167 verified push-does-not-merge; the workflow_dispatch escape hatch verified by run 35528969349.

[2026-09-20T18:52:31Z · sase-13t.6] Verified 2026-09-20 against live PyPI + Actions. (1) Full release through changed path: 0.34.70 has 5 unyanked files (x86_64/aarch64 manylinux_2_28, universal2, win_amd64, sdist); run 35526991744 (gate commit) ran the completeness gate + dist-vs-EXPECTED_DIST_SUFFIXES guard live ('verified 5 distributions'); dispatch run 35528969349 (dry_run=false build_wheels publish_pypi expected_version=0.34.70) was all green: 5 builds with smoke tests on linux/macos/windows, twine check, quota step ('PyPI quota ok: 2,270,272,572 used + 0 incoming <= 10,737,418,240 limit, 8,467,145,668 free'), publish skip-existing no-op, merge job ran with no open release PR. (2) 0.34.48 reports 5 files, none yanked. (3) Headroom re-measured: 31 releases/155 files/2.27 GB (2.11 GiB) of 10 GiB; 8.47 GB free = ~108 releases at the latest 78.5 MB release (~116 at 73 MB avg): ~108 days at 1 release/day vs ~25 days at the old 4.32/day - in line with the ~105 day projection. (4) Release-plz green: last 12 runs incl. push run 35528672167 (cadence commit) success with Merge release PR + all builds skipped, i.e. push updates the release PR/gate but does not cut or publish; actstat not used (athena-only), gh run list used instead. (5) Downstream sase-10d, sase-12y.4, sase-12w.6.4.2, sase-11l.11.4, sase-zr.7.1.1.5.4.1 noted with 0.34.70 complete evidence; ratchet_core_window --report-only proposes 0.34.48->0.34.70; floor raise left to sase-10d. Not verified live: a scheduled daily cut (first 2026-09-21 07:41 UTC), filed as PROPOSED FOLLOW-UP. Open decisions from sase-13t.2 (macOS arm64-only, opt-level s) remain for the user.

## Dependencies

- **Depends on:** [sase-13t.2](sase-13t.2.md) ✓ · ⧖ 2026-09-20
- **Depends on:** [sase-13t.3](sase-13t.3.md) ✓ · ⧖ 2026-09-20
- **Depends on:** [sase-13t.4](sase-13t.4.md) ✓ · ⧖ 2026-09-20
- **Depends on:** [sase-13t.5](sase-13t.5.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-13t.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-13t.6/README.md) | [sase-13t.6](sase-13t.6.md) | 0 |
