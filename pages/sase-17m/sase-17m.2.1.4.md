# Bead: sase-17m.2.1.4 — Classification sweep and cross-repo verification

[Bead Pages](../README.md) / [sase-17m.2.1](sase-17m.2.1.md) / sase-17m.2.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17m.2.md) · **Assignee:** `sase-17m.2.1.4` · **Size:** small
**Created:** 2026-09-23 22:54:53 EDT · **Closed:** 2026-09-24 02:34:37 EDT
**Plan:** [202609/agent\_session\_core\_expand.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_core_expand.md)

## Description

sweep: classify every remaining famil hit in sase-core, fix stragglers, confirm byte-identical output and unchanged schema versions, and verify that a sase workspace built against the final core passes sase tool run check. Record follow-ups for wire-cutover and core-contract on the phase bead.

## Notes

[2026-09-24T06:25:04Z · sase-17m.2.1.4] PROPOSED FOLLOW-UP: core-contract flips pinned legacy spellings (agent_cleanup/planner+wire agent_family_parallel; agent_hold family/families renames+selectors; agent_identity LEGACY_AGENT_SESSION_KIND=families path; relationships Session emits family; launch wires family_attach_parent/suffix+%id display; ownership convert_family/RESERVATION+CONTAINER_KIND family_generation/expected_family_generation; scan wires agent_family/agent_family_role/agent_family_parallel/family_shell/family_root_dismissed/family_member/family_key/family_anchor + AGENT_SESSION_INDEX_COLUMN value + runner serial_family claim + stats Session emits family; fleet locators family_id/family_role/family_label + logical_key family: segment + family-<hex> fallback + gate followup/grid family_name + owner-facts agent_family_role/parallel + presentation family_* fields; editor directive family keyword+metadata+completion/LSP maps; agent_group_archive canonical_global_family; storage SQL agent_family column+idx_agent_artifacts_agent_family)

[2026-09-24T06:25:36Z · sase-17m.2.1.4] PROPOSED FOLLOW-UP: core-contract removes legacy pyo3 registrations parse_agent_family_name, resolve_agent_family_parent, reconcile_agent_artifact_index_dismissed_family_members, fleet_followed_batch_family_promotions (keep new agent_session_* names)

[2026-09-24T06:26:04Z · sase-17m.2.1.4] PROPOSED FOLLOW-UP: wire-cutover tightens dual-shape sase directive tests to session-only and switches sase readers to new binding names (see companion commit a764a76d4)

[2026-09-24T06:26:39Z · sase-17m.2.1.4] PROPOSED FOLLOW-UP: sase just check red on pre-existing mypy error src/sase/ace/tui/widgets/file_panel/_content.py:132 FilePanelContentMixin has no attribute parent (unrelated TUI code, fails on clean tree with either core; blocks full cross-repo sase tool run check gate)

[2026-09-24T06:27:08Z · sase-17m.2.1.4] sweep classification: remaining famil hits = unrelated meanings (provider_usage model_family, query revert/tokenizer families, glossary pluralization test, source_language/vcs_log/machine_setup OS+language families, target_family unix) + pinned legacy spellings (see core-contract note) + legacy bindings (4 wrappers) + legacy-input fixtures/tests; fixed stragglers: launch clan-conflict+hold-self messages, hold validation message, family_dismissal_lineage error labels, storage SQL comment, artifact context doc, legacy/family locals

[2026-09-24T06:34:37Z · sase-17m.2.1.4] sweep done: 535 famil hits classified (unrelated/pinned-legacy/legacy-binding/legacy-fixture), 10 stragglers fixed; no SCHEMA_VERSION/SQL/golden/key-order drift; 8 bindings registered with new==legacy parity; sase-core check green; sase rebuilt via just install, test-scoped 749 passed + directive companions 37 passed; full sase check blocked only by pre-existing mypy error in unrelated TUI file (follow-up noted)

## Dependencies

- **Depends on:** [sase-17m.2.1.3](sase-17m.2.1.3.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.2.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.2.1.4/README.md) | [sase-17m.2.1.4](sase-17m.2.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@ae9dbf6`](https://github.com/sase-org/sase-core/commit/ae9dbf6e0719761d825478021aa8ff8d7b27aae8) | refactor(core): sweep remaining agent-family spellings to agent session | [sase-17m.2.1.4](sase-17m.2.1.4.md) | 2026-09-24 02:35:32 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.2.1.4][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-17m.2.1.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.2.1.4/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.2.1.land/README.md

<!-- sase:referenced-by:end -->
