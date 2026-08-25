# Bead: sase-sq.8.1 — Retire the config glossary

[Bead Pages](../README.md) / [sase-sq.8](sase-sq.8.md) / sase-sq.8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-sq.8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-sq.8.md) · **Assignee:** `sase-sq.8.1.land`
**Created:** 2026-08-24 23:10:52 EDT · **Closed:** 2026-08-25 02:49:09 EDT
**Plan:** [202608/retire\_config\_glossary.md](https://github.com/sase-org/sase--plans/blob/main/202608/retire_config_glossary.md)

## Description

The strand-backed glossary is the only glossary implementation, ACE exposes it through MemoryPane, stale config and CLI surfaces are gone, and documentation and generated skills describe the final memory-web model.

## Notes

[2026-08-25T06:49:09Z · sase-sq.8.1.land] LAND VERIFICATION (sase-sq.8.1.land, master 882ba36f5).

VERIFIED (step 1). Read the epic bead, all three phase beads, and every note. All three
phases are CLOSED/done, but 8.1.2 and 8.1.3 carry only stitch auto-close notes that
explicitly imply no verification, so I checked the tree rather than the notes. Epic
commits: cebab38a1 (retire-core), 93d379e0a (unify-ace), 882ba36f5 (finish-docs).

Read the source, not the notes:
- Phase 1: src/sase/glossary/ and glossary_config.py are gone from git; relations.py,
  render.py, resolution.py, text_filter.py moved under sase/memory/web/; the v1 read log
  and report live at sase/memory/legacy_glossary_read_{log,report}.py with no append API.
  parser_glossary.py, glossary_handler.py, init_memory/glossary.py, the packaged
  generated-glossary template, _glossary_catalog_{config,ranges}.py, ValueKind.GLOSSARY
  and memory/web/{migrate,cli_migrate}.py are all deleted. `.venv/bin/sase glossary`
  now errors with "invalid choice: 'glossary'" and `sase memory web` exposes only
  list/show. The schema rejects memory.glossary (verified directly with Draft7Validator
  against the landed sase.schema.json) while ace.keymaps.glossary survives as the
  one-release inert compat block. `sase memory read glossary:stitch` and
  `sase memory web show glossary` both work end to end on this tree.
- Phase 2: every glossary_pane/glossary_panel* module and its Config-hub subtab are
  gone; PromptInputBar.GlossaryPanelRequested now carries a resolved glossary:<slug>
  note_identity that PromptBarMemoryPanelMixin opens on the Memory subtab. The new
  sase/memory/web/mutation.py does atomic create/delete with collision validation,
  SHA-256 digest conflict protection, glossary re-validation of the post-mutation web,
  and managed-roster regeneration of the descriptor. ACE and the CLI share one closure
  graph: memory_panel_catalog.py calls build_strand_mention_catalog /
  strand_mention_relations from sase.memory.web.closure, the same module memory/web/cli.py
  reads. doctor/checks_config_keymap_glossary.py inspects unmerged config layers so the
  warning only fires on a real user override, and it is registered as config.keymap_glossary.
- Phase 3: docs/{memory,cli,completion,configuration,ace,init,getting_started,xprompt}.md
  and the sase_memory_read skill source describe the final model; the only surviving
  "sase glossary" strings are deliberate historical prose about the retired command's
  legacy log and the retired pane's folded keybindings. docs/editor.md needed no change:
  its only glossary mentions are semantic highlighting, which this epic preserves.

Ran the plan's own landing checklist. `sase skill init` deployed the 14 pending provider
skill files from this clean canonical tree; chezmoi commit c70d9c83 records
SASE_SOURCE_REVISION=882ba36f5, matching HEAD exactly, and I applied the skill targets so
the deployed ~/.claude/skills/sase_memory_read/SKILL.md now documents web:keyword reads
instead of "Coming soon". `sase memory init --check` is clean for sase, home, and bob-cli.

GAPS FOUND AND FIXED (all caused by this epic, all fixed here as epic work):
1. memory-README.template.md wrote *is* / *renders* while prettier normalizes generated
   Markdown to _is_ / _renders_, so `sase memory init --check` reported permanent
   one-line drift in every root. Fixed the template; regenerated sase/memory/README.md,
   the chezmoi home README (chezmoi commit 02dbc9cf), and bob-cli's README.
2. tests/ace/tui/widgets/test_prompt_glossary_panel_entry.py (5 nodes) still asserted the
   removed GlossaryPanelRequested.term. Rewrote against note_identity, including a real
   source_path fixture that exercises the slug derivation and a new
   no-source-path miss case.
3. tests/xprompt/test_repo_mention_catalog.py::test_glossary_claimed_name_excluded seeded
   the exclusion from a memory.glossary config block that no longer feeds the catalog.
   Reseeded it from a real glossary web descriptor + strand.
4. tests/main/test_memory_log.py lost its `from datetime import UTC, datetime` when the
   glossary-log tests were removed, breaking the two surviving proposal tests.
5. Removing the Glossary sub-tab left _config_hub_strip_thresholds keyed to `tab_count
   >= 7`, which can no longer be reached: both flag states fell back to the 5-tab-era
   width 85, and micro kicked in at 73 against a 59-cell compact strip. Re-measured the
   rendered strip (81/59 cells with Flags on, 68/48 off) and retuned to 82/69/60 with
   the branch at >= 6. Updated the paired test plus the config-hub digit-navigation,
   flags-off numbering, and config_panel_tabs catalog assertions that still assumed
   seven sub-tabs, and the PRODUCTION_PRODUCERS count (44 -> 43) after glossary.write
   was removed from the proc-producer inventory.
6. Rebaselined 18 Config-hub PNG goldens across test_ace_png_snapshots_{config_center_config,
   config_center_edit,config_launch,feature_flags}.py. I read each diff.png first: every
   one is confined to the tab-strip row (01 ALL | 02 Flags | 03 Gloss | ... becomes
   01 ALL | 02 Flags | 03 Launch | ...), including the 70x32 micro-tier frames that
   exercise the new thresholds. Used the scoped --sase-update-visual-snapshots form, not
   a blanket update.

INTEGRATED (step 2). Only two non-epic commits landed inside this epic's window:
6cc02fd68 and d3f61b818, both pure test-file splits (launch admission, init-memory
managed agents). Neither touches glossary or memory-web code and both pass on the
integrated tree; test_init_memory_managed_agents_generation.py's "Glossary Terms" not-in
assertion still holds because glossary.md is now a user-owned descriptor, not a generated
note. There is no PR base branch: master is level with origin/master and no other refs
exist. I also checked the two downstream roots the plan names. bob-cli's local checkout
was four commits stale and still looked unmigrated; on origin/master it is already
migrated by 79b5dba (memory.glossary gone, four strand files present), so the only real
bob-cli drift was this epic's README paragraph, which I regenerated. actstat has no
glossary configuration at all.

GATES. Ran every `just check-full` gate individually: fmt (python), fmt (markdown),
keep-sorted, ruff, mypy, feature flags, pyscripts, test waits, changelog, patch/stitch
terminology, toobig, SASE validation, and committed plans all pass. Full suite via
`just test-cost`: 36781 passed, 13 skipped, 9 failed — all nine pre-existing and
dispositioned below. `just test-visual`: the 18 Config-hub goldens are green; 15 reds
remain, none in a surface this epic touches. I could not run `just check-full` end to end
because lint (symvision) aborts it on sase-tb (see below), so I ran its gates one by one
instead; symvision's failure set is byte-identical to the pre-epic set, with no entry
from this epic's files. `sase bead epic-symbols sase-sq.8.1` reports no entries.

FOLLOW-UPS (step 3). One PROPOSED FOLLOW-UP existed, on 8.1.1:
- chat_fork symvision private-import blocker: already filed as sase-tb by
  sase-sq.7.1.land. Reproduced independently on this tree and recorded a +1 (now +3)
  rather than filing a duplicate; confirmed every other whole-repo lint gate passes, so
  it is the only thing standing between this tree and a green check-full.
Issues I found myself while verifying, none caused by this epic:
- sase-tc (new, ci, small): test_tracked_marker_path_passing_sites_are_reviewed fails on
  clean master because 7318c52b7's agent_chat_from_name split moved six marker-path
  sites into _agent_chat_from_name_* submodules without updating the reviewed allowlist.
  Linked related to sase-tb, same refactor wave.
- sase-td (new, flake, small): test_plugins_pane_lazy_fetches_highlighted_latest waits on
  the enrich call marker instead of the applied entry, so it loses the race under the
  parallel lane. Failed once in two full runs, passed immediately on isolated rerun.
- Bead-CLI structured-note drift (6 test_cli_golden nodes + test_cli_search): declined as
  a duplicate. sase-sq.7.1.land already routed it to active epic sase-t2; I added one
  corroboration there confirming it still reproduces on this newer HEAD.
- test_cli_history date literal: duplicate of sase-t9, already filed. No action.
- Visual backlog: recorded a +1 on sase-r5 (now +15) with the exact post-rebaseline
  residue — 15 nodes, 14 of them Agents-tab/artifacts goldens that post-date that bead's
  original list, plus help_panel_keymaps which it already names. Sampled agents_selected_row
  and confirmed its diff is confined to the footer keybinding-hint row, matching sase-r5's
  footer/leader attribution, not anything this epic renders.
- Flake-baseline gate: `just selection-health --fail-on-new-flake` reports two nodes over
  baseline. test_default_pipe_creates_family_member_with_fork_and_shared_workspace is
  already sase-r2. test_default_config_matches_public_schema now passes on master — its
  finalizers.instances.commit.refusal 'defer' schema gap was fixed by 6a91ae88e at
  2026-08-24T20:14:47Z, and all 13 of its stored failure records predate that. That is
  exactly sase-o0's fixed-at-retirement pattern, so I recorded it there as a measured
  case with the named fix commit; the +1 took sase-o0 from snoozed to ready.

KNOWN LOOSE END, reported not swallowed: the chezmoi repo's `git pull --rebase && git
push` step inside `sase skill init` failed because ~/.local/share/chezmoi has an
unrelated uncommitted edit to home/sase/memory/sase.md (adding `priority: 10`) left by
another agent. Both of my chezmoi commits (c70d9c83 skills, 02dbc9cf memory README) are
correct and scoped to their own files, and both are applied to the live home tree, but
they sit unpushed on top of five pre-existing unpushed "chore: initialize sase memory"
commits. I did not stash another agent's in-flight work to force the push through.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sq.8.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sq.8.1.land/README.md) | [sase-sq.8.1](sase-sq.8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b592cfa`](https://github.com/sase-org/sase/commit/b592cfa5760d6f3f8c1b2f948780b0a8e25ae1cf) | fix(memory): finish retiring the config glossary across ACE and generated memory | [sase-sq.8.1](sase-sq.8.1.md) | 2026-08-25 02:53:12 EDT |
