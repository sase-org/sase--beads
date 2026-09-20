# Bead: sase-zr.7 — Close out sase-zr: decision integrity, honest status, and fast TUI gate refresh

[Bead Pages](../README.md) / [sase-zr](README.md) / sase-zr.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.07](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.07.md) · **Assignee:** `sase-zr.7.land`
**Created:** 2026-09-16 14:25:08 EDT · **Closed:** 2026-09-20 13:01:08 EDT
**Plan:** [202609/sase\_zr\_close\_out.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_zr_close_out.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/sase_zr_close_out.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/sase_zr_close_out.md

<!-- sase:links:end -->

## Description

The narrowed sase-zr close-out holds end to end: an accepted gate decision can never be superseded while its execution runs, any post-acceptance failure is durable and recoverable instead of invisible, TALE/EPIC APPROVED derives from the receipt while PLAN COMMITTED waits for archive success, the TUI paints gate responses on exact rows promptly from every source, Telegram rejects strangers and TTY-only options, and every deliberately deferred audit gap is tracked by a ready task bead so the land agent can close sase-zr.

## Notes

[2026-09-19T12:05:54Z · sase-zr.7.1.1.5.4.land] LANDING HANDOFF from sase-zr.7.1.1.5.4.land: nested decision-integrity work is complete. Closed sase-zr.7.1.1.5.4, sase-zr.7.1.1.5, and sase-zr.7.1.1; phase sase-zr.7.1 auto-closed (delegated work landed). Stopped here because this containing epic is still incomplete: phases 7.2, 7.3, and 7.5 remain in_progress. Waiting land agent should resume those phases; do not treat 7.1 as a blocker.

[2026-09-20T17:01:08Z · sase-zr.7.land] LANDED by sase-zr.7.land on 2026-09-20.

VERIFIED (step 1). Read this epic's note #1 and every child bead and note: phases
7.1-7.5 plus the whole nested 7.1.1 tree (7.1.1.1-.4, 7.1.1.5, 7.1.1.5.1-.3,
7.1.1.5.4, 7.1.1.5.4.1-.2). Each note's claims were checked against current source
and against the ten commits carrying SASE_BEAD=[sase-zr.7*] (934be032d, 26797a95a,
1d14218a3, df0090f04, e91fa138b, cc6d51d2d, 8989d0a72, bfc6142fc, 244442ee8,
96b913333), plus sase-telegram 24900c0 and 4d20559.

- decision-integrity (7.1 via 7.1.1): notification_gates/execution_owner.py,
  failure_outcome.py (stages command / terminal_prepare / side_effects / follow_up),
  failure_notifications.py and the journal/poller/reclaim consumers are all in tree.
  1336 passed / 3 skipped across tests/gate_shell/, tests/gate_conformance/ and every
  tests/test_gate*.py, test_notification*.py, test_plan_approval*.py,
  test_plan_archive*.py.
- approval-projection (7.2): notification_gates/approval_projection.py is read by
  decision.py::_project_accepted_decision, the _meta_enrichment_gate loader,
  plan_approval_actions.py::project_plan_committed and failure_outcome.py, so the
  receipt-derived label reaches every load path and rolls back on archive failure.
  gate_shell/settlement.py::publish_gate_shell_terminal_state publishes terminal state
  and the pulse before follow-up launch, guarded by
  test_refresh_pulse_runs_before_followup_launch.
- ace-fast-refresh (7.3): shells/settlement.py::touch_agent_refresh_pulse plus the
  _artifact_paths classifier, the off-loop receipt watcher, disappearance detection
  before cache replacement, run_off_loop, and GateRetryModal wired from both
  _notification_gate_recovery.py and _notification_gate_execution.py. 233 passed
  across the ACE notification/gate suites.
- telegram-auth (7.4): verified in the linked sase-telegram checkout at 24900c0 --
  the chat/sender check ahead of every handler, requires_tty hidden in
  render_gate_keyboard and rejected pre-submission, and "source": "telegram" on the
  submission payload.
- verify-close (7.5): docs/notifications.md and sase-telegram docs/inbound.md +
  README corrected and pushed.

REMAINING EPIC WORK, NOW FINISHED. Phase 7.5 explicitly landed with "NOT DONE: fresh
before/after latency p50/p95 evidence was not captured". I captured it with a
throwaway probe (the committed reusable probe stays descoped per the plan), recorded
method and numbers on sase-zr.7.5 note #3, and committed them to docs/notifications.md
in 24cbeb882. Acceptance receipt to Agents row data: broad tier-1 load p50 74.8 /
p95 123.4 ms vs exact artifact-dir delta p50 1.7 / p95 2.5 ms, n=25 on a
1,500-artifact fixture, with the classifier confirming the old project-level pulse
named no row and the new agent-dir pulse names the exact one. Response publication to
refresh-pulse visibility: p50 407.5 / p95 450.8 ms before vs p50 97.7 / p95 130.3 ms
after, n=10 behind a 150 ms follow-up-launch barrier. That closes the sase-zr landing
audit's gap 11 remainder.

INTEGRATED (step 2). Reviewed every non-epic commit from 934be032d to HEAD that touches
a file this epic touched. The workspace was 8 commits behind origin/master, so I
fast-forwarded to 598f1e820 and re-verified there.

- 624a29ea7 (service git readiness) adds GateAdapter.preflight_decision into
  execute_gate_selection, ahead of acceptance and skipped once a response is published.
  It composes with, rather than contradicts, this epic's rule that a failure after
  acceptance must be durable: it moves a knowable archive-credential failure to before
  acceptance so the gate stays pending. No change needed.
- 511a6c5ae (pending TALE/EPIC/QUESTION status on the toast tick) landed an hour after
  7.3 and consumes 7.3's machinery correctly: it resolves dirs on the poll worker and
  feeds them through the same artifact-delta queue via
  request_notification_agents_refresh, with no second event-loop resolve and no forked
  refresh path. No change needed.
- 49e2eeed9 (executor split), 7179ec2e2, 6e06a3e24, 76df54778, e98ef5b1c, 37f0651d6
  and 9f9f0d6f1 all touch epic files but land cleanly; the failure-outcome, journal and
  sudo paths they moved still carry the epic's contract, proven by the 1336-test gate
  suite above.
- 86ff62c08 and 45df42549 removed the symvision and mypy failures phase 7.5 had
  reported as pre-existing.
- sase-telegram: no drift on the epic's files since 24900c0.

VERIFICATION. At 598f1e820 + 24cbeb882: fmt (python), fmt (markdown), keep-sorted,
ruff, mypy (now clean after 45df42549), feature flags, pyscripts, test waits, changelog,
patch/stitch terminology, toobig, SASE validation and committed plans all pass.
just test-scoped: 43754 passed, 23 skipped, 5 failed. just check itself stops at lint
(symvision) on sase-13s, so the remaining gates were run individually. Every one of the
5 test failures and the symvision failure is a filed non-epic bead (below); none touch
gate, approval-projection or ACE refresh code. just check-full was not run: this prompt
did not authorize it.

FOLLOW-UP DISPOSITIONS. The only PROPOSED FOLLOW-UP entry among this epic's children is
sase-zr.7.5 note #1, which bundled four items:
1. mypy no-untyped-def in src/sase/main/ace_tmux*.py -- DECLINED as already fixed.
   sase-13k was closed by 45df42549; mypy is green here (4679 files, 0 errors).
2. symvision private-misuse in ace_tmux_support.py / memory/selector_models.py --
   DECLINED as already fixed by 86ff62c08 (sase-13l closed). Its successor error class,
   28 unused publics in sdd-clone / runner-slot / service-host / completion split
   modules, is sase-13s; CORROBORATED with +1 carrying my reproduction at 598f1e820.
3. sase-telegram tests/test_receiver.py 15 failures -- NEW TASK sase-13z (ci, small,
   ready). Root-caused: 2f76876 (sase-11y.6) added a _service_host_owns_receiver()
   early return to ensure_receiver_running, and the 15 tests never neutralize the
   ambient service_host flag or service config, so the function returns None before
   submitting. Reproduced on a clean telegram tree at 4d20559 against sase 6087c0a8e
   and 598f1e820.
4. just test-cost hung >2h -- duplicate of sase-xc; relayed as a prose note there
   rather than a +1, because I did not re-run it myself.

Phase 7.3's note also listed three failures it judged unrelated. All three reproduce
here and are now corroborated: test_capacity_gate_to_admission x2 on sase-13o (+1),
test_changed_query_incomplete_load_after_reconcile_rearms on sase-13n (+1), and
tests/tool/test_executor.py::test_literal_argv_preserves_spaces_and_dashes, which had
no bead -- NEW TASK sase-140 (ci, small, ready): it execs the literal name "python",
absent on this host, so the child never starts and the recipe exits 127.

One further failure surfaced only after the fast-forward: the contract manifest is
stale again in the opposite direction, because 58f2de8f8 deleted the contract marker
from tests/test_tool_adoption_report_tool.py without refreshing the manifest that
5023214db had just updated. CORROBORATED on sase-13m with +1, including the correction
that the bead's stated direction is now backwards.

NOT CONFIRMED, RECORDED HONESTLY. The ace-fast-refresh phase was asked to confirm the
j/k p95 16 ms benchmark. pytest -s -m slow tests/ace/tui/bench_tui_jk.py failed 8 of 10
scenarios here, but the host sat at load average 19.75 on 16 CPUs with a concurrent
rustc/cc1 build, so these wall-clock key-to-paint numbers carry no signal. Open bead
sase-lx documents exactly this confound on the same benchmark and says to re-measure on
a quiet host before concluding a regression, so I did not file a duplicate. The
deterministic guards covering the same contract do pass: 76 tests across
tests/perf/test_agents_display_rebuild_guard.py,
tests/ace/tui/test_event_handlers_auto_refresh_dirty_flags.py,
tests/ace/tui/test_axe_status_read_cache.py and
tests/test_notification_toast_polling_agent_refresh.py, including the quiet-tick
no-reload guard.

Deferred-by-owner scope is untouched and still tracked: sase-11v, sase-11w, sase-11x.
sase bead epic-symbols sase-zr.7 reports no entries. Landing now passes to parent
sase-zr for its narrowed-contract re-verification.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-zr.7.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-zr.7.land/README.md) | [sase-zr.7](sase-zr.7.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`24cbeb8`](https://github.com/sase-org/sase/commit/24cbeb8826eadbd4227e1f7c61314c04f4dfd907) | docs(notifications): record before/after latency evidence for the two gate-refresh paths | [sase-zr.7](sase-zr.7.md) | 2026-09-20 12:56:54 EDT |
| sase--plans | [`sase--plans@632085a`](https://github.com/sase-org/sase--plans/commit/632085a0821b96df3ba396b6a8f9c34e40c13913) | docs(plans): mark the gate-approval epics done | [sase-zr.7](sase-zr.7.md) | 2026-09-20 13:11:35 EDT |
