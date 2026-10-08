# Bead: sase-1hi.10.1 — Stamp order and surface, revision binding on every route, kind validation, and new-note grants

[Bead Pages](../README.md) / [sase-1hi.10](sase-1hi.10.md) / sase-1hi.10.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1hi.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.land.md) · **Assignee:** `sase-1hi.10.1` · **Size:** large
**Created:** 2026-10-08 05:26:41 EDT · **Closed:** 2026-10-08 06:20:08 EDT
**Plan:** [202610/plan\_decisions\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202610/plan_decisions_landing_repairs.md)

## Description

gate: keep author order and the true decided_via in stamps, re-stamp from response.json on retry, carry review_revision through detached gate answers, make kind validation real, fail closed on callers and host checks, let memory grants name notes that do not exist yet, and add the missing stamping, stale_review, and agent-refusal tests.

## Notes

[2026-10-08T10:19:57Z · sase-1hi.10.1--1] PROPOSED FOLLOW-UP: sase tool run check is red only on 5 NEW symvision unused-public items (sase-1hp backlog): claude_projects_root (instructions/_runs.py), git_fetch_origin (llm_provider/commit_finalizer_git_status.py), collapsed_row_text + expanded_row_text (ace/tui/modals/plan_decision_rows.py), prompt_origin_for_launch (agent/launch_provenance.py). None are in phase-touched files. Evidence of pre-existing: ran the exact gate command (symvision src/sase with both exclude-decorators) in a clean HEAD worktree — same 5 symbols flagged, and the unused-symbol sets differ only by phase-added write_acceptance_meta (triaged KNOWN). Do not repair in this phase.

[2026-10-08T10:20:08Z · sase-1hi.10.1--1] Gate decision repairs implemented and verified: author-order/immutable stamps, true decided_by/decided_via surfaces with unknown-source rejection, response.json recovery without re-resolution, review_revision binding on attached+detached routes, real kind-validation rebuild with fail-closed callers/host checks, future-note/strand grants with exists:false. Fixed mypy overload error (resolved narrowing) plus 3 phase-test fixture bugs. Checks: ruff+mypy+all other lint gates green; 22/22 focused tests pass (test_plan_gate_decision_repairs.py, test_plan_decisions_gate.py); epic-symbols empty. Remaining check red is 5 pre-existing NEW symvision items proven identical on clean HEAD worktree, recorded as follow-up (sase-1hp).

## Dependencies

- **Blocks:** [sase-1hi.10.2](sase-1hi.10.2.md) ✓ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1hi.10.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.10.1.md) | [sase-1hi.10.1](sase-1hi.10.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c929bb1`](https://github.com/sase-org/sase/commit/c929bb176b7ecbc1f8dc8a96aad5863a80d08a65) | feat(plan): repair gate decision acceptance, stamps, validation, and grants | [sase-1hi.10.1](sase-1hi.10.1.md) | 2026-10-08 06:21:40 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1hi.10.1--1][1] | implement approved gate decision repairs plan | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.10.1.md

<!-- sase:referenced-by:end -->
