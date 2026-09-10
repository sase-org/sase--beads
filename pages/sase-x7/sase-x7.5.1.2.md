# Bead: sase-x7.5.1.2 — Land every Rust core contract change as one release

[Bead Pages](../README.md) / [sase-x7.5.1](sase-x7.5.1.md) / sase-x7.5.1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-x7.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-x7.5.md) · **Assignee:** `sase-x7.5.1.2` · **Size:** medium
**Created:** 2026-09-10 05:59:55 EDT
**Plan:** [202609/shared\_format\_bridge.md](https://github.com/sase-org/sase--plans/blob/main/202609/shared_format_bridge.md)

## Description

bridge-core-contracts: Make the canonical Patch wire native in sase_core's parser, add canonical discriminator support to the gateway and xprompt LSP, add the two migration conversion contracts the kit will call, update the PyO3 bindings and parity tests, then publish one core release and ratchet the host's sase-core-rs floor and pinned revision.

## Notes

[2026-09-10T11:05:35Z · sase-x7.5.1.2] Core contracts implemented and verified on the opened sase-core tree. Native parse_patch_project_bytes now builds PatchWire directly; parse_project_bytes is the ChangeSpecWire projection. Added GET /api/v1/patch-tags alongside changespec-tags, LSP catalog accepts entry_kind without legacy kind, and migration plan/apply/verify contracts: migration_patch_records_{plan,apply,verify} and migration_gate_bundles_{plan,apply,verify}. Verified: cargo fmt --check, clippy -D warnings, cargo test --workspace including PyO3 (python3.12). Golden/parity included in workspace tests. epic-symbols currently clean. Remaining for this same phase (do not close until done): land sase-core to origin/master, wait for release-plz to publish sase-core-rs, then in the host repo raise pyproject.toml sase-core-rs floor, ratchet sase-core-revision.txt, add the six new bindings to tools/check_sase_core_rs_bindings REQUIRED_BINDINGS, tools/validate_sase_core_rs REQUIRED_BINDINGS, and tests/test_check_sase_core_rs_bindings_tool.py, confirm tools/check_sase_core_rs_bindings, tools/validate_sase_core_rs, and tools/validate_sase_core_rs_version, run host just check, then close this bead only.

## Dependencies

- **Depends on:** [sase-x7.5.1.1](sase-x7.5.1.1.md) ✓ · ⧖ 2026-09-10
- **Blocks:** [sase-x7.5.1.4](sase-x7.5.1.4.md) ◐ · ⧖ 2026-09-10
- **Blocks:** [sase-x7.5.1.5](sase-x7.5.1.5.md) ◐ · ⧖ 2026-09-10
- **Blocks:** [sase-x7.5.1.6](sase-x7.5.1.6.md) ◐ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-x7.5.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.5.1.2/README.md) | [sase-x7.5.1.2](sase-x7.5.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@02a1725`](https://github.com/sase-org/sase-core/commit/02a172567b30e697fedf517b29f58e4a9349a895) | feat(core): land native PatchWire parser and shared-format conversion contracts | [sase-x7.5.1.2](sase-x7.5.1.2.md) | 2026-09-10 07:07:08 EDT |
