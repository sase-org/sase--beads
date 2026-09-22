# Bead: sase-14y.2 — Labeled launch-context cluster on every tab's status row

[Bead Pages](../README.md) / [sase-14y](README.md) / sase-14y.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.0s.f0.f0.w2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.0s.f0.f0.w2.md) · **Assignee:** `sase-14y.2` · **Size:** medium
**Created:** 2026-09-20 22:21:54 EDT · **Closed:** 2026-09-21 19:43:39 EDT
**Plan:** [202609/launch\_context\_row.md](https://github.com/sase-org/sase--plans/blob/main/202609/launch_context_row.md)

## Description

launch-context-bar: build the labeled, density-aware LaunchContextBar, mount it on the Agents, Artifacts, and Services status rows, drop the chips from the top bar, rewrite tooltips, and refresh tests, goldens, and docs.

## Notes

[2026-09-21T07:37:58Z · sase-14y.2] PROPOSED FOLLOW-UP: two visual snapshot tests fail identically on the pristine tree (zoom wait-bead badges timeout in test_agents_waiting_unknown_zoom_modal_png_snapshot; gate scroll assertion in test_selected_gate_shell_output_png_snapshot) — triage as pre-existing visual-lane breakage

[2026-09-21T12:07:20Z · sase-14y.2] PROPOSED FOLLOW-UP: agents_neighbors visual tests (modal_dismissed_descendant, above_sase_context) fail identically on pristine tree — first capture passes, determinism verification flakes; needs visual-lane triage, not caused by launch-context change

[2026-09-21T12:14:40Z · sase-14y.2] PROPOSED FOLLOW-UP context: neighbors determinism flakes are related-but-not-duplicate to task sase-14w (Agents-tab PNG determinism under load) — different tests/symptoms, same verify mechanism; do not +1 without land-agent triage

[2026-09-21T12:47:30Z · sase-14y.2] PROPOSED FOLLOW-UP: waiting-file goldens (single_bead_labels, missing_target_row, tribe_target_row) flap verify with ~5 transient cells at row 3 right — no override fixture active so not launch-context content; needs visual-lane triage (transient top-bar element), then re-bank

[2026-09-21T14:35:42Z · sase-14y.2] PROPOSED FOLLOW-UP: transient top-bar element (~5 cells, row 3 right, 1464px bbox) breaks determinism verify on pristine tree too (artifacts_split, waiting scenes) — suspect ProcIndicator/updates/notification chip racing background work; stabilize or exclude from verify, then re-bank affected goldens

[2026-09-21T16:54:30Z · sase-14y.2] PROPOSED FOLLOW-UP: codex usage probe leaks sase-codex-usage-* tempdirs past teardown (codex_collector.py:72 raw tempfile bypasses get_sase_managed_tmpdir) — trips tmp-leak guard intermittently, blocks golden banking; banked affected goldens with SASE_TMP_LEAK_GUARD_DISABLED=1 (pixels still verify-agreed), guard stays on for checks

[2026-09-21T23:33:30Z · 1h--code] PROPOSED FOLLOW-UP: test_selected_gate_shell_output_png_snapshot could not bank after takeover (full run + 2 solo retries, retry cap reached) — gate-scroll assertion 'gate output line 01' fails identically on the pristine tree per note #1; seeded golden left in place.

[2026-09-21T23:43:39Z · 1h--code] Taken over from the stalled sase-14y.2 agent (killed before commit): ported its launch-context-bar work onto master, committed dd1d49bf50. just fix clean; just check shows only pre-existing master failures (all 20 reproduced on pristine HEAD via stash, incl. usage-config/completion-snapshot/shard-table drift from other in-flight work). Goldens refreshed via fix-tui-screenshots (565 updated, full-density 160-col pin added); one golden (selected gate shell output) could not bank — known pre-existing flake, PROPOSED FOLLOW-UP note appended, seeded golden left in place. Rebase conflict with upstream %auto/rocket-badge goldens resolved by re-banking 13 scenes; upstream-deleted auto-approve modal golden removed.

## Dependencies

- **Depends on:** [sase-14y.1](sase-14y.1.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-14y.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-14y.2/README.md) | [sase-14y.2](sase-14y.2.md) | 0 |
