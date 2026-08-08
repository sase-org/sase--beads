# Bead: sase-hb.3 — Catalog, authoring, completion, and documentation updates

[Bead Pages](../README.md) / [sase-hb](README.md) / sase-hb.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.vh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.vh/README.md) · **Assignee:** `sase-hb.3` · **Size:** medium
**Created:** 2026-08-07 22:51:31 EDT · **Closed:** 2026-08-08 01:50:19 EDT
**Plan:** [202608/xprompt\_skill\_directories.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_skill_directories.md)

## Description

user-surfaces: expose the split xprompt and slash names consistently across every user-facing workflow.

## Notes

[2026-08-08T05:49:47Z · sase-hb.3] PROPOSED FOLLOW-UP: sase/memory/generated_skills.md still documents the old src/sase/xprompts/skills/ source path and pre-cutover #<name> skill references — needs a memory edit plus `sase memory init`, which requires explicit user permission the phase could not grant itself.

[2026-08-08T05:50:19Z · sase-hb.3] Phase 3 (user surfaces) complete. Carried skill_name through the mobile/editor helper catalog wire (matching the sase_gateway contract), sase xprompt list JSON, the sase xprompt show record (new skill_name field, slash row, "skill . /<name>" chip), the HTML catalog badge, and completion rows (a #skills/foo row now advertises /foo). Verified both reference forms hand the completion panel the same XPromptAssistEntry, so argument hints agree. Authoring: new src/sase/xprompt/skill_locations.py is the single source of canonical skill destinations; a draft declaring skill: is offered only sase/skills/ scopes (project rows project-qualify the hash reference while the slash name stays bare), the save modal verdict shows "#<project>/skills/foo . /foo" instead of implying #foo, and save_markdown_xprompt / save_markdown_document / save_config_xprompt now raise SkillPlacementError (surfaced verbatim in ACE) rather than smuggling a skill into sase/xprompts/ or a config entry. Docs: rewrote the xprompt.md Skill Field section (canonical sources table, source/reference/provider name split, hard-cutover statement), added a Skill Order section to content_layout.md, updated the discovery-order note, architecture/development path tables, ace.md slash-skill completion, editor.md, init.md, and the sase skill init / --allow-dirty help strings. Verification: just fmt and just lint clean (symvision included), full just test 27602 passed / 10 skipped, just test-visual 562 passed / 1 skipped, all with added tests for the editor bridge, list JSON, show render, completion row/parity, save guards, skill destinations, and the modal verdict. just check-full still stops at its sase validate gate on ~/sase/xprompts/bob_query.md declaring skill: outside a canonical source - that is the chezmoi source migration owned by sase-hb.4, not a Phase 3 regression. Memory-file drift recorded as a PROPOSED FOLLOW-UP.

[2026-08-08T05:50:53Z · sase-hb.3] Phase 3 skill cutover: skill_name plumbed through mobile/editor catalog, xprompt list JSON, show record (slash row + chip), HTML badge, and completion rows; new skill_locations.py restricts skill drafts to sase/skills/ and save.py raises SkillPlacementError for non-canonical writes; docs updated. Verified: just fmt/lint clean, just test 27602 passed/10 skipped, just test-visual 562 passed/1 skipped.

## Dependencies

- **Depends on:** [sase-hb.2](sase-hb.2.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-hb.5](sase-hb.5.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-hb.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hb.3/README.md) | [sase-hb.3](sase-hb.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c181d4c`](https://github.com/sase-org/sase/commit/c181d4c2442a47140f6465fb204decd4b7eac70d) | feat(skills)!: surface skill names across read surfaces and restrict authoring to skills/ | [sase-hb.3](sase-hb.3.md) | 2026-08-08 01:51:43 EDT |
