# Bead: sase-1fs.2 — Add explicit retired-request recovery with correct completion checks

[Bead Pages](../README.md) / [sase-1fs](README.md) / sase-1fs.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.4s.f1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.4s.f1.md) · **Assignee:** `sase-1fs.2` · **Size:** medium
**Created:** 2026-10-03 12:42:04 EDT · **Closed:** 2026-10-03 17:04:11 EDT
**Plan:** [202610/bob\_cli\_agents\_publication\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202610/bob_cli_agents_publication_recovery.md)

## Description

publication_recovery: add project-scoped retired-request retry, preserve deferred prompts, recognize session pages, and test acknowledgment only after successful publication.

## Notes

[2026-10-03T20:43:17Z · sase-1fs.2] PROPOSED FOLLOW-UP: just check lint (symvision) fails on five unused public symbols in src/sase/axe/runner_kill_provenance.py (KillProvenance, classify_runner_kill, format_kill_classification, oom_kill_evidence, reset_oom_baseline) — unmodified vs HEAD 1466f1a67b from 9fe4405683; no existing task tracks these names (sase-1ay and closed sase-1dn cover other unused-public sets). Privatize the same-file helpers per sase/memory/symvision.md.

[2026-10-03T21:02:50Z · sase-1fs.2] PROPOSED FOLLOW-UP: tests/ace/tui/actions/test_prompt_snippet_location_flow.py::test_shift_tab_round_trip_preserves_trigger failed in parallel test-scoped (assert has ⇥ todo in Finding destinations…) — already tracked by sase-1e4; isolated recovery tests passed.

[2026-10-03T21:02:55Z · sase-1fs.2] PROPOSED FOLLOW-UP: tests/ace/tui/test_launch_context_bar.py::test_agents_row_fit_shares_density_between_gauge_and_bar timed out in wait_for after 5.0s under parallel test-scoped — no existing task tracks this node; does not touch publication recovery files.

[2026-10-03T21:04:11Z · sase-1fs.2] Verified: sase agent sync -t/--retry-retired requires --project and is rejected with --check/--drop-retired/--repair-*; Rust select/complete/classify plus Python adapters revive retired rows under the outbox lock, acknowledge only when the canonical run or session page exists with the requested SHA, and keep deferred prompts retryable unless restored/archived/not-applicable. 65 recovery tests passed; mypy green; completion spec updated. Remaining just check red is pre-existing unused-public symbols in runner_kill_provenance.py (PROPOSED FOLLOW-UP); parallel TUI flakes cited sase-1e4 and launch_context_bar wait_for timeout.

## Dependencies

- **Depends on:** [sase-1fs.1](sase-1fs.1.md) ✓ · ⧖ 2026-10-03
- **Blocks:** [sase-1fs.3](sase-1fs.3.md) ✓ · ⧖ 2026-10-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1fs.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1fs.2/README.md) | [sase-1fs.2](sase-1fs.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@3d406d4`](https://github.com/sase-org/sase-core/commit/3d406d4cef2078a2f9513dc7b4fa098c12a23c1e) | feat(agent-publication-recovery): retry selection, page+SHA completion, and prompt status | [sase-1fs.2](sase-1fs.2.md) | 2026-10-03 17:05:12 EDT |
| sase | [`b51df19`](https://github.com/sase-org/sase/commit/b51df19d88d26d43377530c7176cdf8e3c83802f) | feat(agents-sync): revive retired publication requests with session-aware completion | [sase-1fs.2](sase-1fs.2.md) | 2026-10-03 17:07:39 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1fs.2][1] | Need the phase scope and design file | 3 |
| read-by | [agent:sase-1fv.1][2] | Check prior records for the known Symvision symbols and avoid duplicating an existing follow-up | 1 |
| read-by | [agent:toobig-6y.macro_terminology_string_pairs_b.0][3] | Need whether kill-provenance symvision is already recorded | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1fs.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1fv.1/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.toobig-6y.macro_terminology_string_pairs_b.0/README.md

<!-- sase:referenced-by:end -->
