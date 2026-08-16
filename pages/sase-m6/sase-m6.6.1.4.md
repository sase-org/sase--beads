# Bead: sase-m6.6.1.4 — Namespace durable query state by pane

[Bead Pages](../README.md) / [sase-m6.6.1](sase-m6.6.1.md) / sase-m6.6.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m6.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.6.md) · **Assignee:** `sase-m6.6.1.4` · **Size:** medium
**Created:** 2026-08-15 06:18:00 EDT · **Closed:** 2026-08-15 07:56:33 EDT
**Plan:** [202608/unified\_artifacts\_query\_1.md](https://github.com/sase-org/sase--plans/blob/main/202608/unified_artifacts_query_1.md)

## Description

persistence: replace the global saved-query, history, and selection stores with pane-keyed records containing source text, canonical text, profile digest, and ArtifactEntryTarget tokens; add safe read-time migration and write-then-read validation while retaining legacy files until success, surface stale-profile saved views as editable errors, and route slots, pickers, history, help, startup, and selection restore through the active pane without switching tabs.

## Notes

[2026-08-15T11:45:17Z · sase-m6.6.1.4] PROPOSED FOLLOW-UP: `sase monitor start` fails with FamilyAttachError ("Cannot create agent family 'sase-m6.6.1': resolved parent is named 'sase-m6.6.1.7'") when invoked from an sase-m6.6.1.4 agent — src/sase/agent/_family_promotion.py:131 promote_agent_to_family raises instead of resolving the family from the calling agents own bead lineage. Blocks routing just check/just check-full through /sase_monitor for any agent under this epic; worked around by running just check in the foreground/background shell instead.

[2026-08-15T11:56:33Z · sase-m6.6.1.4] Namespaced saved-query, query-history, and query-selection persistence by pane_id, keyed on the active pane's compiled query-profile digest with ArtifactEntryTarget tokens for selections. Added safe read-time migration of legacy flat-format files (lifted under the 'patches' pane_id) plus write-then-read validation, and surfaced stale-profile records as editable errors instead of dropping them. Rewired slot actions, the saved-query picker, prev/next history navigation, help-modal sections, startup loads, and selection restore to route through the active pane without switching tabs; the CLI default-query resolution in parser_ace.py still resolves the 'patches' pane. Verified: unit tests test_saved_queries.py, test_query_history.py, test_query_selection.py, and the frozen-format goldens in test_persistence_goldens.py all pass against both legacy and namespaced fixtures; TUI behavioral suites (test_saved_query_slot_keys.py, test_saved_query_picker.py, test_search_query_panel_cache.py — confirming SearchQueryPanel still never hits disk on a mounted app — plus the PNG visual snapshot) pass unchanged. Ran 'just check': all lint gates (fmt, ruff, mypy, pyscripts, symvision, keep-sorted, toobig, changelog, terminology) green, and the scoped test lane (634/2654 files) passed with exit code 0.

## Dependencies

- **Depends on:** [sase-m6.6.1.1](sase-m6.6.1.1.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-m6.6.1.5](sase-m6.6.1.5.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-m6.6.1.6](sase-m6.6.1.6.md) ✓ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m6.6.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m6.6.1.4/README.md) | [sase-m6.6.1.4](sase-m6.6.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`368e8f6`](https://github.com/sase-org/sase/commit/368e8f66479170f3c4f977369130daa5a8178eab) | feat(ace): namespace durable query state by pane | [sase-m6.6.1.4](sase-m6.6.1.4.md) | 2026-08-15 07:57:13 EDT |
