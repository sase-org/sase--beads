# Bead: sase-y5.12 — Recover and land the sase-y5 usage-context surface

[Bead Pages](../README.md) / [sase-y5](README.md) / sase-y5.12

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-y5.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-y5.land.md) · **Assignee:** `sase-y5.12.land`
**Created:** 2026-09-09 06:11:31 EDT · **Closed:** 2026-09-09 09:03:45 EDT
**Plan:** [202609/usage\_context\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_context_recovery.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/usage_context_recovery.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/usage_context_recovery.md

<!-- sase:links:end -->

## Description

Re-implement the lost sase-y5.10 capacity-hint wiring from the recovered artifact and clear the sase-y5 release residue so the subscription-capacity epic can close.

## Notes

[2026-09-09T13:03:45Z · sase-y5.12.land--1] Land verification: both phases landed and were re-verified against source. sase-y5.12.1 (cef06cdca) restored usage/hints.py and usage/peek.py, re-exported provider_usage_window_applies/provider_usage_summarize_for_model through usage/_facade.py and usage/store.py, and wired scoped capacity hints into model_picker_rows/model_picker_options, alias-member detail in models_panel_rendering_descriptions, and quiet usage attention into provider_disables_indicator (off-event-loop peek worker, provider-scoped click into action_open_provider_usage). sase-y5.12.2 (d165fbbaa) fixed timestamp_label so a future verbose reset drops the (0s ago) suffix, baselined the sase-yq pager flake, and added the Subscription Usage section to docs/agent_providers.md. No provider_usage_metrics/override_flags residue remains, and the declared sase-core-rs floor 0.32.50 carries every provider_usage_* binding the epic uses, which retires the sase-y5.4 and sase-y5.7 floor-ratchet follow-ups.

GATE OUTCOME, STATED PLAINLY: the monitored `just check-full && just test-visual` run (b16fy3zcmdcv, 29m36s) exited 1. `just check-full` itself PASSED in full - every lint gate, SASE validation, committed plans, test cost, and the flake baseline - and the failure was entirely in `just test-visual`, which is a separate lane that check-full does not include. It reported 35 failed / 862 passed / 1 skipped.

I triaged all 35 rather than accepting or rebaselining any of them:
- 2 were contention flakes: re-running only the 35 failing node IDs on the unchanged tree gave 33 failed / 2 passed. The two that flipped were test_models_panel_usage_120_columns_png_snapshot (this epic's own golden, a one-cell State column narrowing that renders `exhausted` as `exhaust` with every other cell identical) and test_agents_context_zoom_modal_png_snapshot.
- The remaining 33 are deterministic and are NOT caused by this epic. I proved it rather than asserting it: I reverted the epic's entire src/ diff with `git checkout 4068437a2 -- src/` (the only non-memory commits in that range are this epic's own d165fbbaa and cef06cdca) and re-ran the same 33 node IDs. All 33 failed identically against pre-epic source. The tree was then restored to HEAD exactly.
- Root causes I identified are stale goldens from other landings, not renderer drift: the 7 axe_* goldens predate the `Spawns/min: / No-op: / Skipped:` row that 9ed0f11b7 (sase-wn.10) added; update_panel_pending and update_panel_unchecked still render the agents-sync import option that 61d72860a (sase-ws.1) deleted, which no current tree can reproduce; and models_panel_runner_limit_action still reads `%wait(runners=N)` where ff6271e53 (sase-yj.4) renamed it to `%queue(runners=N)`. I deliberately did not run `--sase-update-visual-snapshots`, since that would silently accept three other epics' unreviewed rendering changes.

Targeted re-verification of this epic's own surface: 50 targeted tests across usage hints/peek/store-bindings/picker/alias/indicator/presentation, both epic PNG suites, `just symvision` clean, and `sase bead epic-symbols sase-y5.12` empty.

Integration: reviewed every commit that landed after this epic opened (00b8f0216 star-alias completion panel, ff6271e53, 4068437a2, and four memory commits); none duplicate or conflict with the usage-context surface, and the prompt completion panel state column is routing provenance, explicitly outside the usage-context phase contract. This workspace is 3 commits behind origin/master (27bbd2f4e, 1852f091a, a1b08d06c); I read their diff and none touches subscription usage, ACE visual goldens, or any file this epic changed.

Follow-ups recorded:
- The one PROPOSED FOLLOW-UP (sase-y5.12.2 note 1, tests/pager/test_syntax_activation.py importing a missing tests.pager.test_app) was declined as already fixed. Verified at HEAD: the file imports no tests.pager.test_app and collects 8 tests cleanly in 2.98s; ff6271e53 rewrote that import to tests.pager._app_helpers about 75 minutes before the note was written, so the phase worker was reading a stale workspace. A bead for the same defect already existed (sase-ym), so I recorded that verification as a note there instead of filing a duplicate.
- The 33 deterministic visual failures are a semantic duplicate of sase-x5 (residual test-visual golden drift, previously 29 nodes). Corroborated with `sase bead +1` carrying the reproduction, the reverted-src proof, and the three named commit causes, which redirect that bead away from its font/renderer-drift hypothesis. Now at +2 reports.
- test_agents_task_bead_notes_png_snapshot is NOT golden drift: it fails a hard `assert "Size:" in svg_plain` and never reaches the PNG comparison, with the Size row missing from the zoomed BEAD lane even though _agent_bead_section._rows emits it for a task summary with size set. Filed as sase-yu (task(ci), small) with a related link to sase-x5.
- The epic's own flaking golden was filed as sase-yv (task(flake), small) rather than buried, since it is this surface's snapshot. The unrelated test_agents_context_zoom_modal flake is recorded in the sase-x5 +1 rather than given its own bead.

Landing also removed a write-only _peek_path global and its unused Path import from the recovered peek.py; that cleanup was present on the tree for the passing check-full run.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-y5.12.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-y5.12.land.md) | [sase-y5.12](sase-y5.12.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2e30cf4`](https://github.com/sase-org/sase/commit/2e30cf499691e1f35bdf90950cc72f69d1c5d947) | refactor(usage): drop the write-only peek path global | [sase-y5.12](sase-y5.12.md) | 2026-09-09 09:25:23 EDT |
