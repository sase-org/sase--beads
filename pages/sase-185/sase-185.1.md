# Bead: sase-185.1 — Pending launch lifecycle and detached relaunch waits

[Bead Pages](../README.md) / [sase-185](README.md) / sase-185.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0r6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0r6.md) · **Assignee:** `sase-185.1` · **Size:** medium
**Created:** 2026-09-24 15:03:17 EDT · **Closed:** 2026-09-24 15:57:25 EDT
**Plan:** [202609/detached\_prompt\_submit.md](https://github.com/sase-org/sase--plans/blob/main/202609/detached_prompt_submit.md)

## Description

pending-launch: add the PendingLaunch record, restore helper, pending proc row, `,X` cancel of not-yet-submitted launches, and quit-time stash; unmount the bar ahead of the relaunch-cleanup/pending-kill holds; move the synchronous post-unmount tail (MRU write, bulk Patch resolution) off the UI thread.

## Notes

[2026-09-24T19:56:46Z · sase-185.1] PROPOSED FOLLOW-UP: master is already red on unrelated gates (reproduces on a clean tree) — mypy attr-defined errors in widgets/_agent_detail_display.py and _agent_detail_state.py, symvision unused command-line-grammar symbols, toobig widgets/decks/panel.py (1051 lines), pyscripts complaining about a stale untracked tests/ace/tui/tools/__pycache__ dir, and 33 deterministic test failures (agent prompt panel, keymap help, config schema, test_app_import_budget, ...) so `just check` cannot go green for any phase until triaged

[2026-09-24T19:56:59Z · sase-185.1] PROPOSED FOLLOW-UP: detached-guards can reuse call_pending_launch_from_worker and the launch_id-keyed hold_launch_for_relaunch_cleanup/pending_launch_is_live from the pending-launch phase; _call_from_ui (provider guard) and _call_from_ui_hold_guard are duplicate thread-marshalling helpers that should collapse onto it when those guards are re-keyed

[2026-09-24T19:57:25Z · sase-185.1] Added PendingLaunch (_pending_launch.py: record, registry, launch-id-keyed stage/row/record helpers, restore_pending_launch_prompt, quit-time stash), PREPARING launch records, ProcObserver.update_pending, and ,X cancel of not-yet-submitted launches. _submit_resolved_launch now accepts (snapshot + unmount + pending row + PREPARING record) before hold_launch_for_relaunch_cleanup; barrier waiters are keyed by launch_id and dropped on cancel. MRU write and bulk Patch resolution moved off the UI thread (pump-free task / typed per-Patch plan from a non-exclusive thread worker). Rejected submits and all-failed bulk launches now restore or stash the prompt. reserve_launch_timestamp_batch measures ~0.09ms warm so it stays on the UI thread. Verified: 17 new tests in tests/ace/tui/test_pending_launch.py plus updated barrier/records/observer tests pass; just test-scoped escalated to the full lane: 46592 passed, 33 failed - all 33 fail identically on a clean tree. Lint gates pass (ruff, fmt, flags, waits, changelog, terminology, validate, committed plans, symvision has no entries for the new symbols); mypy/symvision/toobig/pyscripts failures reproduce on a clean tree and are unrelated (recorded as PROPOSED FOLLOW-UP). docs/ace.md and docs/perf_runbook.md updated.

## Dependencies

- **Blocks:** [sase-185.2](sase-185.2.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-185.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-185.1/README.md) | [sase-185.1](sase-185.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8c4f3f8`](https://github.com/sase-org/sase/commit/8c4f3f8094b9c8c968382ac4ce79e9d5cd788822) | feat(ace): accept prompt submits as pending launches (sase-185.1) | [sase-185.1](sase-185.1.md) | 2026-09-24 15:58:18 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-185.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-185.1/README.md

<!-- sase:referenced-by:end -->
