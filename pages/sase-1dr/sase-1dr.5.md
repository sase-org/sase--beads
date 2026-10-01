# Bead: sase-1dr.5 — Python history service and the sase memory history CLI

[Bead Pages](../README.md) / [sase-1dr](README.md) / sase-1dr.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3o](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3o.md) · **Assignee:** `sase-1dr.5` · **Size:** medium
**Created:** 2026-09-30 19:09:24 EDT · **Closed:** 2026-10-01 02:17:44 EDT
**Plan:** [202609/memory\_history.md](https://github.com/sase-org/sase--plans/blob/main/202609/memory_history.md)

## Description

history-cli: add the thin facade and wire types, a scope builder for project and chezmoi home repos from the agent-docs inventory and generated-note list, a thread-safe history service, and one shared visual-vocabulary table. Ship `sase memory history` with colored text and JSON output for subjects, versions, diffs, and the feed. Measure real-repo performance.

## Notes

[2026-10-01T05:29:34Z · sase-1dr.5] Real-repo perf (sase checkout, 139 subjects / 1186 versions, fixed extension): cold rebuild 6.5s (budget 1.5s), warm fresh-check 0.17s (budget 30ms), timeline query 0.07s, CLI text end-to-end 1.9s / JSON 2.0s (budget 300ms incl. interpreter startup). Snapshot 3.2MB; raw walk output only 241KB so classification/blob reads dominate cold.

[2026-10-01T05:30:10Z · sase-1dr.5] PROPOSED FOLLOW-UP: land the sase-core git-runner deadlock fix (linked checkout, uncommitted): crates/sase_core/src/file_history/runner.rs drains stdout on a reader thread instead of read-after-exit; without it every memory_history sync over >64KB log output hits the 10s budget kill. Needs sase-core commit+push, sase-core-revision.txt ratchet past it, and extension rebuild. Regression test: file_history::runner::tests::output_larger_than_the_pipe_buffer_does_not_deadlock.

[2026-10-01T05:30:28Z · sase-1dr.5] PROPOSED FOLLOW-UP: close the section-5.5 perf gap (cold 6.5s vs 1.5s, warm 0.17s vs 30ms, CLI ~1.9s vs 300ms) in core (blob/classify pipeline, 3.2MB snapshot parse) or revise the budgets; launch phase owns budget verification.

[2026-10-01T05:30:46Z · sase-1dr.5] PROPOSED FOLLOW-UP: sase-core sase tool run check is red on 9 pre-existing clippy-1.95 lints (agent_runtime, agent_scan, finalizer/run_view, fleet_owner_facts, provider_usage x2, tool_run receipt+triage); no tracking bead found; none touch file_history/runner.rs.

[2026-10-01T05:32:19Z · sase-1dr.5] Verified before close: 30 new tests pass (vocabulary/scopes/render/CLI incl. historical names, ambiguity, -A v7/~2/SHA/date, JSON passthrough, no read-audit rows); ruff+format+mypy clean on all new files; sase-core focused tests pass (5/5 runner incl. new >64KB regression); real-repo timeline/feed/diff/strand/JSON verified live; sase-core-revision.txt at sase-core HEAD 11f29c3; no epic-symbol leftovers. Known gaps filed as PROPOSED FOLLOW-UP (core landing+pin, perf budgets, clippy drift).

[2026-10-01T06:17:13Z · sase-1dr.5--1] PROPOSED FOLLOW-UP: just check symvision gate stays red on 4 pre-existing unused publics in files this phase never touched (HandoffSubmitResult, StarterResolution, owner_ref tracked by sase-1dn; fit_next_word_ghost in next_word_completion.py from the sase-1dq word-completion line); reproduced identically on the monitored base run triage (4 KNOWN) and unaffected by this phase

[2026-10-01T06:17:44Z · sase-1dr.5--1] Verified: all 20 phase-owned symvision NEW items resolved (service.py now imports facade symbols directly incl. a wire_schema_version drift guard in HistoryService.__init__; deleted dead scope_from_dict; privatized 3 scopes + 7 render_text in-file helpers; label_for/is_hidden_by_default re-keyed to open sase-1dr.6 in Justfile); just _lint-symvision shows only the 4 pre-existing KNOWN items (filed as PROPOSED FOLLOW-UP citing sase-1dn); ruff+format+mypy clean; 30/30 tests/memory history tests pass (vocabulary/scopes/render/CLI incl. wire-schema contract)

## Dependencies

- **Depends on:** [sase-1dr.4](sase-1dr.4.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1dr.6](sase-1dr.6.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1dr.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1dr.5.md) | [sase-1dr.5](sase-1dr.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@62788b4`](https://github.com/sase-org/sase-core/commit/62788b4004039c1e119e7dcee61b29309bfd2505) | feat(sase-1dr.5): file history runner support in sase-core | [sase-1dr.5](sase-1dr.5.md) | 2026-10-01 02:21:24 EDT |
| sase | [`ebf070e`](https://github.com/sase-org/sase/commit/ebf070e16ae0b24bf889d582c574d01752bb6d54) | fix(sase-1dr.5): resolve phase-owned symvision failures in memory history | [sase-1dr.5](sase-1dr.5.md) | 2026-10-01 02:52:07 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1dr.5--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1dr.5.md

<!-- sase:referenced-by:end -->
