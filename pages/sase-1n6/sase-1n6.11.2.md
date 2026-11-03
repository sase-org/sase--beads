# Bead: sase-1n6.11.2 — Seal and enforce the core source-pin containment

[Bead Pages](../README.md) / [sase-1n6.11](sase-1n6.11.md) / sase-1n6.11.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1n6.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.land.md) · **Assignee:** `sase-1n6.11.2` · **Size:** medium
**Created:** 2026-11-03 09:51:13 EST · **Closed:** 2026-11-03 11:15:22 EST
**Plan:** [202611/e2\_steward\_train\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202611/e2_steward_train_completion.md)

## Description

containment: release.yml seals sase-core-revision.txt as the core source pin with a containment proof for tag v<core>, seal and evaluate refuse without it, and the stale rust-backend doc sentence and ratchet test names are fixed.

## Notes

[2026-11-03T15:20:58Z · sase-1n6.11.2] LANDED containment: tools/release_candidate SCHEMA_VERSION=2; sealed key core_containment {pin, core_version, tag, compare_status, tag_sha}; subcommand `containment` uses tools/_release_core.prove_containment (GitHub compare ahead/identical + local-git fallback). seal/evaluate refuse without a record that proves exactly that 40-hex pin by exactly the sealed core version; typed refusal CORE_LAG(pin=…, core=…). release.yml reads sase-core-revision.txt and runs containment before seal. No sase-core commit; pin unchanged.

Live proof 2026-11-03: pin f1bbb4f3b81383c06df422c9df9fa13f0ec244f7; core-ensure CORE_LAG(pin=f1bbb4f3…, newest_complete=0.43.3); `release_candidate containment --pin-file sase-core-revision.txt --core-version 0.43.3` → REFUSED CORE_LAG(pin=f1bbb4f3b81383c06df422c9df9fa13f0ec244f7, core=0.43.3). Same typed lag for pyproject 0.43.2.

[2026-11-03T15:51:48Z · sase-1n6.11.2] PROPOSED FOLLOW-UP: tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed fails identically on clean HEAD bdbbce02e3 — unreviewed path-passing sites src/sase/instructions/_readout_build.py:build_readout and src/sase/instructions/_readout_classify.py:classify_artifact_dir (read-only agent_meta.json/done.json inspection). Triage labeled FLAKY with no owner; check run 3753b7d7b3d6e6e68982f58fa4de5651 verdict no_new_failures. No open task bead tracks these two sites.

[2026-11-03T16:15:22Z · sase-1n6.11.2] Verified schema v2 core_containment (pin, core_version, tag, compare_status, tag_sha); seal/evaluate refuse without a record that proves the exact 40-hex pin by the sealed core version; release.yml reads sase-core-revision.txt and runs containment before seal; live pin f1bbb4f3b81383c06df422c9df9fa13f0ec244f7 refuses CORE_LAG against 0.43.2 and 0.43.3; epic-symbols clean. sase tool run check 80875a5b76ec04281d1c23f9e0f239c4: lint green, 59832 passed, verdict no_new_failures — 1 FLAKY (test_tracked_marker_path_passing_sites_are_reviewed) reproducing identically on clean HEAD bdbbce02e3; recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-1n6.11.3](sase-1n6.11.3.md) ◐ · ⧖ 2026-11-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n6.11.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.11.2/README.md) | [sase-1n6.11.2](sase-1n6.11.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`173a548`](https://github.com/sase-org/sase/commit/173a548ee147036be6bfbee3f16a9e22a64e3d42) | feat(release): seal core source-pin containment at tag v\<core\> | [sase-1n6.11.2](sase-1n6.11.2.md) | 2026-11-03 11:17:26 EST |
