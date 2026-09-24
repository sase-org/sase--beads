# Bead: sase-17m.2.1.1 — Identity, launch, holds, and directive/editor surfaces

[Bead Pages](../README.md) / [sase-17m.2.1](sase-17m.2.1.md) / sase-17m.2.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.2.md) · **Assignee:** `sase-17m.2.1.1` · **Size:** medium
**Created:** 2026-09-23 22:54:50 EDT · **Closed:** 2026-09-24 00:09:04 EDT
**Plan:** [202609/agent\_session\_core\_expand.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_core_expand.md)

## Description

identity-directives: rename agent_family.rs to agent_session.rs and the agent_identity, artifact_link, agent_launch, hold, editor, and LSP family concept. Add the parse_agent_session_name and resolve_agent_session_parent bindings, accept %id session=, reserve session/sessions, and flip editor completion to session= with companion sase tests that tolerate both core shapes.

## Notes

[2026-09-24T04:00:17Z · sase-17m.2.1.1] PROPOSED FOLLOW-UP: wire-cutover tightens the dual-shape directive tests to the new shape after the core pin bump

[2026-09-24T04:00:48Z · sase-17m.2.1.1] Phase exit: reserved-name check found no existing agent named session/sessions (rg over ~/.sase/projects empty, agent list clean); session/sessions added to RESERVED_USERNAMES so creation and validation reject them for new names, historical parsing untouched

[2026-09-24T04:01:38Z · sase-17m.2.1.1] Remaining famil hits in owned files: (a) legacy serialized spellings pinned for core-contract: family_name keys, family/families hold fields, family_attach_* launch keys, AgentContainerKind/DirectiveValueRole "family" values, families/ link paths, family: relationship keys, invalid-id-family code, family= keyword/directive syntax, "family" completion-kind matching; (b) legacy binding names: parse_agent_family_name, resolve_agent_family_parent; (c) no unrelated-meaning hits in owned files. No *_SCHEMA_VERSION value, SQLite schema, golden, or key-order assertion changed.

[2026-09-24T04:02:07Z · sase-17m.2.1.1] PROPOSED FOLLOW-UP: sase workspace sase tool run check is blocked by pre-existing mypy error in src/sase/ace/tui/widgets/file_panel/_content.py:132 (FilePanelContentMixin has no attribute parent), verified present with this phase changes stashed; unrelated to identity-directives

[2026-09-24T04:09:04Z · sase-17m.2.1.1] Closed by explicit `sase stitch create -B close` after create_commit landed a764a76d4 ("feat(ace): tolerate new agent-session spelling in directive contract and completion"). The commit author requested bead completion after verifying the bead scope. Reopen with `sase bead open sase-17m.2.1.1` if more work remains.

## Dependencies

- **Blocks:** [sase-17m.2.1.2](sase-17m.2.1.2.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.2.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.2.1.1/README.md) | [sase-17m.2.1.1](sase-17m.2.1.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a764a76`](https://github.com/sase-org/sase/commit/a764a76d41fbcacfe08ecbf93a351d3c53d732ad) | feat(ace): tolerate new agent-session spelling in directive contract and completion | [sase-17m.2.1.1](sase-17m.2.1.1.md) | 2026-09-24 00:05:04 EDT |
| sase-core | [`sase-core@c5b9c0d`](https://github.com/sase-org/sase-core/commit/c5b9c0d68867fb1cef8923b06270e39d5f9533d1) | feat(core): additive agent-session rename for identity, launch, holds, and editor surfaces | [sase-17m.2.1.1](sase-17m.2.1.1.md) | 2026-09-24 00:09:36 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.2.1.1][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-17m.2.1.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.2.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.2.1.land/README.md

<!-- sase:referenced-by:end -->
