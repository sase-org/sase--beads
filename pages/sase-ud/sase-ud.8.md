# Bead: sase-ud.8 — Fork, CLI, and conformance

[Bead Pages](../README.md) / [sase-ud](README.md) / sase-ud.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0eg](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0eg.md) · **Assignee:** `sase-ud.8` · **Size:** medium
**Created:** 2026-08-26 14:02:56 EDT · **Closed:** 2026-08-26 22:45:32 EDT
**Plan:** [202608/gate\_shells.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_shells.md)

## Description

gate-fork-cli: classify a settled gate shell in resolve_family_member_shell with a GATE SHELL source label, add `sase gate list`/`show`/`cancel` as peers of the monitor verbs, grow the gate conformance matrix a shell dimension, and rewrite the /sase_gate skill template.

## Notes

[2026-08-27T02:39:28Z · sase-ud.8] PROPOSED FOLLOW-UP: Add a `shell:` filter token (shell:gate, shell:proc) to sase agent search — requires a sase-core (Rust) schema change, not free. Verified the agent_artifacts SQLite table (sase-core crates/sase_core/src/agent_scan/index.rs, CREATE TABLE around line 1982) has no shell_kind/agent_family_role/gate_id columns; those fields only live in the record_json blob the Python catalog deliberately never reads (src/sase/agents/catalog/_sources.py comment: "Only the columns the catalog's kind/attribute derivation actually needs. Never SELECT *"). A real token needs: sase-core adds a shell_kind column via ensure_agent_artifacts_column, populates it on INSERT, bumps the index schema version, rebuilds bindings; then src/sase/agents/catalog/_sources.py (_ARTIFACT_INDEX_COLUMNS + ArtifactIndexRecord), _models.py (AgentCatalogRow), _build.py (_build_row), _query.py (agent_catalog_query_entry), and src/sase/ace/query_profile/profiles/_agents.py (QueryFieldSpec) all need additions. Interim: role:gate already works today with zero code changes since role is derived by string-parsing the member suffix (e.g. acme--gate -> role=gate) — may be sufficient without the real column.

[2026-08-27T02:45:32Z · sase-ud.8] Auto-closed by `sase stitch create` after create_commit landed d4c3bb408 ("feat(gate-shell): add fork classification, CLI list/show/cancel, and shell conformance"). No verification is implied by this note. Reopen with `sase bead open sase-ud.8`, or pass `-B|--do-not-close-bead` on mid-flight commits.

## Dependencies

- **Blocks:** [sase-ud.10](sase-ud.10.md) ◐ · ⧖ 2026-08-26
- **Depends on:** [sase-ud.7](sase-ud.7.md) ✓ · ⧖ 2026-08-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ud.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ud.8/README.md) | [sase-ud.8](sase-ud.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d4c3bb4`](https://github.com/sase-org/sase/commit/d4c3bb4083fe11d0b74d3e9ab3fa7ebe0b19e6e1) | feat(gate-shell): add fork classification, CLI list/show/cancel, and shell conformance | [sase-ud.8](sase-ud.8.md) | 2026-08-26 22:43:35 EDT |
