# Bead: sase-s9 — Procs tab query filtering

[Bead Pages](../README.md) / sase-s9

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0bh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0bh.md) · **Assignee:** `sase-s9.land`
**Created:** 2026-08-23 08:01:34 EDT · **Closed:** 2026-08-23 12:37:04 EDT
**Plan:** [202608/procs\_filter.md](https://github.com/sase-org/sase--plans/blob/main/202608/procs_filter.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | [bead:sase-sb][1] | Discovered when sase-s9.2 skipped /sase_final and entered a poll/wait loop |
| related | [bead:sase-sh][2] | Proposed as a PROPOSED FOLLOW-UP by phase sase-s9.6 while porting the flat grammar to Rust; the epic's parity tests are what exposed the divergence, and extending those tests is part of the fix |

[1]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-sb/README.md
[2]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-sh/README.md

<!-- sase:links:end -->

## Description

The Admin Center Procs tab has a slash-revealed query bar backed by a real, shared query dialect: free text matches a proc's command and output, closed `key:value` filters cover monitor/running/status/runtime/completion-time, every term negates with `-`, boolean keys have a bare shorthand, and `m` cycles the monitor filter on, inverted, and off.

## Notes

[2026-08-23T14:59:19Z · 0bs] DISCOVERED ISSUE: just _lint-symvision (and therefore just check lint) fails on unused public symbol ProcsFilterBar in src/sase/ace/tui/modals/procs_filter_bar.py. Reproduction: just _lint-symvision. The class is referenced from src/sase/ace/tui/styles.tcss and tests/ace/tui/widgets/test_procs_filter_bar.py but from no non-test Python file, so Symvision treats it as unused. This workspace's Justfile already whitelists sase-s9(ProcQueryFilter), sase-s9(proc_query_row), and sase-s9(query_needs_output), but not ProcsFilterBar. Closed phase sase-s9.3 owned adding the widget and Admin Center key integration; closed sase-s9.4 owned the pane filter session. Remaining in-progress phases are sase-s9.5 (m monitor-filter cycle) and sase-s9.7 (docs/visual). Confirmed not caused by the home-task-types-note work: that tree only touches init_memory, task_types, docs, and tests around task_types.md. Fix belongs on this epic: either import/compose ProcsFilterBar from the Admin Center Procs pane (matching PatchFilterBar), add --epic-symbol sase-s9(ProcsFilterBar) until a later phase consumes it, or add a # symvision: src/sase/ace/tui/styles.tcss pragma if CSS is the intended lasting consumer.

[2026-08-23T15:12:02Z · sase-s8.land] DISCOVERED ISSUE (already fixed, no action needed from sase-s9): the Justfile carried a stale `--epic-symbol "sase-s9(ProcQueryFilter)"` exemption. Commit 2e0ac0f37 (feat(ace): wire Procs filter bar into pane) gave ProcQueryFilter a real consumer in src/sase/ace/tui/modals/procs_pane_filter.py, so symvision started refusing the entry with "symbol 'ProcQueryFilter' is already properly used. Remove this unnecessary --epic-symbol entry." and `just check` went red at lint for every agent in the repo. Reproduction: `just symvision` at HEAD 2e0ac0f37. I removed only that one line while landing epic sase-s8, because the gate blocked my own landing; `just symvision` is now clean. The two remaining sase-s9 entries (proc_query_row, query_needs_output) are untouched and still needed. sase-s9's land agent should re-run `sase bead epic-symbols sase-s9` as usual and not be surprised that one entry is already gone.

[2026-08-23T15:18:21Z · 0bt] DISCOVERED ISSUE: Independent corroboration during unrelated remove_legacy_commit_command verification. just _lint-symvision fails: --epic-symbol sase-s9(ProcQueryFilter): symbol ProcQueryFilter is already properly used. Remove this unnecessary --epic-symbol entry. Reproduction: just _lint-symvision or just check (after mypy). Confirmed not caused by this tree: Justfile is unmodified. I did not fix it; remaining in-progress phases are sase-s9.5 and sase-s9.7, and closed sase-s9.1 owned the query grammar types.

[2026-08-23T16:37:04Z · sase-s9.land] LANDED epic sase-s9 (Procs tab query filtering) at master HEAD 062ae22c2 plus this
landing's own diff.

VERIFIED (step 1). All 7 phases closed and their work confirmed in the source, not just
in their notes. sase-s9.2, .3, and .4 were closed by another agent with "the agent forgot
to close this bead" and carried no closing note, so they were verified entirely from
code:

- grammar (sase-s9.1, commit dcbf570d5): HOST_DATE_BOUND_KEYS / HOST_DURATION_BOUND_KEYS
  in query_profile/registry.py, the bare-flag branch in the flat parser, the bound-key
  direction lookups in the evaluator and normalizer, and the highlighter branch.
- dialect (sase-s9.2, commit ab0260376): procs_query_schema() in
  query_profile/profiles.py matches the plan's field table exactly (text/cmd/out/name/
  agent/project/status/kind/monitor/running/failed/exit/min/max/after/before/since/until/
  limit); status: and kind: source PROC_STATUS_CHOICES / PROC_KIND_CHOICES from
  sase.main.parser_proc rather than duplicating them; src/sase/ace/tui/_proc_query.py
  holds the row adapter, the 32 KB output tail cap, the needs-output AST gate, and the
  version-keyed row cache.
