# Bead: sase-1eq.5.1 — TUI macro surfaces and goldens

[Bead Pages](../README.md) / [sase-1eq.5](sase-1eq.5.md) / sase-1eq.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.5.md) · **Assignee:** `sase-1eq.5.1.land`
**Created:** 2026-10-03 13:29:42 EDT · **Closed:** 2026-10-04 23:24:43 EDT
**Plan:** [202610/tui\_macro\_surfaces.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_macro_surfaces.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/tui_macro_surfaces.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/tui_macro_surfaces.md

<!-- sase:links:end -->

## Description

Rename the SASE TUI's xprompt modules, identifiers, CSS, copy, keymap actions, and Admin Center ids to macro spellings. The agent prompt tab and headings say raw prompt. Pre-rename resume state still opens, retired keymap actions stay flag-gated aliases, and the PNG goldens match the new pixels.

## Notes

[2026-10-04T20:21:49Z · sase-1fv.land] DISCOVERED ISSUE: During implementation of the existing-definition catalog fix, targeted just fix-tui-screenshots runs repeatedly timed out at tests/ace/tui/visual/test_ace_png_snapshots_existing_finder.py::test_existing_snippet_finder_png_snapshot waiting for the TODO sentinel. The last frame showed the snippet finder open with the first gh plugin row selected and GitHub snippet body in Preview; both TODO rows were visible lower in the match list, so the sentinel does not describe the default selected preview. Likely update the fixture to select todo or wait for the current plugin preview. Three retries failed in each run; the snippet golden remained untouched. This is in scope for the active TUI macro surfaces and goldens work.

[2026-10-04T21:00:37Z · 50--c] -d 🔒 sase-1eq-prompt-precedence-note.md

[2026-10-05T03:24:43Z · sase-1eq.5.1.land] LANDED by sase-1eq.5.1.land at master 404b0e2ac2.

VERIFIED (step 1): All six phases are closed. Phase commits: c3914fb7c1 (tui-browser), e7408ed219 (tui-completion), 781bb0e7ae (tui-prompt-copy), 6320828878 (tui-sweep), 404b0e2ac2 (tui-goldens). tui-contracts (sase-1eq.5.1.1) has no commit of its own. Its keymap and stats-request work reached master in 6320828878, so no feat!/BREAKING CHANGE footer for the three keymap actions exists in history. The behavior is verified in source:
- legacy_xprompt_syntax.RETIRED_KEYMAP_ACTIONS and normalize_keymap_actions are wired through keymaps/registry_app.py and scopes.py: flag-gated, and both spellings error in both flag states.
- default_config.yml and the schema use focus_macro, clear_macro_focus, and start_last_vcs_macro_in_editor.
- Config hub sub-tab and Statistics view ids are macros, with unconditional xprompts readers. Top-level xprompts still maps to config.
- stats/query.py sends macro_top_n, macro_breakdown_top_n, and macro_focus.
- PREVIEW_TAB_LABEL is "RAW PROMPT", with 20 AGENT RAW PROMPT sites.
- No tracked PNG golden or TUI module name contains xprompt. All 887 golden names the visual tests reference exist (905 tracked).
- The remaining TUI-scope xprompt hits (45 files) are classified: legacy readers or imports, resume migrations, and pre-flip wires.
- The terminology guard covers the TUI trees.
Epic note #1 (sase-1fv.land snippet finder sentinel) was fixed in 404b0e2ac2 with initial_query="todo". Epic note #2 (50--c, private attachment sase-1eq-prompt-precedence-note.md, body "-d [...]") could not be reviewed: the attachment is unavailable offline, has no shared-store object and no local file, and 50--c left no chat transcript. The same note sits on parent sase-1eq.5. 50--c was a restart-wait verification agent, and its note text carries no actionable scope.

INTEGRATED (step 2): aeccf84357 (sase-1fv land, after tui-sweep) added a legacy-config-key test, tests/ace/tui/modals/test_mini_macro_target_catalog.py. Once tui-goldens widened the guard over tests/ace, its three literals failed test_macro_string_literals_avoid_xprompt_terms at HEAD. Fixed by allowlisting the two classified legacy-input literals with a per-file reason in tests/_macro_terminology_string_pairs_a_late.py and tests/_macro_terminology_strings.py. The guard plus contract suites then passed 190 tests. Other post-start commits (existing-definition finder flow, macro arg parenthesis, restart, deck) are guard-clean and need no changes.

CHECKS: sase tool run check 4c482e611c702f4e57eb3c29b94e3444: every lint stage passed, including symvision and mypy. The full lane ran 52,599 passed with 3 NEW failures, none caused by this epic: machine bootstrap help (new sase-1gd), test_agents_row_fit (passed in isolation; +1 sase-1g2), test_fast_failure_matches_inline_with_tail (passed in isolation; +1 sase-1fi). j/k bench (pytest -s -m slow tests/ace/tui/bench_tui_jk.py): 10 passed, 7 failed. That is the same set tui-goldens reproduced on a clean base, so there is no navigation regression. epic-symbols: none.

FOLLOW-UP TRIAGE:
- 5.1.1#1 browser_load_keymap: declined. sase-pe is closed and the renamed test_macro_browser_load_keymap.py passes.
- 5.1.1#2: declined for parser_root_help, export_save, and gate_turn followup, which pass at HEAD (fixed by bca08d1242). The prompt_tab_focus_steal part got +1 on sase-1fy, with a deterministic serial two-file repro.
- 5.1.1#3 mypy EntryPoints.get and symvision discover_macro_plugin_entry_points: declined. Both are clean at HEAD.
- 5.1.2#1: superseded by #3 (Config hub is Macros/#macros, verified).
- 5.1.2#2 sticky epic widget: declined. It passes at HEAD.
- 5.1.3#1 and #3, 5.1.6#2 (FrontmatterPanel NoMatches nodes test_app_title and test_artifacts_limit_keys ctrl_j): folded into the sase-1fy +1. Same frontmatter_panel.py:206 stack, and both pass in isolation, so no separate node-specific beads.
- 5.1.3#2: +1 sase-1fn, with a serial order-dependent repro.
- 5.1.4#1 (docs families/ and KillProvenance): declined. Already tracked (sase-1fs, sase-1fv.4, sase-1g0), and the guard and symvision are clean now.
- 5.1.5#1 and #3, 5.1.6#1 (JinjaScopeKind, completion spacer binding, xprompts_used, stats response keys): owned by in-progress core-flip sase-1eq.10. Recorded a pointer note on sase-1eq.10 listing the adapters.
- 5.1.5#2 (PNG goldens): completed by 5.1.6.
- 5.1.5#4 (Justfile sase-1fv.5 epic symbols): declined. No epic-symbol entries remain, and sase-o7 tracks the systemic guard.
- 5.1.5#5 KillProvenance: declined, tracked by sase-1g0 and clean now.
- 5.1.5#6 and 5.1.6#2 machine bootstrap help: created sase-1gd (ci, small).
- 5.1.6#2 bench: +1 sase-lx (selected-tribe p95) and +1 sase-199 (axe tab set). Created sase-1ge (fleet fault p95, ci, large) and sase-1gf (clan and link-rail stall records, ci, large). Output-variable PNG: declined, already tracked by sase-1bb and not re-run.

## Attachments

- 🔒 sase-1eq-prompt-precedence-note.md · text/markdown · 1.05176 KiB (private attachment)

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.5.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.5.1.land/README.md) | [sase-1eq.5.1](sase-1eq.5.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cddd30c`](https://github.com/sase-org/sase/commit/cddd30c515923b444d0d2d472ec4ffdd915a0778) | test(terminology): allowlist legacy-key literals in mini-macro catalog test | [sase-1eq.5.1](sase-1eq.5.1.md) | 2026-10-04 23:27:32 EDT |
| sase--plans | [`sase--plans@d2863db`](https://github.com/sase-org/sase--plans/commit/d2863db27631ad1dfb2344c21f5a7bc95a696f49) | chore(plan): mark sase-1eq.5.1 TUI macro surfaces epic done | [sase-1eq.5.1](sase-1eq.5.1.md) | 2026-10-04 23:32:28 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.5.1.land][1] | Need the epic scope, children, and linked plan file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.5.1.land/README.md

<!-- sase:referenced-by:end -->
