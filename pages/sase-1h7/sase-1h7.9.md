# Bead: sase-1h7.9 — Wait modal toggle, CLI, Jinja, and Telegram parity

[Bead Pages](../README.md) / [sase-1h7](README.md) / sase-1h7.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3v.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3v.linker.w0.md) · **Assignee:** `sase-1h7.9` · **Size:** medium
**Created:** 2026-10-06 18:17:45 EDT · **Closed:** 2026-10-07 18:39:13 EDT
**Plan:** [202610/wait\_for\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202610/wait_for_epic.md)

## Description

surfaces: add a tri-state "Follow epics" toggle to the `w` wait modal, filter derived beads out of edits and relaunch rewrites, export the follow state in `sase agent list -j` and `sase agent wait` rows, synthesize `agents["x"].created_epic(s)` for Jinja, and show the hand-off in Telegram status text when waits are shown there.

## Notes

[2026-10-07T21:34:58Z · sase-1h7.9] PROPOSED FOLLOW-UP: symvision _runs private-import errors in agents_sync/v2_snapshot_io.py and ace/tui/widgets/decks/final/overview_card.py fail just check identically on the clean base tree; needs its own bead

[2026-10-07T21:46:08Z · sase-1h7.9] PROPOSED FOLLOW-UP: just validate red on init repo --check (beads sidecar README template drift about issues.jsonl export wording); unrelated to surfaces, refresh not run to avoid sidecar churn

[2026-10-07T22:38:08Z · sase-1h7.9] PROPOSED FOLLOW-UP: test-scoped shows 13 failures that reproduce without this phase (7 identical on clean base: 3 bead_fast_path, claimed_status, finalizers_discard_guard, app_import_budget, launch_context_bar; 6 load/order flakes passing on re-run: panel_shell_history, agy_usage_probe, prompt_key_perf, deck_block_spread, snippet shift_tab, terminate_processes); needs owner triage, none touch wait/CLI/Jinja paths

[2026-10-07T22:39:13Z · sase-1h7.9] Surfaces done and verified: tri-state Follow epics toggle in w modal (Space, Ctrl+J/K, plan-row disabled, authored-bead prefill, epic_follow_agents apply, removal prunes entries/pins beads), relaunch rewrites split for_epic=true and drop derived beads, list -j exports wait_for_epics_of/epic_follows, wait rows use shared phrasing, Jinja created_epic(s) with waiter-entry precedence, Telegram status parity. 164 focused tests green; ruff/mypy/fmt gates green; symvision+scoped deltas recorded as follow-ups (pre-existing on base).

## Dependencies

- **Blocks:** [sase-1h7.10](sase-1h7.10.md) ◐ · ⧖ 2026-10-06
- **Depends on:** [sase-1h7.6](sase-1h7.6.md) ✓ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h7.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h7.9/README.md) | [sase-1h7.9](sase-1h7.9.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5a3f8ae`](https://github.com/sase-org/sase/commit/5a3f8ae57447ed8ced231dc82e170e0834c9df3c) | feat(wait): tri-state Follow epics toggle with split for\_epic occurrences | [sase-1h7.9](sase-1h7.9.md) | 2026-10-07 19:38:28 EDT |
| sase-telegram | [`sase-telegram@15ccce3`](https://github.com/sase-org/sase-telegram/commit/15ccce3857d6802b2fe9a57e4e4d4df846dd4bf1) | feat(telegram): render wait follow suffixes on agent tokens | [sase-1h7.9](sase-1h7.9.md) | 2026-10-07 20:08:33 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h7.9][1] | Need full description and dependency state | 2 |
| read-by | [agent:sase-1h9.land][2] | Need whether CLI completion vocab is this phase's unfinished work | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h7.9/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h9.land/README.md

<!-- sase:referenced-by:end -->
