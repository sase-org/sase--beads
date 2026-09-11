# Bead: sase-zp.1 — Establish the weighted capacity directive contract

[Bead Pages](../README.md) / [sase-zp](README.md) / sase-zp.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0jl](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0jl.md) · **Assignee:** `sase-zp.1` · **Size:** medium
**Created:** 2026-09-11 13:40:28 EDT · **Closed:** 2026-09-11 15:13:02 EDT
**Plan:** [202609/bead\_work\_capacity.md](https://github.com/sase-org/sase--plans/blob/main/202609/bead_work_capacity.md)

## Description

capacity_contract: rename the directive field in Rust and its Python adapters, enforce weighted-load thresholds, update queue presentation, and test the binding boundary.

## Notes

[2026-09-11T19:10:26Z · sase-zp.1] PROPOSED FOLLOW-UP: research_swarm still emits %wait(priority=N) — the installed sase-research-artifacts xprompt renders %wait(priority=20) on every swarm unit, which the queue contract now rejects; map wait-slot fields onto %queue(capacity=..., priority=...) so tests/fakey/test_runner_slots_e2e.py::test_installed_research_swarm_quarter_weights_fill_one_fakey_capacity_unit can expand and launch.

[2026-09-11T19:13:02Z · sase-zp.1] Verified weighted capacity contract: Rust queue_directive (capacity field, %q:N/%queue(N)/%queue(capacity=N) equivalent, obsolete runners= rejected, parse_queue_capacity), runner_capacity schema 3 (occupied weighted load vs N, capacity 0 true-drain, global max_running_agents still applies, wait_runners storage spelling), editor/LSP keyword order capacity/p/priority/w/weight; PyO3 parse_queue_capacity + format_queue_directive(capacity=); Python adapter validate_queue_capacity + wait modal #capacity-input/#capacity-preview + [capacity] lane tag. Focused pytest 158 passed (queue_directive, xprompt contract, wait/modal/edit/chop). cargo fmt --check clean on opened sase-core. sase bead epic-symbols sase-zp.1: no leftovers. SASE just check remains red on unrelated live bead sase-z9 feature-flag lint, symvision private imports, toobig continuation_capture.py, and workspace-drift full-suite failures; capacity-related research_swarm %wait(priority=N) recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-zp.2](sase-zp.2.md) ✓ · ⧖ 2026-09-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zp.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zp.1/README.md) | [sase-zp.1](sase-zp.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e48aa7d`](https://github.com/sase-org/sase/commit/e48aa7db0fdcb39c35895b0bff82171c56e452c1) | feat(queue): rename runners to weighted capacity in Python adapters and TUI | [sase-zp.1](sase-zp.1.md) | 2026-09-11 15:39:48 EDT |
| sase-core | [`sase-core@d2f8d72`](https://github.com/sase-org/sase-core/commit/d2f8d72734c6a74ea116ed7d7ddf97b3a05bf796) | feat(queue): replace runners with weighted-load capacity contract | [sase-zp.1](sase-zp.1.md) | 2026-09-11 15:45:10 EDT |
