# Bead: sase-d9.7 — Documentation, footer, and end-to-end coverage

[Bead Pages](../README.md) / [sase-d9](README.md) / sase-d9.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.r3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.r3/README.md) · **Assignee:** `sase-d9.7` · **Size:** small
**Created:** 2026-08-01 12:39:51 UTC · **Closed:** 2026-08-01 15:13:23 UTC
**Plan:** [202608/clan\_summary\_view\_hints.md](https://github.com/sase-org/sase--plans/blob/main/202608/clan_summary_view_hints.md)

## Description

polish: update the ace docs and help popup for clan view hints, audit hint numbering against the member jump gutter, add the clan keypath to the view-hints perf harness, and cover the whole `v` flow on a clan with an app-level test.

## Notes

[2026-08-01T15:12:22Z · sase-d9.7] PROPOSED FOLLOW-UP: hint markers split URLs — the epic clan summary hint golden shows [2] inserted mid-URL inside the hosted bead page link (https://github.com/sase-[2]org/sase--beads/...), and it maps to a fabricated workspace-relative path; FILE_PATH_RE / the shared hint appender should skip path tokens inside http(s) URLs (affects agent and family renders too, so it is a separate change).

[2026-08-01T15:12:41Z · sase-d9.7] PROPOSED FOLLOW-UP: `just view-hints-perf-check` fails on master independently of this epic — the `large_reply_repeat_press` and `hint_mode_auto_refresh` steps report annotated_chars=102541 instead of 0, so the ordinary-agent repeat press is rescanning the annotated document instead of reusing the cached hint render; verified by stashing all clan work and re-running.

[2026-08-01T15:12:57Z · sase-d9.7] Fixed in passing: tests/ace/tui/widgets/test_agent_display_clan_context_hints.py tripped the pyscripts Rule 2 path linter on the literal "sase_beads" skill name (pre-existing `just check` failure from the context phase); now uses the same split-string constant the clan display helpers already use.

[2026-08-01T15:13:23Z · sase-d9.7] Docs: documented clan v hint behavior (sources, fold-level dependence, gutter separation, enrichment race) in docs/ace.md Clan and Family Detail Panels and updated the Agents-tab v keymap row. Help popup: v entry now reads 'Hint files/tools/commits/clans' (30 chars, was 34 and silently truncated). Footer: unchanged — _keybinding_bindings.py clan branch untouched, so the clan footer set is identical. Numbering audit: new widget test builds a 12-member clan with 12 summary paths and asserts the CLAN MEMBERS roster block is byte-identical with and without hints and carries no [N] markers; the new hint-mode PNG golden (agents_clan_panel_epic_hints_120x40) confirms the 0-9 gutter is untouched while [1]/[2] annotate the summary. Perf: added clan_container_press to tests/perf/tui_trace/view_hints.py with a 5-member / 8 KB-summary fixture (make_hint_clan_container), a clan_container flag on the hint-render trace span, and three absolute-only gates (view_files p50 <= 30 ms, hint render p50 <= 65 ms, annotated_chars <= 40k) with no max_baseline_ratio; the frozen baseline is unchanged. Measured 1.9 ms / 5.7 ms / 7592 chars over 3 runs, well clear of the ceilings and off the unbounded-repr path. End-to-end: tests/ace/tui/actions/test_view_files_clan_hints.py drives the real mixins over a real clan render — press v, submit '1', pager opens the resolved summary path — plus the enrichment race, submitting before the deferred render publishes and asserting it waits on _agent_hint_render_ready and still resolves, with no 'No files or commits found' warning. just check green and just test-visual green (401 passed, 1 skipped). Two pre-existing issues recorded as PROPOSED FOLLOW-UPs (hint markers splitting URLs; view-hints-perf-check gates already failing on master for the ordinary-agent repeat press).

## Dependencies

- **Depends on:** [sase-d9.2](sase-d9.2.md) ✓
- **Depends on:** [sase-d9.3](sase-d9.3.md) ✓
- **Depends on:** [sase-d9.4](sase-d9.4.md) ✓
- **Depends on:** [sase-d9.5](sase-d9.5.md) ✓
- **Depends on:** [sase-d9.6](sase-d9.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-d9.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-d9.7/README.md) | [sase-d9.7](sase-d9.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`624db9a`](https://github.com/sase-org/sase/commit/624db9a9f7baf4545451cd460a026684198a34f1) | docs(ace): document clan view hints and cover the clan \`v\` flow | [sase-d9.7](sase-d9.7.md) | 2026-08-01 15:15:01 |
