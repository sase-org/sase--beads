# Bead: sase-hb.2 — Python discovery, validation, generation, and bundled migration

[Bead Pages](../README.md) / [sase-hb](README.md) / sase-hb.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.vh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.vh/README.md) · **Assignee:** `sase-hb.2` · **Size:** medium
**Created:** 2026-08-07 22:51:25 EDT · **Closed:** 2026-08-08 01:11:18 EDT
**Plan:** [202608/xprompt\_skill\_directories.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_skill_directories.md)

## Description

sase-runtime: consume the core contract, enforce canonical placement, preserve slash names, and migrate bundled sources.

## Notes

[2026-08-08T05:09:46Z · sase-hb.2] PROPOSED FOLLOW-UP: the epic plan inventory missed a config-defined skill — `sase_gmail` is declared with `skill: true` in ~/.config/sase/sase_athena.yml; phase 4 must migrate it to a canonical ~/sase/skills/sase_gmail.md (chezmoi home/sase/skills/) alongside bob_query.md, or the hard cutover drops it.

[2026-08-08T05:09:59Z · sase-hb.2] PROPOSED FOLLOW-UP: 6 pre-existing test failures unrelated to this phase — tests/test_gate_cli_show.py (4) and tests/gate_conformance/test_gate_conformance.py[cli/ace-legacy_shared_input] (2); they reproduce on a clean master tree because sase-core master is ahead of this repo on the gate declared-inputs mobile wire (commit 65e0ec1).

[2026-08-08T05:10:09Z · sase-hb.2] PROPOSED FOLLOW-UP: tests/ace/tui/visual/test_ace_png_snapshots_frontmatter_panel.py::test_frontmatter_panel_raw_diagnostics_png_snapshot fails on a clean master tree too (pre-existing visual snapshot drift, not caused by the skill layout work).

[2026-08-08T05:10:18Z · sase-hb.2] PROPOSED FOLLOW-UP: sase/memory/generated_skills.md still says skills are generated from `src/sase/xprompts/skills/`; the canonical packaged location is now `src/sase/skills/`. Memory edits need explicit user authorization, so this was left untouched.

[2026-08-08T05:10:38Z · sase-hb.2] Cross-repo: this phase also added one small change to the linked sase-core checkout (uncommitted, for the land agent) — crates/sase_core/src/xprompt_catalog.rs now skips SKILL.frame.template.md in the packaged skills scan plus a covering test, so the native fallback does not report the packaged Jinja frame as a misplaced skill. Verified with cargo fmt --check, clippy -D warnings, and cargo test --workspace (all green).

[2026-08-08T05:10:47Z · sase-hb.2] Deferred to phase 3 by plan assignment: docs/xprompt.md still points at src/sase/xprompts/skills/, and the mobile helper bridge / ACE authoring + copy-on-edit destinations still need skill_name and canonical-destination handling. Phase 2 carried skill_name only as far as needed to keep the tree green (structured catalog entry, ACE assist entry, `/` completion match+insert, `/foo` jump+preview lookup, and `/foo` syntax highlighting).

[2026-08-08T05:11:18Z · sase-hb.2] Phase 2 implemented in the sase repo (uncommitted, left for the epic land agent). Content layout: mirrored the Rust skill wire in Python (SkillSource, SkillPlacementIssue, skills LayoutPath on project/home/chezmoi, schema_version 2) and added resolve_skill_file_sources / skill_reference_name / skill_placement_issue adapters. New src/sase/xprompt/loader_skills.py centralizes every skill decision so Python enforces exactly the native rules: canonical placement + truthy skill is required in both directions, package/plugin/project/home/home_project sources load first-wins, accepted skills keep foo as XPrompt.skill_name and take skills/foo (or app/skills/foo) as the xprompt reference. Ordinary xprompt dirs, plugin xprompts/, and all config entry parsing now reject skill: with a migration diagnostic recorded as an XPromptLoadIssue(kind=skill_placement). Removed the packaged xprompts/skills special scan and config-based skill support. Moved all 16 bundled sources + SKILL.frame.template.md to src/sase/skills/, renders the frame through the sase.skills package, and repointed the source-integrity guard and provenance manifest at the packaged skill subtree (manifest hash and ordering now key on skill_name). Selection, rendering, target grouping, generated frontmatter, self-audit directive, inventory, and compact source display all use skill_name; generation refuses outright on any placement violation (skill init exits 1, plan reports blockers, skill list warns in a Misplaced Sources panel). Verified: just install; just lint clean (ruff, mypy 2851 files, symvision, toobig, keep-sorted, changelog); just test 27540 passed with only 6 pre-existing gate failures that reproduce on a clean master tree; just test-visual back to its one pre-existing frontmatter-panel failure; sase-core cargo fmt --check, clippy -D warnings, and cargo test --workspace all green. Manual: sase xprompt show 'skills/sase_plan' resolves while bare sase_plan is unresolved with suggestions; sase skill list, sase skill init, sase doctor -C config.xprompt_definitions, and sase validate all report the two unmigrated live sources (bob_query.md and the config-defined sase_gmail) with exact move instructions — that is the hard cutover working as designed and clears in phase 4.

[2026-08-08T05:11:54Z · sase-hb.2] Phase 2 verified: just lint clean; just test 27540 passed; just test-visual back to single pre-existing failure; sase-core cargo fmt/clippy/test green. #skills/sase_plan resolves, bare #sase_plan rejected with suggestions, /sase_plan unchanged.

## Dependencies

- **Depends on:** [sase-hb.1](sase-hb.1.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-hb.3](sase-hb.3.md) ◐ · ⧖ 2026-08-07
- **Blocks:** [sase-hb.4](sase-hb.4.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-hb.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hb.2/README.md) | [sase-hb.2](sase-hb.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ab442ed`](https://github.com/sase-org/sase/commit/ab442ed247dbf2aec27ab89095852d1efb3a7216) | feat(skills)!: require skills to live in a dedicated skills/ directory | [sase-hb.2](sase-hb.2.md) | 2026-08-08 01:12:39 EDT |
