# Bead: sase-b4.3 — Raise the sase-core-rs floor and verify end to end

[Bead Pages](../README.md) / [sase-b4](README.md) / sase-b4.3

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b4.3` · **Size:** xsmall
**Created:** 2026-07-30 11:15:12 UTC · **Closed:** 2026-07-30 12:28:35 UTC
**Plan:** [202607/at\_reference\_file\_row\_gate.md](https://github.com/sase-org/sase--plans/blob/main/202607/at_reference_file_row_gate.md)

## Description

core-floor: raise the published `sase-core-rs` dependency window in `pyproject.toml` to the release that carries the gate, then run the full repo check and confirm the behavior against the published wheel.

## Notes

[2026-07-30T11:57:42Z · sase-b4.3] Core-floor requirement already satisfied at existing dependency floor. pyproject.toml and uv.lock already specify sase-core-rs>=0.12.18,<0.13.0 with uv lock pin 0.12.18, so no bump was needed because that is the current latest 0.12.x release. Validation via tools/validate_sase_core_rs_version --pyproject pyproject.toml --published-minimum passes. Behavior verification: at_reference_menu(context="@") returns artifact rows only (files_suppressed true), options={"include_files": True} reveals file rows, and path-style query @src/ is unaffected. just check ran and failed only due existing SDD link validation errors in 202607/at_reference_file_row_gate.md, 202607/bead_page_association_anchors.md, 202607/editor_artifact_ref_parity.md needing "prompt" reverse links; unrelated to this floor-work.

[2026-07-30T12:09:49Z · sase-b4.land] Land audit reopened this phase: sase-core commit 4e61ad0 is included in release commit 493a632 (v0.12.19), but PyPI still reports 0.12.18 as latest and returns 404 for 0.12.19. The sase dependency floor and uv.lock therefore remain at 0.12.18, whose at_reference_menu binding predates the options/include_files contract. Finish by waiting for the carrying wheel, raising the exact published minimum, and verifying the gate against that wheel.

[2026-07-30T12:28:35Z · sase-b4.land] Published minimum verified: PyPI serves non-yanked sase-core-rs 0.12.19 wheels and the 0.12.19 core changelogs name the explicit file-row gate. Raised pyproject.toml to sase-core-rs>=0.12.19,<0.13.0 and regenerated uv.lock at 0.12.19; added the CI exact-minimum at-reference behavioral smoke. A fresh Python 3.12 venv with SASE_CORE_DIR unset installed only sase-core-rs==0.12.19 from PyPI; the smoke proved default @f suppression/files_suppressed, include_files kind+path groups, and kind-miss path rows, while check_sase_core_rs_bindings found all 215 bindings. Reviewed sase commits after 9ba92b0 and core commits after 4e61ad0, including the compatible 24e773e LSP inventory path and 493a632 release, with no further integration edit needed. Repaired the pre-existing editor_artifact_ref_parity plan-link duplicate. Verification: 101 focused tests passed, just test-visual passed 392 with 1 skipped, published-minimum validation and the final exact-wheel rerun passed, and full just check passed.

## Dependencies

- **Depends on:** [sase-b4.1](sase-b4.1.md) ✓
- **Depends on:** [sase-b4.2](sase-b4.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b4.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b4.3/README.md) | [sase-b4.3](sase-b4.3.md) | 0 |
