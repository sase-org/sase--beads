# Bead: sase-123.7 — Complete the screenshot and inline-memory contracts

[Bead Pages](../README.md) / [sase-123](README.md) / sase-123.7

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-123.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-123.land.md) · **Assignee:** `sase-123.7.land`
**Created:** 2026-09-17 21:13:49 EDT
**Plan:** [202609/complete\_tui\_screenshots.md](https://github.com/sase-org/sase--plans/blob/main/202609/complete_tui_screenshots.md)

## Description

Live TUI captures reliably address and clean up their own window, remote captures preserve arguments across SSH, and inline memory reads render each target once with complete agent workflow guidance.

## Notes

[2026-09-18T04:00:52Z · sase-123.7.land] LANDING AUDIT at 80336097ad on 2026-09-17/18: leaving sase-123.7 open and its linked plan unchanged because reproduced epic work remains. Read this epic (no previous notes), every child and all eight child notes, both approved plans via audited reads, actual source/tests, all five epic commits, and post-start drift. Fetched origin/master equals HEAD. Durable audit: file:explicit:e8b9c4338d74ab54ee9e348b.

VERIFIED: one packaged renderer and shared test facade/font fingerprint; 273 renderer/glyph/fingerprint tests pass. Normal unique local IDs, metadata recovery, two real isolated tmux windows, keep/recapture, resize/metadata cleanup, shell-boundary capture/cleanup, multi-root inline body dedup, and top-level listing suppression have passing coverage. The 117 focused launcher/capture/export/memory/report/gate tests all pass. No governed check-full pass is claimed because the epic is not ready to land.

REMAINING EPIC WORK: (1) _claim_window reserves and performs list-windows/new-window before its exception guard. Injecting TimeoutExpired after server-side creation leaks a window and claim, makes zero cleanup calls, and exposes raw TimeoutExpired. Startup and wait-regex polling lose known pane text if the next capture subprocess times out. (2) Remote metadata drops sase_tmux_target=@42 and reconstructs a display-name target, losing phase 2 ownership semantics. The send-keys hint still quotes only the outer shell, so the remote SSH join reinterprets target/key boundaries. Screenshot memory tells agents to copy sase_tmux_window while describing a unique identity; correct that to sase_tmux_target within the already approved memory scope. (3) A root embedding a child hides that child's unread grandchild from Markdown/Rich/single-note JSON; batch JSON still lists a nested grandchild that it also embeds because suppression only rewrites roots. (4) Real Textual App reproduction exports BEFORE while a finite visual worker is still running and later paints AFTER. Ignoring every worker misses finite selected-detail work; waiting for all recurring workers is also wrong. An unset refresh Event outlives a patched 50ms settle deadline until an outer 250ms cancellation, leaving screen_1.pending. Bound awaited refresh work and meaningful finite visual completion.

INTEGRATION: reviewed df0090f040, 6e06a3e24c, e91fa138b0 after the first epic commit, plus 76df54778f after epic creation. Preserve gate/core failure IDs, restart decisions, recovery notifications, and newer Agents capacity/attention/load/fleet/search/group/detail behavior. No competing screenshot renderer or new consumer needs migration. Remote unique-target propagation is required integration with this epic's local identity change.

EVERY PROPOSAL: sase-123.7.1 note 1 (empty attempt_id fixtures) is fixed in df0090f040; all three named tests now pass, and active gate epic sase-zr.7.1.1.5 already tracked the issue. Declined a new task as resolved. sase-123.7.1 note 2 and sase-123.7.5 note 1 are one visual backlog report: used sase_new_task, all-status ci searches, last-week ci sweep, active epics and plausible children; corroborated existing sase-x5 (+11), and recorded causal golden-integration evidence on active sase-126. Fresh named node test_agent_list_png_snapshot differs by 2756 pixels: actual adds (p) to view: file and shifts group hint; expected omits it. Old and current rasterizers produce identical actual bytes. This independently confirms one node plus inherited 107/106 phase counts, not a common cause for all failures. Do not blanket-regenerate. Actual file:explicit:89b3629330021159e922d710; expected file:explicit:a276711d01074f55e3581a95. Preserve the original parent's sase-123.1 proposal already forwarded to sase-x5 (+10).

SIDE ISSUE: immutable artifact snapshots were created, but --bead attachment failed with the known dirty hidden plans clone. Used existing bug searches/sweep and corroborated sase-10y; refs remain in this note and the plan. No foreign hidden-clone edits.

WHITELIST: sase bead epic-symbols sase-123.7 and sase-123 both report no entries. No close attempted, no force, no canonical memory/source/accepted-plan edits. Prepared remaining-only four-phase plan sase_plan_screenshot_residual_contracts.md with parent_bead=sase-123.7. It covers launch exceptions/diagnostics, retained remote identity and corrected authorized guidance, nested memory listings, and finite visual settling plus integrated acceptance. The child handoff preserves this landing and original parent sase-123. After the child lands, re-read descendants/notes/plans and drift, run governed full verification, resolve epic work, and close normally only when ready; then post-close symvision and linked-plan status, followed by the user's direct-plan-ancestor readiness/close procedure. Closure/status duties are not child phases.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-123.7.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-123.7.land.md) | [sase-123.7](sase-123.7.md) | 0 |
