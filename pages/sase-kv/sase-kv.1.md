# Bead: sase-kv.1 — Required \`ref.icon\` in the artifact ref provider spec wire

[Bead Pages](../README.md) / [sase-kv](README.md) / sase-kv.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.z6.f2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.z6.f2.md) · **Assignee:** `sase-kv.1` · **Size:** small
**Created:** 2026-08-13 09:16:30 EDT · **Closed:** 2026-08-13 09:25:11 EDT
**Plan:** [202608/artifacts\_tab\_icons.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_tab_icons.md)

## Description

wire: add a required `icon` string to the Rust `ArtifactRefProviderRefSpecWire`, validate it as a bounded one-or-two-cell glyph, and cover accept/reject and digest cases in the Rust unit tests.

## Notes

[2026-08-13T13:25:11Z · sase-kv.1] Added required ref.icon: String to ArtifactRefProviderRefSpecWire in crates/sase_core/src/artifact_ref/provider_spec.rs (sase-core repo), with a validate_tab_icon check (non-empty, trimmed, no control chars, <=8 chars/32 bytes, 1-2 display cells via unicode_width) wired into validate_artifact_ref_provider_spec. Left ARTIFACT_REF_PROVIDER_SPEC_WIRE_SCHEMA_VERSION at 1 per D2, with a comment recording why. Added tests: rejects_missing_or_malformed_icon (empty/whitespace/control/overlong/3-cell), accepts_two_cell_emoji_icon, digest_changes_when_icon_changes, plus updated valid_spec_passes_and_digest_is_stable's fixture. Updated the sase_core_py fixture in crates/sase_core_py/src/lib.rs (artifact_ref_contract_bindings_round_trip_json_shapes) to include icon. Verified: cargo test -p sase_core --lib artifact_ref::provider_spec (10/10 pass) and full 'just check' (fmt+clippy+whole workspace test suite) both clean. Changes are uncommitted in the sase-core checkout, ready for the epic land agent.

[2026-08-13T13:26:24Z · sase-kv.1] Added required icon field to ArtifactRefProviderRefSpecWire with validate_tab_icon() (non-empty, trimmed, no control chars, <=8 chars/32 bytes, 1-2 display cells). Wired into validate_artifact_ref_provider_spec. Fixed sase_core_py fixture. Verified: cargo test -p sase_core --lib artifact_ref::provider_spec (10/10 pass) and full just check (fmt, clippy, whole workspace test suite) both clean in sase-core repo.

## Dependencies

- **Blocks:** [sase-kv.3](sase-kv.3.md) ◐ · ⧖ 2026-08-13
- **Blocks:** [sase-kv.4](sase-kv.4.md) ✓ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-kv.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kv.1/README.md) | [sase-kv.1](sase-kv.1.md) | 0 |
