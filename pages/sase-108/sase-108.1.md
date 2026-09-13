# Bead: sase-108.1 — Rust link-location grammar

[Bead Pages](../README.md) / [sase-108](README.md) / sase-108.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1o](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.1o.md) · **Assignee:** `sase-108.1` · **Size:** medium
**Created:** 2026-09-13 10:09:11 EDT · **Closed:** 2026-09-13 11:09:01 EDT
**Plan:** [202609/pager\_line\_addressed\_links.md](https://github.com/sase-org/sase--plans/blob/main/202609/pager_line_addressed_links.md)

## Description

core-location: in sase-core, add the one link-location grammar (split_link_location plus its binding), accept GitHub-style line fragments in parse_fragment, and extend the document file-path scanner so a location suffix stays inside the link span.

## Notes

[2026-09-13T15:07:46Z · sase-108.1] PROPOSED FOLLOW-UP: sase_gateway fleet launch tests can miss settled receipts — cargo test -p sase_gateway failed fleet_launch_accepts_scoped_request_and_returns_receipt, fleet_launch_omits_bridge_name_when_prompt_has_id (receipt never reached state settled), and fleet_mutate_refuses_terminal_missing_capability_and_bridge_failure (seeded fleet row); this phase did not touch gateway.

[2026-09-13T15:09:01Z · sase-108.1] Verified in sase-core: split_link_location table covers colon/GitHub forms and the not-a-location guards; parse_fragment round-trips L12-40/L12C5/L12C5-L40C2 to canonical L12/L12-L40; document-scan spans keep :12-40, :12:5-40, #L12, #L12-L40, #L12C5-L40C2, markdown dest :27-44, and URL :12 as one URL (src/foo.py:12- still yields :12). Bindings artifact_ref_split_link_location and artifact_ref_link_location_wire_schema_version round-trip. fmt-check and clippy passed; artifact_ref unit tests and sase_core_py 144 binding tests passed. Pre-existing sase-yn LockTimeout flake still fails under parallel load (passed in isolation); sase-xv libpython path still needed for sase_core_py runtime.

## Dependencies

- **Blocks:** [sase-108.3](sase-108.3.md) ✓ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-108.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-108.1/README.md) | [sase-108.1](sase-108.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@17947a0`](https://github.com/sase-org/sase-core/commit/17947a05ffd6aea9555a8498f42da0777229b8ea) | feat(artifact-ref): add the one link-location grammar | [sase-108.1](sase-108.1.md) | 2026-09-13 11:11:32 EDT |
