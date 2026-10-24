# Bead: sase-1nn.8.2 — Cut sase-core-rs 0.42.3 and raise sase's exact core pin

[Bead Pages](../README.md) / [sase-1nn.8](sase-1nn.8.md) / sase-1nn.8.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.land.md) · **Assignee:** `sase-1nn.8.2` · **Size:** medium
**Created:** 2026-10-23 18:32:22 EDT · **Closed:** 2026-10-23 20:22:46 EDT
**Plan:** [202610/v0\_18\_1\_release\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_release_landing.md)

## Description

core-cut: dispatch the guarded sase-core cut for v0.42.3, wait for a complete 0.42.3 on PyPI, ratchet sase's ==0.42.2 pin, and prove the floor smoke locally.

## Notes

[2026-10-23T22:40:31Z · sase-1nn.8.2] Dispatched guarded sase-core cut for v0.42.3. PR #334 (chore: release v0.42.3) is OPEN/MERGEABLE/green and contains source pin 58aca5fe. Command: gh workflow run release-plz.yml -R sase-org/sase-core --ref master -f dry_run=false. Dispatch run 40034878073 (workflow_dispatch, head 58aca5fe): https://github.com/sase-org/sase-core/actions/runs/40034878073. sase master bb81495765 still pins sase-core-rs==0.42.2. Polling PyPI for the full EXPECTED_DIST_SUFFIXES set via monitor.

[2026-10-23T22:50:29Z · sase-1nn.8.2--1] Monitor cd60bhwtkvnz crashed in 1s: gh --json emitted ANSI (stdout starts with ESC), json.loads failed at column 1. Cut still in progress: dispatch 40034878073 in_progress, Merge release PR waiting, PR #334 OPEN/MERGEABLE, macos CI + maturin still pending, PyPI 0.42.3 404. Restarting wait with NO_COLOR/GH_COLOR=never and ANSI strip.

[2026-10-24T00:22:23Z · sase-1nn.8.2--2] PROPOSED FOLLOW-UP: TUI import budget over cap (sase-1ic) — sase tool run check 981738e311517a34324ee4002d5bd789 at 43314db7ad plus the 0.42.3 pin: tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget failed 3532 modules vs 3527 cap, triage KNOWN witness 0565caed0d1ee997557a16ec01dc1ecb, verdict no_new_failures. Phase did not touch TUI imports.

[2026-10-24T00:22:28Z · sase-1nn.8.2--2] PROPOSED FOLLOW-UP: project_labels audit at stranded_project_key_for_agent — same check failed tests/test_project_display_presentation_audit.py::test_project_labels_never_derive_from_paths (Path(str(project_file)).parent.name), KNOWN witness 0ac521ba0d479f11138736980b1ee6de. Unrelated to the pin. Origin a7996c3b77 (sase-1no.4) added a path-label exemption for that site after the check started; same audit class as closed sase-1ly.

[2026-10-24T00:22:46Z · sase-1nn.8.2--2] Cut complete: sase-core-rs 0.42.3 is on PyPI with the full EXPECTED_DIST_SUFFIXES set (manylinux_2_28_x86_64.whl, manylinux_2_28_aarch64.whl, universal2.whl, win_amd64.whl, .tar.gz). Files: sase_core_rs-0.42.3-cp312-abi3-macosx_10_12_x86_64.macosx_11_0_arm64.macosx_10_12_universal2.whl, sase_core_rs-0.42.3-cp312-abi3-manylinux_2_28_aarch64.whl, sase_core_rs-0.42.3-cp312-abi3-manylinux_2_28_x86_64.whl, sase_core_rs-0.42.3-cp312-abi3-win_amd64.whl, sase_core_rs-0.42.3.tar.gz. Dispatch 40034878073 completed success (workflow_dispatch head 58aca5fe). PR #334 MERGED at 2026-10-23T22:56:27Z (merge f726ca1e). Push 40036737007 completed success including linux x86_64/aarch64, macos universal2, windows x86_64, sdist, twine check, publish to PyPI. Tag v0.42.3 contains sase-core-revision.txt 58aca5fe69158286092e3a33685687a52f8d2b8f. python tools/ratchet_core_pin exit 2 applied ==0.42.2 -> ==0.42.3 in pyproject.toml and uv.lock; revision file unchanged. Floor smoke /tmp/release-core-floor-sase-1nn.8.2: sase-core-rs pin confirmed: 0.42.3; sase_core_rs 0.42.3 exposes all 876 bindings required by src/sase; tools/validate_sase_core_rs exit 0. just fix clean. sase tool run check 981738e311517a34324ee4002d5bd789: 57252 passed, 2 KNOWN (sase-1ic import budget 3532 vs 3527; project_labels stranded_project_key_for_agent, later exempted on origin a7996c3b77), verdict no_new_failures. epic-symbols: none.

## Dependencies

- **Blocks:** [sase-1nn.8.3](sase-1nn.8.3.md) ◐ · ⧖ 2026-10-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nn.8.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.8.2.md) | [sase-1nn.8.2](sase-1nn.8.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`dd0c6d8`](https://github.com/sase-org/sase/commit/dd0c6d8d191d2c7c099ec939dbec80cd5ceaf06a) | chore(deps): pin sase-core-rs to 0.42.3 | [sase-1nn.8.2](sase-1nn.8.2.md) | 2026-10-23 20:24:14 EDT |
