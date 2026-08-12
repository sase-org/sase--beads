# Bead: sase-k2.1 — ProjectSpec description truncation and duplicate-block repair

[Bead Pages](../README.md) / [sase-k2](README.md) / sase-k2.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yn](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yn/README.md) · **Assignee:** `sase-k2.1` · **Size:** large
**Created:** 2026-08-12 11:28:34 EDT · **Closed:** 2026-08-12 12:32:27 EDT
**Plan:** [202608/external\_mirror\_refinement.md](https://github.com/sase-org/sase--plans/blob/main/202608/external_mirror_refinement.md)

## Description

spec_repair: fix the two-blank-line record terminator that silently drops any Patch whose DESCRIPTION contains a blank run, in both the Python and Rust parsers plus the block writer, and add the raw-text de-duplication repair that reclaims the archives the external PR mirror has already corrupted.

## Notes

[2026-08-12T16:20:23Z · sase-k2.1] PROPOSED FOLLOW-UP: flake baseline gate exceeds current baseline — just check-full selection-health reports six reproducible flakes over tests/reproducible_flake_baseline.txt: test_contract_manifest_matches_marker_selection and five test_core_vcs_log nodeids.

[2026-08-12T16:26:12Z · sase-k2.1] PROPOSED FOLLOW-UP: stale Symvision epic whitelist blocks just check — bead sase-js is closed, so the Justfile epic-symbol entries for five artifact-ref symbols must be removed and the now-unused symbols cleaned up.

[2026-08-12T16:32:27Z · sase-k2.1] Implemented ProjectSpec blank-run parser/doctor repair. Verified focused pytest passed, rust-check passed, live archive repaired to 289 NAME blocks / 289 unique names, duplicate-block doctor OK, and two sync-external dry runs planned zero writes. just check-full and just check were blocked by unrelated flake-baseline and stale Symvision whitelist issues recorded as follow-ups.

## Dependencies

- **Blocks:** [sase-k2.5](sase-k2.5.md) ✓ · ⧖ 2026-08-12
- **Blocks:** [sase-k2.6](sase-k2.6.md) ✓ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-k2.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-k2.1.md) | [sase-k2.1](sase-k2.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d4139e9`](https://github.com/sase-org/sase/commit/d4139e96e2ac263f7a8af15ddcf4bc74d3f66edc) | fix: repair duplicate ProjectSpec patch blocks | [sase-k2.1](sase-k2.1.md) | 2026-08-12 12:34:55 EDT |
| sase-core | [`sase-core@2519b42`](https://github.com/sase-org/sase-core/commit/2519b429fc25f3849fe967f191207957a66e10e8) | fix: preserve indented ProjectSpec blank lines | [sase-k2.1](sase-k2.1.md) | 2026-08-12 12:36:22 EDT |