- bar (sase-s9.3, commit 3d2065412): ProcsFilterBar with SHOW_WHEN_ACTIVE,
  FORWARD_ARTIFACTS_PAGING = False, and the procs teal accent; consume_priority_tab()
  consulted from config_center_modal.py:271.
- pane (sase-s9.4, commit 2e0ac0f37): ProcsPaneFilterMixin with the committed/live query
  split, restore-on-dismiss, limit: capping, and ProcsSessionState.query for
  cross-open persistence.
- monitor (sase-s9.5, commit 7db3ea954): toggle_flag_token plus the m cycle.
- rust (sase-s9.6): landed in the linked sase-core repo as commit aeefa36, released as
  v0.31.7. Verified against the installed sase_core_rs 0.31.7, not just by reading:
  tests/test_query_profile_corpus_facade.py passes 31/31 including the bare-flag and
  bound-key parse/canonicalize parity parameters.
- polish (sase-s9.7, commit 37abe195b): docs/ace.md "Filtering procs" section with the
  full key table and the worked example, the / and m keybinding rows, the
  config_center_procs_tab_filtered_120x40 PNG golden (which passes), and the / and m
  rows in the Procs help-modal section.

Ran the epic's own suites green: 213 tests across tests/ace/tui/test_proc_query.py,
tests/ace/tui/test_procs_pane_filter.py, tests/test_filter_tokens.py,
tests/test_query_profile_reference.py, tests/test_profile_highlighting.py,
tests/test_query_profile.py, and tests/test_query_profile_corpus_facade.py.

EPIC BEAD NOTES, all three addressed:
- 0bs (unused public ProcsFilterBar): resolved. Commit 2e0ac0f37 gave it a real non-test
  consumer; procs_pane.py:26 imports it and procs_pane.py:98 mounts it.
- sase-s8.land and 0bt (stale --epic-symbol sase-s9(ProcQueryFilter)): already removed by
  sase-s8.land in commit 42b900fa1. Confirmed absent.

INTEGRATED (step 2). Reviewed all 20 non-epic commits from dcbf570d5^ to HEAD. No commit
landed since this epic started touches the shared query stack, the procs schema, or the
Procs pane -- the only ACE files any of them touched are Agents-tab surfaces
(agent_family_members.py, agent_groups/_keys.py, agent_time.py, and the agent-list render
cache and layout). Checked specifically that 1d00fb2c4 (direct typed proc launches) added
no proc kind or status the procs schema's enums would need, and that 0c648e033
(group stand-alone proc shells under their project) is already matched by the row
adapter, which indexes project: on both the project key and its resolved display name.

Two integration defects were found and fixed as part of this landing:

1. Commit 1d00fb2c4 reverted commit 42b900fa1's rename from a stale base, putting
   _is_terminal_state back in src/sase/agent/wait_watch/_types.py while
   wait_watch/__init__.py still imports and re-exports is_terminal_state. That was a live
   ImportError on master -- src/sase/agents/_wait_live_rows.py:19 imports it, so
   "sase agent wait" live rendering was broken -- and it failed just check at mypy for
   every agent in the repo. Restored the public name.
