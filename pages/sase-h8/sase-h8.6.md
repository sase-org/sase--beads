# Bead: sase-h8.6 — Fix the ACE fixture-state and cross-test-leakage family

[Bead Pages](../README.md) / [sase-h8](README.md) / sase-h8.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.v5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.v5/README.md) · **Assignee:** `sase-h8.6` · **Size:** medium
**Created:** 2026-08-07 18:05:44 EDT · **Closed:** 2026-08-07 22:47:38 EDT
**Plan:** [202608/parallel\_suite\_flake\_class.md](https://github.com/sase-org/sase--plans/blob/main/202608/parallel_suite_flake_class.md)

## Description

fixture: fix the triaged ACE nodes whose injected fixture state is overwritten by a queued repaint or leaks across tests, by making state injection settle-verified and the affected panes isolated per test.

## Notes

[2026-08-08T01:49:50Z · sase-h8.3] TRIAGE (from sase-h8.3): the phase-triage table is research:202608/parallel_suite_flake_triage.md, committed to the research sidecar. It measures family membership at master 47b9f0017 and corrects the epic plan in several places, including the family your phase owns. Read it before starting; see also the sase-h8.3 bead notes.

[2026-08-08T02:44:47Z · sase-h8.6] MEASURED: pre-fix contention baseline at master 050c9477c (SASE_CONTENTION_REPEAT=6, 26 workers on CPUs 0,1) over tests/ace/tui/test_agent_metadata_search.py: 4/6 commit_repeat_q_and_passthrough, 3/6 reverse_key_override, 3/6 yank_and_frozen_refresh; red repeats 3,4,5,6. Post-fix soak of the same files plus tests/ace/tui/test_artifacts_files_detail.py: 0 nodes failed across 6 repeats (585.3s), red repeats none.

[2026-08-08T02:45:00Z · sase-h8.6] MECHANISM (confirmed, not inferred): a probe that schedules _fire_debounced_detail_update right after the injected write showed the panel document replaced by the real agent document ("No prompt file found."), so `/` captured a corpus with no match. Waiting for the debouncer to be idle before writing does not close the window because the next repaint is scheduled after the check. Fix suppresses the competing render: sase.ace.testing.set_agent_prompt_document installs a one-way gate on AgentPromptPanel.update for that panel instance, so no app-driven repaint (debounced detail, immediate header, header-enrichment message, slow-tool tick) can re-derive the document, and the helper settle-verifies its own write with a bounded wait.

[2026-08-08T02:45:54Z · sase-h8.6] FALSIFIED: with the gate install line disabled, the new guard node tests/ace/tui/test_agent_metadata_search.py::test_pinned_metadata_document_survives_a_debounced_repaint fails serially and deterministically in 2.1s, and a contention soak taken while it was disabled reproduced the original family again (3/6 guard, 1/6 reverse_key_override, 1/6 exits_when_identity_changes). The fix is therefore falsifiable without contention.

[2026-08-08T02:46:36Z · sase-h8.6] F4 SCOPE CORRECTION CONFIRMED: test_rapid_navigation_loads_only_the_final_detail is not a flake. It already fakes app.set_timer and asserts on the last scheduled callback, it is absent from the health store flake set (per sase-h8.3), and tests/ace/tui/test_artifacts_files_detail.py was 0/6 in the post-fix soak. No cross-test-leakage fixture was needed; the epic plan overstated this membership and the sase-h8.3 triage table is right.

[2026-08-08T02:47:09Z · sase-h8.6] PROPOSED FOLLOW-UP: tests/doctor/test_checks_providers.py::test_setup_hint_points_script_installs_at_the_install_subcommand fails deterministically and serially at this workspace master (050c9477c), on a stashed clean tree too — a second X1-shaped regression the sase-h8.3 triage table does not list; triage it like the six gate nodes.

[2026-08-08T02:47:21Z · sase-h8.6] PROPOSED FOLLOW-UP: phase gate lint check should also flag raw injections into app-derived ACE panels (panel.update(Text(...)) on #agent-prompt-panel and friends) and point at sase.ace.testing.set_agent_prompt_document, the same way it flags the retired ad-hoc _wait_until copies.

[2026-08-08T02:47:38Z · sase-h8.6] Published sase.ace.testing.set_agent_prompt_document, a settle-verified pinned-document injector that suppresses the competing repaint, and moved the three F3 test_agent_metadata_search nodes onto it plus a new guard node. Verified: pre-fix contention baseline 4/6, 3/6, 3/6; post-fix 0 nodes across 6 repeats; guard node fails deterministically in 2.1s with the pin disabled. just lint green (ruff, mypy 2844 files, symvision). just check-full: 27440 passed, 7 pre-existing failures only — the six known X1 gate nodes from ff0b765a4 plus tests/doctor/test_checks_providers.py::test_setup_hint_points_script_installs_at_the_install_subcommand, which also fails on a stashed clean tree and is noted as a follow-up. F4 half confirmed out of scope by measurement.

[2026-08-08T02:48:21Z · sase-h8.6] Verified: pre-fix soak red at repeats 3-6 (26 workers/2 CPUs), post-fix soak 0 failures over 6 repeats (585.3s); new guard node fails deterministically with the pin disabled; just lint green; just check-full failures all pre-existing.

## Dependencies

- **Depends on:** [sase-h8.2](sase-h8.2.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-h8.3](sase-h8.3.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-h8.8](sase-h8.8.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h8.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.6/README.md) | [sase-h8.6](sase-h8.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f980248`](https://github.com/sase-org/sase/commit/f980248c19958191a84e57100aa4de289bb3897c) | test(ace): pin the metadata-search corpus against competing repaints | [sase-h8.6](sase-h8.6.md) | 2026-08-07 22:48:58 EDT |
