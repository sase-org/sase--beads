# Bead: sase-zf.3 — Load-path pushdown parity and secondary query consumers

[Bead Pages](../README.md) / [sase-zf](README.md) / sase-zf.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0iy](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0iy.md) · **Assignee:** `sase-zf.3` · **Size:** medium
**Created:** 2026-09-10 18:01:48 EDT · **Closed:** 2026-09-10 20:43:33 EDT
**Plan:** [202609/agents\_query\_unification.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_query_unification.md)

## Description

consumers-and-pushdown: compile the new dialect into the existing Rust candidate-filter pushdown with window-safety parity, and migrate the machines-pane writer, project seeding, unread-jump, neighbor, and prospective-clan consumers to the shared match-mask facade.

## Notes

[2026-09-11T00:24:02Z · sase-zf.3] PROPOSED FOLLOW-UP: Resolve feature-flag registry drift for live flag bead sase-z0 (link_events) — just check currently fails at lint (feature flags); recent warnings also mention sase-z5 weighted_queue_capacity, sase-z6 ace_unified_agents, and sase-z9 completion_managed_install_recipe.

[2026-09-11T00:25:16Z · sase-zf.3] PROPOSED FOLLOW-UP: Fix test-wait lint violations in tests/fakey/test_provider_drain_e2e.py — _lint-test-waits reports fixed-sleep-missing-pragma at lines 65 and 86.

[2026-09-11T00:39:11Z · sase-zf.3] PROPOSED FOLLOW-UP: Triage stable unrelated full-suite failures from escalated test-scoped — fleet_count_logical_agents row_kind/family_role contract, installed research_swarm %wait(priority=...) plugin drift, and restart_recovery marker mutation audit drift.

[2026-09-11T00:43:33Z · sase-zf.3] Verified: focused agents query/pushdown/consumer pytest suite passed (56 passed); just fmt-py-check, just _lint-ruff, just _lint-mypy, just _lint-symvision, just _lint-changelog, just _lint-patch-stitch-terminology, just _lint-toobig, just validate, and just validate-committed-plans passed. Ran just check; it reached _lint-test-waits and stopped on existing fixed-sleep-missing-pragma failures in tests/fakey/test_provider_drain_e2e.py lines 65 and 86, recorded as PROPOSED FOLLOW-UP. Ran sase bead epic-symbols sase-zf.3: no entries.

## Dependencies

- **Depends on:** [sase-zf.2](sase-zf.2.md) ✓ · ⧖ 2026-09-10
- **Blocks:** [sase-zf.4](sase-zf.4.md) ◐ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zf.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zf.3/README.md) | [sase-zf.3](sase-zf.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e62e96f`](https://github.com/sase-org/sase/commit/e62e96f5ff917f5837051f2a192f842f453ce18d) | feat(agents): push down live query filters | [sase-zf.3](sase-zf.3.md) | 2026-09-10 20:45:16 EDT |