2. --epic-symbol sase-s9(proc_query_row) and sase-s9(query_needs_output) were retired
   properly rather than merely deleted. Both had only in-file and test consumers, so per
   the Symvision decision hierarchy they were privatized to _proc_query_row and
   _query_needs_output (step 2, "make it private", not step 4, "whitelist"), their in-file
   callers and tests updated, and both dropped from __all__. sase bead epic-symbols
   sase-s9 now reports no entries.

FOLLOW-UPS. Five PROPOSED FOLLOW-UP entries were collected from the child beads; every
outcome is recorded here.

- sase-s9.6, flat AND operand order: FILED as task sase-sh (bug, medium, ready), linked
  related to this epic. Confirmed real and confirmed NOT caused by this epic: Python's
  flat parser sorts AndExpr operands by key while Rust preserves first-seen order, and it
  reproduces on long-standing Stitches fields (repo:x author:y) that the epic never
  touched. Canonical form and evaluation agree, so nothing is user-visible; the cost is
  that the parity suite cannot assert parse-AST equality for multi-field queries.
- sase-s9.6, just check fmt and symvision failures: DECLINED as already fixed. just check
  now passes every gate including fmt (python) on launch_admission.py and symvision on the
  wait_watch and cli_duration helpers.
- sase-s9.6, 8 unrelated failures in the core-identity-changed full suite: DECLINED as no
  longer reproducing. This landing's just check escalated to the full suite twice; the
  named areas (xprompt directive completion parity, CLI completion snapshot key order,
  agents help wrapping, TUI sase-update confirm timeout) were all green.
- sase-s9.7, sase validate / init memory --check reporting 7 files out of sync: DECLINED
  as already fixed. sase memory init --check now reports "SASE is initialized. No init
  subcommands need to run.", and just check's SASE validation gate passes.
- sase-s9.7, just test-visual PNG pixel drift: CORROBORATED on existing ready task sase-r5
  (now +14) rather than filed anew, since sase-r5 is the standing record for
  "just test-visual is red on master". Re-measured at 363 failed / 425 passed (sase-r5 was
  filed at 37 failed) and contributed evidence that argues against its current
  "stale goldens from recent UI landings" root cause: binning changed_ratio across the 481
  diff artifacts gives 62 below 0.01%, 96 at 0.01-0.1%, 272 at 0.1-0.5%, 40 at 0.5-2%, and
  only 10 above 2%, and the pass/fail split tracks each golden's write date rather than
  which UI code changed -- every Procs and Agents golden regenerated 2026-08-23 passes
  while the ones written 2026-08-21 fail at ~0.43%. Not caused by this epic, which added
  exactly one golden, and that golden passes.

One further follow-up was discovered during this landing:

- tests/test_models_panel_edit_outcomes.py::test_on_alias_edited_offers_commit_when_in_repo
  failed as the sole failure of a 36432-test full parallel lane, then passed in isolation
  and 3/3 under xdist. CORROBORATED on in-progress task sase-oh (now +8), which already
  tracks exactly this node as a full-lane flake. No new bead.

VERIFICATION. just

