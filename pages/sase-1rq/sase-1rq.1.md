# Bead: sase-1rq.1 — Turn sase-core CI green and unblock its release

[Bead Pages](../README.md) / [sase-1rq](README.md) / sase-1rq.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.19h](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.19h.md) · **Assignee:** `sase-1rq.1` · **Size:** xlarge
**Created:** 2026-11-07 07:46:42 EST · **Closed:** 2026-11-07 10:07:01 EST
**Plan:** [202611/red\_ci\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202611/red_ci_repair.md)

## Description

sase-core: fix the macOS-only agent_artifact_run_trash test failure that keeps master CI and the v0.44.0 release-plz PR red, then get a sase-core-rs release containing sase's core pin published under the release_merge decision.

## Notes

[2026-11-07T14:15:26Z · sase-1rq.1--2] Release PR #343 MERGED at 2026-11-07T14:09:22Z merge SHA 317ea6a1252710e1d6c44d7289eb856f994950e0 (PR head 7aadfbbe1742893e2c8544e7b560805d185ad7f8). Master CI 42376693328 success at dec432ca, PR CI 42376753765 success. Tag v0.44.0 created 14:09:38Z; Release-plz run 42380255957 and CI 42380255837 in_progress on merge SHA; PyPI 0.44.0 404 pending.

[2026-11-07T14:19:11Z · sase-1rq.1--2] Publish watch 14:1xZ: Release-plz 42380255957 jobs release/PR/sdist success, 4 wheels in_progress (linux x86_64+aarch64, macos universal2, windows x86_64); CI 42380255837 ubuntu+scripts success, macos+maturin in_progress; PyPI 0.44.0 404; tag v0.44.0 points at merge 317ea6a; pin c8adc878 ancestor of v0.44.0 verified (exit 0), fix dec432ca also in tag. EXPECTED_DIST_SUFFIXES = manylinux_2_28_x86_64/aarch64, universal2, win_amd64, .tar.gz. Monitor 4nt929 staged; bead stays open until publish green.

[2026-11-07T14:20:32Z · sase-1rq.1--2] Publish watch 14:20Z: Release-plz 42380255957 still in_progress (release/PR/sdist success, 4 wheels in_progress); CI 42380255837 still in_progress (ubuntu+scripts success, macos+maturin in_progress); PyPI 0.44.0 still 404; master tip still 317ea6a. Cannot publish ci_evidence or close yet; monitor 4nt929 remains staged. Bead stays open.

[2026-11-07T15:06:49Z · sase-1rq.1--3] PROPOSED FOLLOW-UP: Transient sigstore Rekor 500 failed the push Release-plz publish-to-PyPI job (run 42380255957, job 128432796254) after twine check passed; scheduled Release-plz run 42381001806 on the same SHA went fully green including publish. If Rekor flakiness recurs, consider retry guidance for the publish job.

[2026-11-07T15:07:01Z · sase-1rq.1--3] sase-core v0.44.0 shipped. Fix dec432ca (canonical trash-root assertion) green: master CI 42376693328 success, PR #343 CI 42376753765 success. PR #343 merged 2026-11-07T14:09:22Z as 317ea6a. Final-tip CI 42380255837 success on 317ea6a; master tip still 317ea6a. Push Release-plz 42380255957 failed only on publish-to-PyPI sigstore Rekor 500 (transient infra, twine check passed); scheduled Release-plz 42381001806 on same SHA fully success incl. publish. PyPI sase-core-rs 0.44.0 complete: 5/5 files unyanked (uploads 14:58:01-12Z). Pin c8adc878 verified ancestor of v0.44.0 (merge-base exit 0); tag v0.44.0 dereferences to 317ea6a. epic-symbols clean. ci_evidence published.

## Dependencies

- **Blocks:** [sase-1rq.2](sase-1rq.2.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.1.md) | [sase-1rq.1](sase-1rq.1.md) | 0 |
