# Bead: sase-16n.11 — Close project tag (+sase) landing gaps

[Bead Pages](../README.md) / [sase-16n](README.md) / sase-16n.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-16n.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-16n.land.md) · **Assignee:** `sase-16n.11.land`
**Created:** 2026-09-23 08:51:45 EDT · **Closed:** 2026-09-23 15:40:11 EDT
**Plan:** [202609/project\_tags\_landing\_gaps.md](https://github.com/sase-org/sase--plans/blob/main/202609/project_tags_landing_gaps.md)

## Description

Finish the work the sase-16n landing audit found missing or broken in project tags. The cases are: `+home` on a fresh machine, CLI and cold-TUI tag rendering, the D7 accept parity, the LSP disabled/hover fields, the invalid rewrite-to-tag, the doctor case collisions, the red prompt-history tests, the metadata pager regression, the tag PNG goldens, the nvim picker/palette/sigil, and the docs.

## Notes

[2026-09-23T18:08:58Z · sase-16n.11.land] LANDING AUDIT (sase-16n.11.land, 2026-09-23). The landing is interrupted: the remaining epic-caused work was planned as a child epic.

VERIFIED against the code and commits:
- sase-core 4300166: items 1-7 implemented (accept regex no longer anchored to line start, empty workflow names match nothing, LSP accept uses catalog project_tags, state/workspace_dir wire fields, disabled diagnostic, modifier and hover, D1-valid rewrite-to-tag, full suggestion dedupe, collision warnings); the LSP parses through VcsProjectCatalogWire. Targeted cargo tests pass.
- sase 394a53b6d: pin, synthetic system +home (checked on an empty SASE_HOME), project_tag_for, wire fields, MRU-keyed completion cache, doctor case collisions and wording, dead-code removal, step-8 launch tests (139 targeted tests pass).
- sase b924b0350: red tests, CLI catalog warm, off-thread startup warm, editor re-highlight, pager PROJECT_TAG spans, MRU label, clan triage accents (64 targeted tests pass).
- sase 848a90a1b: fixture catalog pin (autouse, function-scoped) plus the prompt and AGENT XPROMPT tag goldens.
- sase-nvim dac30c9: picker fallback, override-preserving palette, sigil groups, README.
- docs: sase 69ca23a2e and sase-github 2b26fa3. All 11 +home first-run examples validate on an empty SASE_HOME.
- No --epic-symbol entries for sase-16n.11.

REMAINING EPIC-CAUSED WORK (planned as the child epic):
- sase-core master CI red on macOS since 4300166: the case-variant collision test creates alpha and ALPHA. This also blocks the v0.34.74 release PR.
- Accept deletes the newline after a line-end ref and joins lines. A glued match can also hide a valid ref. Pre-v5 catalogs lose accept deletions. Stale comment and dead checks.
- nvim: modifier_set uses ipairs, but Neovim >= 0.10 passes set-shaped modifiers, so no accent or sigil color ever shows. Override tracking compares only the foreground. The picker fails silently.
- sase: frozen_intent_vcs_prefix regression from the project_tag_for change (prose mentions count as prefixed). on_project_tag_catalog_warmed only calls App.refresh(), which rebuilds nothing. The pager styles unknown tags, uses the theme accent instead of D6 per-project accents, and styles tags inside md fences. The prompt-history filter calls load_project_tag_catalog on the UI thread (from sase-16n.3). The catalog cache is not reset between tests. Test gaps and docs nits.
- Integration with c6c70befc: the tribe PROMPTS chip makes up +name for Patch and owner/repo refs.
- Other commits since 08:51 were reviewed with no action needed. b3e31bb59's Ctrl+K seed is consistent with the epic. The 555025931 and 26f676fb0 splits dropped nothing.

PROPOSED FOLLOW-UP outcomes:
- sase-16n.11.3 #1 (test_load_launchable_prunes_provider_mismatched_prefix): not caused by the epic (it fails at 3844ed83d, before sase-16n). Filed as new task sase-172 (ci, large).
- sase-16n.11.4 #1 (prompt_search_count_pill_flexoki golden): the same stale prompt-search pill golden family as sase-16w, so recorded as a +1 on sase-16w.
- sase-16n.11.4 #2 (agents_retry_e2e unseeded hex IDs): a new root cause, distinct from closed sase-13v and sase-dc. Filed as new task sase-173 (flake, large).
- sase-16n.11.4 #3 (symvision ExpandedLaunchSegments): a duplicate of sase-16u, which already has 5 +1s, and no longer reproduces because caca6b60f privatized the class. Noted on sase-16u as closable; no +1.

Other discoveries, not caused by this epic:
- Symvision is red on ClanSummaryDigest: DISCOVERED ISSUE note on active epic sase-170.
- The link-toast scope line shows raw project keys: DISCOVERED ISSUE note on sase-16t.
- 'sase artifact link rm' fails with 'observed_operation_ids must not be empty': DISCOVERED ISSUE note on sase-yy.8.6.
- The sase-16n.11.6 remark about the sase-github check being blocked by a pre-existing dep-pin failure was not a formal proposal and was not pursued.

[2026-09-23T19:40:11Z · sase-16n.11.7.land] Resumed after child epic sase-16n.11.7 closed. Rechecked: all 6 phases and child epic closed; every REMAINING EPIC-CAUSED item from landing audit #1 (macOS core test, accept line-join/glued/pre-v5, nvim set modifiers/override tracking/picker, follow-up prefix regression, warm refresh rebuild, pager accents/unknown/fences, history-filter UI-thread load, test cache reset, tribe PROMPTS chip integration, test gaps, docs nits) verified in sase-core fb1ca29 (CI green incl. macOS, pinned), sase-nvim 9378313, sase 1230ed8da and 00badb84e. Post-child drift (master commits since 14:10) reviewed: no tag integration needed. The 11 red bead-work/completion-snapshot tests caused by project_tag_for returning unknown names unchanged were fixed in the sase-16n.11.7 landing (pinned tag catalog in tests/test_bead/conftest.py, synced completion snapshot). No epic-symbol entries. just symvision still red only on other epics' symbols (ClanSummaryDigest/sase-170, llm_provider usage capability cache/_probe_meta, plugins browser mark_all_message).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16n.11.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-16n.11.land.md) | [sase-16n.11](sase-16n.11.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16n.11.5][1] | parent epic context | 1 |
| read-by | [agent:sase-16n.11.7.land][2] | Parent plan bead: review descendants, notes, and linked plan for close | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.11.5/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.11.7.land/README.md

<!-- sase:referenced-by:end -->
