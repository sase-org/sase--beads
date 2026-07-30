# Bead: sase-b2.9 — Raise the published \`sase-core-rs\` floor

[Bead Pages](../README.md) / [sase-b2](README.md) / sase-b2.9

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b2.9` · **Size:** small
**Created:** 2026-07-30 01:33:53 UTC · **Closed:** 2026-07-30 03:41:53 UTC
**Plan:** [202607/bead\_and\_agent\_artifact\_refs.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_and_agent_artifact_refs.md)

## Description

pin: after the sase-core release publishes, raise the `sase-core-rs` floor to the version that first ships the wire-schema-2 artifact-reference bindings, refresh the lock, and update the declared-minimum assertion.

## Notes

[2026-07-30T03:41:53Z · sase-b2.9] Raised the sase-core-rs floor to >=0.12.17,<0.13.0 (pyproject.toml:46), refreshed uv.lock, and updated the declared-minimum assertion in tests/test_sase_core_rs_telemetry_smoke_tool.py. Verified 0.12.17 is the first published release containing the wire-schema-2 artifact-ref work (sase-core commits c1ae5f5/858d24c/aaa4e05, release c24e7e9; PyPI upload 2026-07-30). tools/validate_sase_core_rs_version passed against the linked sase-core checkout and with --published-minimum; tools/check_sase_core_rs_bindings ran in a scratch venv holding exactly sase-core-rs==0.12.17 and confirmed all 213 required bindings; that same wheel reports artifact_ref_wire_schema_version()==2 and parses bead:/agent: refs. just check fully green.

## Dependencies

- **Depends on:** [sase-b2.8](sase-b2.8.md) ✓