… and 302 more characters

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-s9.1](sase-s9.1.md) | Bare boolean flags and host bound keys in the shared flat grammar | ✓ closed | medium | 2026-08-23 | 1 | 1 |
| [sase-s9.2](sase-s9.2.md) | Procs query profile and row adapter | ✓ closed | medium | 2026-08-23 | 0 | 1 |
| [sase-s9.3](sase-s9.3.md) | Procs filter bar widget and Admin Center key integration | ✓ closed | small | 2026-08-23 | 1 | 1 |
| [sase-s9.4](sase-s9.4.md) | Procs pane filter session | ✓ closed | medium | 2026-08-23 | 1 | 1 |
| [sase-s9.5](sase-s9.5.md) | The \`m\` monitor-filter cycle | ✓ closed | small | 2026-08-23 | 1 | 1 |
| [sase-s9.6](sase-s9.6.md) | Mirror the shared grammar extensions in sase-core | ✓ closed | medium | 2026-08-23 | 1 | 2 |
| [sase-s9.7](sase-s9.7.md) | Documentation, visual snapshot, and copy review | ✓ closed | small | 2026-08-23 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-s9: Procs tab query filtering [closed]"]
    n1["sase-s9.1: Bare boolean flags and host bound keys in the shared flat grammar [closed]"]
    n2["sase-s9.2: Procs query profile and row adapter [closed]"]
    n3["sase-s9.3: Procs filter bar widget and Admin Center key integration [closed]"]
    n4["sase-s9.4: Procs pane filter session [closed]"]
    n5["sase-s9.5: The `m` monitor-filter cycle [closed]"]
    n6["sase-s9.6: Mirror the shared grammar extensions in sase-core [closed]"]
    n7["sase-s9.7: Documentation, visual snapshot, and copy review [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n1 -.-> n2
    n1 -.-> n6
    n2 -.-> n3
    n3 -.-> n4
    n4 -.-> n5
    n5 -.-> n7
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-s9.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s9.1/README.md) | [sase-s9.1](sase-s9.1.md) | 1 |
| [bbugyi200.athena.sase-s9.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s9.3/README.md) | [sase-s9.3](sase-s9.3.md) | 1 |
| [bbugyi200.athena.sase-s9.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s9.4/README.md) | [sase-s9.4](sase-s9.4.md) | 1 |
| [bbugyi200.athena.sase-s9.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s9.5/README.md) | [sase-s9.5](sase-s9.5.md) | 1 |
| [bbugyi200.athena.sase-s9.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s9.6/README.md) | [sase-s9.6](sase-s9.6.md) | 2 |
| [bbugyi200.athena.sase-s9.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s9.7/README.md) | [sase-s9.7](sase-s9.7.md) | 1 |
| [bbugyi200.athena.sase-s9.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s9.land/README.md) | [sase-s9](README.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`dcbf570`](https://github.com/sase-org/sase/commit/dcbf570d53a3b8e705955b9729df84672f1abb7c) | feat(query): add flat boolean flags and bounds | [sase-s9.1](sase-s9.1.md) | 2026-08-23 08:55:48 EDT |
| sase | [`ab02603`](https://github.com/sase-org/sase/commit/ab0260376c0af00e8b6042c4dc7651145c1b0748) | feat: Procs query profile and row adapter (sase-s9.2) | [sase-s9.2](sase-s9.2.md) | 2026-08-23 09:41:21 EDT |
| sase | [`f0b932c`](https://github.com/sase-org/sase/commit/f0b932c9d5ce3880cc793f9252a7b4eb56f22c30) | test(query): cover Rust parity for bare flags and bound keys | [sase-s9.6](sase-s9.6.md) | 2026-08-23 09:41:27 EDT |
| sase-core | [`sase-core@aeefa36`](https://github.com/sase-org/sase-core/commit/aeefa360c80ac12c7cc7684ee4988f745c14038e) | feat(query): port bare-boolean flags and host bound keys | [sase-s9.6](sase-s9.6.md) | 2026-08-23 09:43:40 EDT |
| sase | [`3d20654`](https://github.com/sase-org/sase/commit/3d2065412ca76bd7fd706655ec91c21c29f59c67) | feat(ace): add Procs filter bar with priority-tab handoff | [sase-s9.3](sase-s9.3.md) | 2026-08-23 09:58:41 EDT |
| sase | [`2e0ac0f`](https://github.com/sase-org/sase/commit/2e0ac0f37c0dafb6e5ef3afc2c213abae9058d15) | feat(ace): wire Procs filter bar into pane with empty-state and count messaging | [sase-s9.4](sase-s9.4.md) | 2026-08-23 10:40:57 EDT |
| sase | [`7db3ea9`](https://github.com/sase-org/sase/commit/7db3ea954ea0b971ba6db4d6d5d2e4f2fe29c213) | feat(ace): bind m to cycle the Procs monitor filter | [sase-s9.5](sase-s9.5.md) | 2026-08-23 11:23:54 EDT |
| sase | [`37abe19`](https://github.com/sase-org/sase/commit/37abe195b91db320983f9a450859d5f3c4b768f0) | docs(ace): document Procs tab filtering and add filtered PNG snapshot | [sase-s9.7](sase-s9.7.md) | 2026-08-23 11:48:51 EDT |
| sase | [`2882047`](https://github.com/sase-org/sase/commit/2882047e2dfcf63beb7b6132767332b223f00b70) | fix(query): retire the sase-s9 symvision exemptions and restore is\_terminal\_state | [sase-s9](README.md) | 2026-08-23 12:39:34 EDT |
