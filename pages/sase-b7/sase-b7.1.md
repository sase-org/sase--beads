# Bead: sase-b7.1 — Rust core: VCS-backed records and on-demand materialization

[Bead Pages](../README.md) / [sase-b7](README.md) / sase-b7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b7.1` · **Size:** medium
**Created:** 2026-07-30 12:52:52 UTC · **Closed:** 2026-07-30 13:21:23 UTC
**Plan:** [202607/vcs\_backed\_artifact\_capture.md](https://github.com/sase-org/sase--plans/blob/main/202607/vcs_backed_artifact_capture.md)

## Description

core-record: add the three VCS-provenance fields and an optional stored path to the artifact-file wire, admit byte-free rows, resolve them to a new `vcs_backed` status, and add a content-verified git materialization primitive exposed through `sase_core_rs`.

## Notes

[2026-07-30T13:21:23Z · sase-b7.1] Verified in sase-core: cargo fmt --all -- --check; cargo clippy --workspace --all-targets -- -D warnings; cargo test --workspace (all crates green, including 1,081 core tests); installed Python binding reports artifact-file query wire v2, artifact-ref wire v3, and exports artifact_file_materialize_vcs. Parent formatting/lints and committed-plan validation passed; its full Python suite is intentionally blocked on follow-on py-record phase sase-b7.3 updating the old v2/v1 wire handshakes (93 expected artifact-reference/query failures), while SASE validation also reports the pre-existing missing epic-plan link in the plans sidecar.

## Dependencies

- **Blocks:** [sase-b7.3](sase-b7.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b7.1/README.md) | [sase-b7.1](sase-b7.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase-core | [`ee287b0`](https://github.com/sase-org/sase-core/commit/ee287b0523c8d611e9ce7935fc2a534287b7b104) | feat!: materialize VCS-backed artifact files | [sase-b7.1](sase-b7.1.md) | 2026-07-30 13:22:25 |
