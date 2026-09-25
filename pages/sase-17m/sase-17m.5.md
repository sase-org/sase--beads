# Bead: sase-17m.5 — ACE agent session surfaces

[Bead Pages](../README.md) / [sase-17m](README.md) / sase-17m.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qh.md) · **Assignee:** `sase-17m.5` · **Size:** large
**Created:** 2026-09-23 22:46:38 EDT
**Plan:** [202609/agent\_session\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_rename.md)

## Description

ace-cutover: rename ACE modules, row kinds, the grouping mode, and visible copy (SESSION SHELLS, SESSION). Update keymap and help text, default_config.yml and the schema, perf baselines, and the PNG goldens, with no change to the performance contract.

## Notes

[2026-09-24T17:24:22Z · 0qz--code] symvision_green_master sweep: agent_session_suffix_token, is_agent_session_member, agent_session_role_for_suffix, allocate_agent_session_child_suffix stay public under --epic-symbol sase-17m(...) entries. ACE surface migration must remove all four entries once the symbols gain real consumers.

[2026-09-25T07:55:26Z · sase-17m.5.1.5] snapshots-sweep core-contract hand-off: marked core-emitted legacy readers still live in ACE (all carry # legacy agent-family spelling markers): fleet summaries family_id/family_role/family_label reads in models/_fleet_agents_{nodes,rows,identity,promotion}.py, agent_bundle.py legacy bundle-key map (~L146), dismissed_agent_groups.py canonical_global_family (~L100), actions/agents/_notification_matching.py family_root_suffix keys, revert_agent_models.py LEGACY_REVERT_SESSION_BASE_KEY=family_base, confirm_revert_agent_modal.py pre-rename scope reader, models/agent_live_query_engine.py family:/kind:family bridge via agent.legacy_agent_family_syntax. Test fixtures mirroring the wire: tests/ace/tui/_fleet_summary_fixture.py, _fleet_locator_fixture.py, _fleet_agents_projection_agent_session_tree.py + visual fleet/families tests (family_id kwargs + remote-family/done-family names). core-contract (sase-17m.8) flips these.

[2026-09-25T07:55:43Z · sase-17m.5.1.5] snapshots-sweep docs-memory hand-off: docs/ace.md still uses the retired concept name in 2 spots owned by sase-17m.6 — L5051 Sequential plan-family workflows and L5066 New plan-family metadata (per-step naming section). Landed ACE copy reads SESSION/session container/session row. Also tests/agents_sync/goldens/deep-family.md + rootless-family.md and src/sase/agents_sync/rendering_family_page.py stay family-named for session-pages (sase-17m.9).

## Dependencies

- **Depends on:** [sase-17m.4](sase-17m.4.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-17m.8](sase-17m.8.md) ◐ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.5.md) | [sase-17m.5](sase-17m.5.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:0qz--code][1] | verify 17m.5 open before adding epic-symbol entries | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qz.md

<!-- sase:referenced-by:end -->
