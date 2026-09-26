# Bead: sase-17x.13 — Finish the \`:\` Command Line: fix landing-audit bugs and spec gaps

[Bead Pages](../README.md) / [sase-17x](README.md) / sase-17x.13

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17x.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17x.land.md) · **Assignee:** `sase-17x.13.land`
**Created:** 2026-09-24 20:28:39 EDT · **Closed:** 2026-09-25 21:13:49 EDT
**Plan:** [202609/command\_line\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_landing_fixes.md)

## Description

The `:` Command Line from epic sase-17x behaves as its plan specifies. Every key in the Keys table works and is configurable under `ace.keymaps.command_line`. No action crashes or silently fails. Completion reaches every candidate and every entity kind. No synchronous disk I/O runs on the UI thread. The chrome and popup match the UX specification. The missing PNG goldens exist, and CI builds a sase-core that exposes `CommandLineGrammar`.

## Notes

[2026-09-25T05:36:41Z · sase-18d.7.land] DISCOVERED ISSUE (sase-18d.7 land, 2026-09-25, master 02c4b029a, still present on origin/master c7a78904b): 'just symvision' fails with unused public CdResolution (src/sase/ace/tui/command_line/builtins.py) and PathCompletionRequest (src/sase/ace/tui/command_line/sources.py). Both were added by fad9b5d03 (sase-17x.13.6) and have no --epic-symbol entry, so every other agent's just check stops at lint (symvision). Privatize them, wire them up, or add sase-17x.13 epic-symbol entries.

[2026-09-25T12:38:34Z · sase-17x.13.land] LANDING INTERRUPTED (sase-17x.13.land, master ea130c678, 2026-09-25): remaining epic work planned as a child epic (plan command_line_landing_gaps, parent_bead sase-17x.13).
VERIFIED: all 9 phases have commits (d0df63a23 7484c50ab 543d01220 bde335de5 61f88ccd6 fad9b5d03 5b305b1b9 403586e27 3c6e8f04d); a per-bullet code audit found most plan items done; command-line + palette + keymap + completion suites 581 passed; symvision clean; no epic-symbol entries. Discovered-issue note #1 (CdResolution/PathCompletionRequest) is resolved: 403586e27 privatized both.
REMAINING (all in the child plan): Esc-on-empty-line and ';' hop deadlock (awaited dismiss() from the input's own key handler; a pilot hangs and the dismissed screen stays attached; this also explains the sase-17x.13.4 Pilot wedge and the sase-17x.13.9 screenshot timeout after hide/reopen); config_center _post_proc_focus_target call_from_thread on the loop (p never focuses the proc); grammar on_ready is lost for a screen reopened mid-load; history walk reuses the old cursor; the literal 'escape' hide; menu keys tied to the history bindings; compact key names; provider disk cache not bypassed after a finish; cd +label/+home resolution; project merge; tip marker write on the loop; ensure_block_for_proc appends from a worker thread; double history count; perf probe start stamp; screen_completion.py at 1039 lines (toobig, master-gate lint red since 3c6e8f04d); 22 stale epic goldens (16 command_line_*, 5 onboarding, help_guide_agents); test gaps.
INTEGRATION: the 25 non-epic commits since d0df63a23 (agent-session rename sase-17m.*, sase-18f green check, sase-18g, tool/triage) need no Command Line changes: no family terms remain under command_line/, cli_spec drift and contract tests pass, and run_policy covers the new flags.
FOLLOW-UPS: 17x.13.2#1, 17x.13.3#1, 17x.13.4#2, 17x.13.5#5 and 17x.13.6#1/17x.13.7#3 (tools mypy, sase-18i symvision, test-waits pragma, 34 clean-base test failures, smoke-tool mypy) declined as resolved at HEAD (mypy 4970+54 clean, symvision clean, test_query_profile_agents etc. pass). 17x.13.8#1 and 17x.13.9#2 (memory README drift) resolved by 4220fe7b7. 17x.13.5#2 and 17x.13.8#2 (visual load flake) resolved by 3c6e8f04d's loader no-op (18/18 pass in 12s). Epic-caused, now in the child plan: 17x.13.4#1 (hop wedge = deadlock), 17x.13.5#1 (goldens + doc_peek seeding), 17x.13.5#4 (disk cache), 17x.13.8#3 (compact keys), 17x.13.9#1/#3 (screenshot after hide/reopen). Routed: 17x.13.5#3 -> new memory task sase-195; 17x.13.7#2 -> +1 sase-17u; 17x.13.8#4 -> +1 sase-14o.
OTHER DISCOVERIES: +1 sase-18n (narrow usage PNGs), +1 sase-18y (fold-levels PNG), +1 sase-13a (zsh sbd flake); new flake sase-194 (Admin Center list scroll offset); DISCOVERED ISSUE on sase-17m.5.1.6 (stale agents_retry_e2e_plan_session_countdown golden from ea130c678); notes on sase-18o (owned by the child plan's goldens phase) and sase-16a. tests/tool/test_settlement.py is over toobig from sase-17p.6; declined because the toobig_split routine owns splits (sase-18h).

[2026-09-26T01:13:49Z · sase-17x.13.10.land] Closed by the sase-17x.13.10 land agent after its child epic landed.

Rechecked:
- All 9 phases (sase-17x.13.1-.9) and the child epic sase-17x.13.10 are closed. Every item on this bead's LANDING INTERRUPTED REMAINING list (note #2) was delivered by the child epic and re-verified in the code at HEAD 7cb835953: the Esc/';' dismiss deadlocks, Procs focus delivery, grammar on_ready for reopened screens, history walk reset, fixed menu keys, compact key names, the disk-cache bypass, cd +label/+home, the project merge, the tip marker write off the loop, the restored-block append on the UI thread, the double history count, the probe stamp, screen_completion.py under toobig (697 lines), the regenerated epic goldens, and the test gaps.
- The land agent also fixed a history same-prefix reset gap, command_line_empty_state and palette-tip golden nondeterminism, and the monotonic-vs-wall-clock elapsed bug in live blocks (from db99493). See the sase-17x.13.10 close note.
- Live walkthrough on the checkout build passed end to end, including a screenshot export after Esc hide and ':' reopen.
- The linked plan (command_line_landing_fixes.md) goal holds for its planned scope: Keys table, keymap scope, sources, UI-thread I/O, chrome, goldens, and the sase-core pin. One caveat: bead-ID completion is empty in live TUIs and shell completion outside agent shells because the shared provider catalog (catalog_sdd._resolve_beads_dir) cannot find the sidecar bead store. That defect predates this family, was never in the plan's entity-sources scope, and is routed as sase-19y.
- Post-child drift: origin/master through 013a17072 has no commit touching command_line code, its tests, or its goldens.
- Epic symbols: none for sase-17x.13. just symvision is clean.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.13.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17x.13.land.md) | [sase-17x.13](sase-17x.13.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-18d.7.land][1] | Check whether the active command-line epic owns the unused CdResolution/PathCompletionRequest symbols | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18d.7.land/README.md

<!-- sase:referenced-by:end -->
