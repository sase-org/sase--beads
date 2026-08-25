# Bead: sase-sq.7.1 — Glossary migration to a core web

[Bead Pages](../README.md) / [sase-sq.7](sase-sq.7.md) / sase-sq.7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-sq.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-sq.7.md) · **Assignee:** `sase-sq.7.1.land`
**Created:** 2026-08-24 18:15:34 EDT · **Closed:** 2026-08-24 23:00:59 EDT
**Plan:** [202608/glossary\_memory\_web.md](https://github.com/sase-org/sase--plans/blob/main/202608/glossary_memory_web.md)

## Description

The `sase` and `bob-cli` glossaries stop living in `memory.glossary` and become file-backed core memory webs: `sase/memory/glossary.md` is a user-owned descriptor with a managed roster region, each term is a strand file under `sase/memory/glossary/`, the Rust glossary source wire addresses strand files so editor go-to-definition lands on a real Markdown note, config and files can never both be live, and `sase glossary *` survives one release as a deprecating alias over `sase memory`.

## Notes

[2026-08-25T01:45:34Z · toobig-40.test_test_cost.0] DISCOVERED ISSUE: During unrelated tests/test_test_cost.py split verification on 2026-08-24T21:45:26-04:00, just check passed fmt, Ruff, mypy, feature-flag, pyscripts, test-waits, changelog, and terminology gates, then failed at lint (symvision). Symvision reported unused public symbols: add_glossary_strand and delete_glossary_strand in src/sase/glossary/web_mutation.py, and glossary_project_root in src/sase/glossary/compat.py. My diff only moves tests/test_test_cost.py into tests/test_test_cost_*.py and does not touch src/sase/glossary. This appears causally tied to active phase sase-sq.7.1.6, which is migrating the sase and bob-cli glossaries to file-backed memory webs; no new task bead created.

[2026-08-25T01:47:06Z · toobig-40.test_ratchet_core_window_tool.0] CORROBORATION: During unrelated tests/test_ratchet_core_window_tool.py split verification on 2026-08-24, just check reached the same lint (symvision) failure: unused public add_glossary_strand and delete_glossary_strand in src/sase/glossary/web_mutation.py, and glossary_project_root in src/sase/glossary/compat.py. Reproduced independently via git stash on plain master (commit f22f11307) with the identical symvision invocation, confirming it is not diff-specific. My diff only touches tests/test_ratchet_core_window_tool*.py and tests/contract_manifest.txt. No new task bead created; routing here per the existing DISCOVERED ISSUE note attributing this to active phase sase-sq.7.1.6.

[2026-08-25T02:04:32Z · toobig-41.project_mutations.0] CORROBORATION: During src/sase/bead/_project_mutations.py split cleanup verification on 2026-08-24, just check passed fmt, keep-sorted, Ruff, mypy, feature-flag, pyscripts, test-waits, changelog, and patch/stitch terminology gates, then failed at lint (symvision). Symvision reported unused public add_glossary_strand and delete_glossary_strand in src/sase/glossary/web_mutation.py plus glossary_project_root in src/sase/glossary/compat.py. The local diff only touches src/sase/bead/_project_mutations_*.py, so this corroborates the existing glossary migration blocker rather than the bead mutation split.

[2026-08-25T02:15:48Z · toobig-41.agent_chat_from_name.0] CORROBORATION: During unrelated src/sase/scripts/agent_chat_from_name.py split verification on HEAD 6ef21dc02, focused agent_chat_from_name tests passed (57 passed), and just check passed fmt, markdown fmt, keep-sorted, Ruff, mypy, feature-flag, pyscripts, test-waits, changelog, and patch/stitch terminology gates before failing at lint (symvision). After fixing the split's private-import findings, just _lint-symvision now deterministically reports unused public add_glossary_strand and delete_glossary_strand in src/sase/glossary/web_mutation.py plus glossary_project_root in src/sase/glossary/compat.py. The local diff only touches src/sase/scripts/agent_chat_from_name.py and the new src/sase/scripts/_agent_chat_from_name_*.py split modules, so this corroborates the existing glossary migration blocker rather than the chat resolver split.

[2026-08-25T03:00:59Z · sase-sq.7.1.land] LAND VERIFICATION (sase-sq.7.1.land, master df956212b, tree clean at start).

VERIFIED (step 1). Read all six phase beads and every note; all six are CLOSED with
resolution done, and each phase's reported work is present in the source, not just in
its note. Epic commits: af27e67e0 (wire), 2b16a0648 (source), ec889f587 (compat),
f7aa438ba (migrate), df956212b (trees); phase roster (sase-sq.7.1.2) landed earlier as
2450497bb, which is why it has no commit of its own. The sase-core half of wire landed
separately as 151a37d and is published as v0.32.3 (c0958b0).

Spot-read the actual code rather than trusting the notes:
- sase-core crates/sase_core/src/glossary.rs declares GLOSSARY_WIRE_SCHEMA_VERSION = 2
  with source_path / key_path / keyword_range / body_range and serde aliases for every
  v1 name, so a v1-shaped payload still deserializes.
- memory/web/catalog.py::glossary_source_from_wire is the single tolerant reader and
  falls back v2 -> v1 key by key, as the published-floor constraint requires.
- roster.py's inline branch now derives Rust display_aliases via strand_glossary_catalog,
  md_escapes keyword and aliases, and wraps at markdown_print_width(); the list branch is
  untouched.
- glossary_catalog.py::_load_editor_glossary_catalog and init_memory/glossary.py::
  load_project_glossary_terms both route through glossary_dual_source_diagnostic, so the
  fail-closed dual-truth rule is one predicate used by both, exactly as planned.
- The planned deletions are gone from src/ and tests/: _glossary_collision_blocker,
  _retired_glossary_note_paths, is_generated_glossary_memory_content, and the
  GENERATED_GLOSSARY_MARKER_* / sase_generated: glossary marker.
- No epic test is marked contract and tests/contract_manifest.txt is untouched by any
  epic commit, so the release-core-floor-smoke job cannot see a v2-only assertion.

Proved the migration end to end rather than re-reading its tests:
- sase/sase.yml has no memory.glossary; sase/memory/glossary/ holds 39 strands;
  sase/memory/glossary.md is the user-owned descriptor (type: core, web: true,
  roster: inline, GLOSSARY TERMS, strand_noun: term, closure: mentions).
- git show df956212b -- sase/memory/glossary.md confirms the plan's central acceptance
  criterion: the **GLOSSARY TERMS:** block is byte-identical across the migration; only
  frontmatter and the preamble's command name changed.
- find_memory_web + memory_web_glossary_entries return 39 entries whose source_path is
  the strand file and whose keyword_range points at the keyword: frontmatter line, so
  editor go-to-definition lands on a real Markdown note.
- sase memory read glossary:stitch and sase glossary read Stitch produce the same closure
  and bodies; sase glossary read/list print their one-line deprecation notice on stderr
  and delegate. sase memory web list shows glossary with 39 strands.
- bob-cli: verified through a sase repo open checkout. The migration landed on
  origin/master as 79b5dba with 4 strands, the memory.glossary block removed, and its
  roster line byte-identical; sase memory init --check is clean against that tree. The
  local primary bob-cli checkout is simply behind origin, which is not epic work.
- sase memory init --check is clean here, and just validate passes every SASE gate,
  which retires phase sase-sq.7.1.1's 'home memory init drift' PROPOSED FOLLOW-UP.

INTEGRATED (step 2). Reviewed all 21 non-epic commits since af27e67e0. None conflict with
or duplicate this epic: 9c7c10aa2 and 69dc50a31 touch xprompt/ACE but not the glossary
catalog, and the rest are test splits, axe/ACE fixes, or bead refactors. One real
interaction found and resolved: f7aa438ba had duplicated _combine_mutation_outcomes into
two bead submixins to clear a symvision finding, and e7eafd0ec later replaced that with a
public shared helper; the current tree carries only e7eafd0ec's version. The epic's own
symvision debt (add_glossary_strand, delete_glossary_strand, glossary_project_root,
reported four times on this bead) was already resolved by privatizing them in df956212b:
epic-symbols is empty and symvision is clean over the whole tree once the unrelated
chat_fork package is excluded.

FIXED AS EPIC WORK. sase memory web migrate glossary emitted the descriptor preamble as
one 414-character line: the template preamble is unwrapped and the generated-note path
used to wrap it via format_generated_memory_markdown, but migrate.py dropped that step.
This repo's copy only looks right because prettier reflowed it; bob-cli, which has no
markdown gate, carries the 414-character line in a committed core memory note.
_descriptor_preamble now wraps at markdown_print_width(), which reproduces this repo's
committed preamble byte for byte, with a regression assertion that every descriptor line
fits the print width. Not fixed: reflowing bob-cli's already-committed
sase/memory/glossary.md, because editing a sase/memory/*.md note needs the owner's
explicit permission, which this turn does not carry. It is cosmetic only - bob-cli runs
no prettier gate and the managed roster region is unaffected.

FOLLOW-UPS (step 3). Every PROPOSED FOLLOW-UP on the six phase beads was dispositioned:
- Bead CLI structured-note drift, proposed four times (7.1.3 n1, 7.1.4 n1, 7.1.5 n2,
  7.1.6 n1-n2): reproduced on clean master (8 failed / 75 passed across
  test_cli_golden.py, test_cli_history.py, test_cli_search.py) and confirmed unrelated to
  the glossary - the search failure expects the pre-structured-notes rendering. Routed as
  a CORROBORATION note onto active epic sase-t2 (Timestamped bead notes), which already
  carried two DISCOVERED ISSUE notes for it. No new task bead.
- The history date-literal node inside that set (7.1.6 n2): already filed as sase-t9 and
  already cross-linked to sase-sq.7.1.3. Declined as a duplicate.
- symvision _combine_mutation_outcomes (7.1.5 n1): already filed as sase-ta and already
  fixed on master by e7eafd0ec. Recorded that on sase-ta so triage does not redo it.
- home memory init drift (7.1.1 n1): resolved; just validate is green.
- Full-suite plan approval hang (7.1.1 n2): did not reproduce -
  test_combined_tale_approval_to_coder_link_lifecycle passes in 5.64s (2 passed).
  Declined for lack of a reproducible failure rather than filed on one agent's
  interrupted run.
- Ratchet the sase-core-rs floor after release (7.1.1 n3): the release exists
  (v0.32.3) and tools/ratchet_core_window --report shows 0.31.12 -> 0.32.3 pending.
  Recorded as evidence on sase-so.5.1, the active phase bead that owns the ratchet,
  together with sase-sq.5's warning that ratcheting past 0.32.0 before sase-t2 lands
  would pull the bead-notes-schema break into the published-floor smoke job.
Two issues I found myself, neither caused by this epic:
- sase-tb (new, ci, small): just check is red at lint (symvision) on master because the
  chat_fork pac

… and 959 more characters

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sq.7.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sq.7.1.land/README.md) | [sase-sq.7.1](sase-sq.7.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d9341f2`](https://github.com/sase-org/sase/commit/d9341f2366a7b1cc16db3a9212aed97c772bf793) | fix(memory): wrap the migrated glossary descriptor preamble | [sase-sq.7.1](sase-sq.7.1.md) | 2026-08-24 23:05:35 EDT |
