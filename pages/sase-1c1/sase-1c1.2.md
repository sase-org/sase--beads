# Bead: sase-1c1.2 — Cut and verify sase-core-rs 0.36.0 on PyPI

[Bead Pages](../README.md) / [sase-1c1](README.md) / sase-1c1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ti](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ti.md) · **Assignee:** `sase-1c1.2` · **Size:** small
**Created:** 2026-09-28 07:09:25 EDT · **Closed:** 2026-09-28 11:41:10 EDT
**Plan:** [202609/master\_ci\_green\_and\_0\_18\_release.md](https://github.com/sase-org/sase--plans/blob/main/202609/master_ci_green_and_0_18_release.md)

## Description

core-release: drive sase-core release PR #315 to all-green CI including macOS, dispatch release-plz with dry_run=false, and verify that PyPI has every 0.36.0 wheel plus the sdist.

## Notes

[2026-09-28T14:11:42Z · sase-1c1.2] PROGRESS: core-macos 1fee641 is on origin/master. PR #315 (chore: release v0.36.0) had red macOS on live_holder_matches_environ_path_through_symlink_with_missing_suffix: logical /var vs canonical /private/var in the assertion, not the product. Landed d437782 test(launch-scratch-liveness): compare canonical paths in symlink regression; sase tool run check d4ee2d629af370ec0289cb69eec4aeed green. release-plz refreshed PR head to cdcd09c (contains d437782). Watching CI run 36433907006 including macos-latest before dispatching release-plz dry_run=false. PyPI latest still 0.35.1.

[2026-09-28T14:31:56Z · sase-1c1.2--1] PROGRESS: PR #315 all-green on head 6e6ab24 (contains d437782). macos-latest pass 14m41s on CI run 36434329174; older run 36433907006 also success. Dispatched release-plz.yml dry_run=false: https://github.com/sase-org/sase-core/actions/runs/36436627545 (queued at 2026-09-28T14:31:32Z). Watching merge of #315, tag v0.36.0, wheel matrix, PyPI publish.

[2026-09-28T15:40:51Z · sase-1c1.2--6] 0.36.0 on PyPI verified: sase_core_rs-0.36.0-cp312-abi3-manylinux_2_28_x86_64.whl, -manylinux_2_28_aarch64.whl, -macosx_10_12_x86_64.macosx_11_0_arm64.macosx_10_12_universal2.whl, -win_amd64.whl, sase_core_rs-0.36.0.tar.gz. Runs: release-plz push 36439410345 success (all wheels + publish to PyPI), CI push 36439409885 success, PR 315 MERGED 14:53:38Z merge 550aa11, tag v0.36.0, pypi_release_files.py status 0.36.0 = complete.

[2026-09-28T15:41:10Z · sase-1c1.2--6] sase-core-rs 0.36.0 cut and verified on PyPI: 4 wheels (linux x86_64, linux aarch64, macos universal2, windows x86_64) + sdist. PR 315 MERGED 14:53:38Z (550aa11), tag v0.36.0. Runs: release-plz push 36439410345 success incl publish to PyPI, CI push 36439409885 success. pypi_release_files.py status 0.36.0 = complete.

## Dependencies

- **Depends on:** [sase-1c1.1](sase-1c1.1.md) ✓ · ⧖ 2026-09-28
- **Blocks:** [sase-1c1.14](sase-1c1.14.md) ◐ · ⧖ 2026-09-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1c1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1c1.2.md) | [sase-1c1.2](sase-1c1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@d437782`](https://github.com/sase-org/sase-core/commit/d43778255b9dca28b4cdb1de38d413bda5e6cbe2) | test(launch-scratch-liveness): compare canonical paths in symlink regression | [sase-1c1.2](sase-1c1.2.md) | 2026-09-28 10:04:23 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1c1.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1c1.2.md

<!-- sase:referenced-by:end -->
