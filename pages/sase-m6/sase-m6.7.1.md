# Bead: sase-m6.7.1 — Relations, reveal, and grouping as Artifacts contract features

[Bead Pages](../README.md) / [sase-m6.7](sase-m6.7.md) / sase-m6.7.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m6.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.7.md) · **Assignee:** `sase-m6.7.1.land`
**Created:** 2026-08-16 02:53:05 EDT
**Plan:** [202608/artifacts\_relations\_and\_grouping.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_relations_and_grouping.md)

## Description

Hierarchy, family, and link relations are declared contract facts rendered by one host-owned relation panel on every Artifacts pane; reveal is a reversible lens that never destroys a composed query; and every pane's grouping runs on the one shared GroupFoldRegistry with collapsed banners as first-class navigation targets. A sidecar that names a property gets jumpers and grouping without shipping code.

## Notes

[2026-08-16T11:31:11Z · chop.refresh_docs.sase.4_900125.1] DISCOVERED ISSUE: Grouping/fold and relation keybindings are unreachable outside the Patches pane. NON_PRS_ARTIFACT_ACTIONS in src/sase/ace/tui/actions/artifacts.py:40 was not extended when f5dda81f3 (phase .5, shared fold registry) routed h/l/H/L/o/O and a0b6cd16b (phase .3, generalized relation navigation) mounted relation navigation across panes. check_app_action therefore returns False for cycle_grouping_mode, cycle_grouping_mode_reverse, expand_or_layout, hooks_or_collapse, hooks_or_collapse_all, expand_all_folds, start_ancestor_mode, start_child_mode, and start_sibling_mode on every non-Patches Artifacts pane, so Textual skips the binding entirely. Verified against a live AcePage: on Stitches, 'o' leaves the grouping mode at by_date and '<' leaves _ancestor_mode_active False. Net effect: the shared fold registry and host-rendered relation panel both render but cannot be driven from the keyboard, and Files/Beads/Plans silently fall through to their own o/L bindings. No test covers the key path — existing tests call pane.group_cycle_mode() and the action methods directly, which is why this passed. Suggest phase .6 (Conformance, docs, and the relation performance gate) add a conformance check that every declared grouping/relation action is actually reachable per pane. Found 2026-08-16 during the docs refresh; documented as a current limitation in docs/ace.md and docs/artifacts_pane_visual_grammar.md rather than fixed, since that agent was scoped to documentation only.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m6.7.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m6.7.1.land/README.md) | [sase-m6.7.1](sase-m6.7.1.md) | 0 |
