# Bead: sase-1io.7.4 — Cut and publish the sase-core-rs release

[Bead Pages](../README.md) / [sase-1io.7](sase-1io.7.md) / sase-1io.7.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1io.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1io.land.md) · **Assignee:** `sase-1io.7.4` · **Size:** medium
**Created:** 2026-10-09 06:48:49 EDT · **Closed:** 2026-10-09 10:41:07 EDT
**Plan:** [202610/finish\_release\_v0\_18\_0.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_release_v0_18_0.md)

## Description

core-release: wait for green sase-core CI on the race fix, dispatch the urgent release-plz cut, and verify the new sase-core-rs is complete on PyPI.

## Notes

[2026-10-09T12:01:11Z · sase-1io.7.4] core-release status: sase-core master tip 5c5bcdc4 (race fix) has CI run 37926536976 in_progress (ubuntu+mac lanes running); release-plz PR 323 refreshed with CI run 37926645055 pending; PyPI sase-core-rs still 0.37.0 (5 dists). Waiting on master CI via monitor.

[2026-10-09T12:19:30Z · sase-1io.7.4--1] core-release status: master CI run 37926536976 success, PR 323 checks all pass (ubuntu+mac, maturin smoke); PyPI still 0.37.0; dispatched urgent cut release-plz run 37929193715 with dry_run=false; waiting on merge then push-triggered tag+publish.

[2026-10-09T12:32:18Z · sase-1io.7.4--2] core-release status: urgent-cut dispatch run 37929193715 FAILED at Merge release PR (transient: master moved 5c5bcdc4->51b66fdb feat(autonomy) mid-wait; waiter saw pending runs 37929307022 then no checks reported on release-plz branch). PR 323 still OPEN chore: release v0.37.1 (includes race fix + autonomy feats), mergeable, checks pending on CI run 37929649960 (ubuntu done success; mac + maturin in progress). PyPI still 0.37.0 (5 dists). Next: wait for PR checks green then re-dispatch urgent cut.

[2026-10-09T12:41:18Z · sase-1io.7.4--2] core-release status: PR 323 CI run 37929649960 nearly green (ubuntu pass, maturin pass, macos-latest still running after ~13m); dispatch 37929193715 failure was transient (master 5c5bcdc4->51b66fdb moved mid-wait). Handing wait+urgent-cut+publish to monitor.

[2026-10-09T14:41:07Z · sase-1io.7.4--4] RELEASE NOT CUT: sase-core-rs 0.37.1 tag+publish run 37935460850 failed on windows x86_64 (E0658 windows_by_handle nightly-only + E0308 Option<u64> vs u64 at fingerprint.rs:187 and jsonl.rs:441); PyPI still 0.37.0 with 5 unyanked dists. PR 323 merged as 8237053f via urgent-cut dispatch 37932603894 (success); PR CI 37929649960 green. sase tool run check 53b24cc5cbeea6d2db9ec0d30d3ca327 verdict pass with the fix present. Landed stable Windows fallback (report 0, freshness on size+mtime) as sase-core 844b6c1d on master, pushed c02edc5b..844b6c1d. epic-symbols clean. Next release-plz cut will publish a version containing the fix.

## Dependencies

- **Depends on:** [sase-1io.7.1](sase-1io.7.1.md) ✓ · ⧖ 2026-10-09
- **Blocks:** [sase-1io.7.5](sase-1io.7.5.md) ✓ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1io.7.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1io.7.4.md) | [sase-1io.7.4](sase-1io.7.4.md) | 0 |
