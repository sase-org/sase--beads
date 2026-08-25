# Bead: sase-th.5 — Isolate the pooled-alias round-robin cursor from tests

[Bead Pages](../README.md) / [sase-th](README.md) / sase-th.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0d8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0d8.md) · **Assignee:** `sase-th.5` · **Size:** medium
**Created:** 2026-08-25 07:32:02 EDT · **Closed:** 2026-08-25 07:53:58 EDT
**Plan:** [202608/repair\_red\_master\_ci.md](https://github.com/sase-org/sase--plans/blob/main/202608/repair_red_master_ci.md)

## Description

pool-cursor: stop the machine-global llm_lb.json cursor from leaking between concurrently running test files, which is why the pooled-alias consumption tests fail only in CI's parallel lane.

## Notes

[2026-08-25T11:53:31Z · sase-th.5--1] PROPOSED FOLLOW-UP: `just check` currently fails `ruff format --check` on src/sase/sdd/_store_link.py (missing a second blank line before `is_matching_store_clone = _is_matching_store_clone` at EOF), introduced by commit 51f6369b3 "refactor(sdd): split store-link clone helpers" — unrelated to this phase, file untouched by sase-th.5. Suspect cause: `.venv/bin/ruff` resolved to 0.16.3 while uv.lock pins ruff==0.15.4 (just install uses `uv pip install -e .[dev]` without --frozen, so it can drift from the lock over time); worth checking whether CI hit the same drift or whether formatting rules changed between ruff 0.15.4 and 0.16.3. Not fixed here to keep this phase scoped to pooled-alias cursor isolation.

[2026-08-25T11:53:58Z · sase-th.5--1] Verified already resolved by prior work; made no code changes. The plan's claim (no HOME isolation in tests/conftest.py, causing the machine-global ~/.sase/llm_lb.json round-robin cursor to leak between concurrently running test files) is stale: commit 27a450be5 'fix: isolate SASE home path resolution' (2026-05-27) added the autouse _isolate_sase_home fixture (tests/_conftest_environment.py, imported into tests/conftest.py) which redirects HOME/SASE_HOME to a fresh tmp_path_factory dir per test, and src/sase/llm_provider/load_balancing.py's rotation_state_path() calls sase_home() fresh on every call with no caching (the module's one lru_cache, _weighted_schedule, is a pure function of pool weights only). Repro evidence: ran the plan's 6 named files plus 2 more sibling files that also touch llm_lb.json (tests/llm_provider/test_launch_default_peek.py, tests/test_launch_default_indicator_pool_rotation.py) under real xdist worksteal distribution — 5 iterations at -n4 (73 tests each) and 10 iterations at -n8 (80 tests each) — 0 failures across all 15 runs. Recent master CI runs are also green. Recorded corroboration on epic sase-j7 (closed epic that owns this flake class) and confirmed no pooled-alias/load-balanced-alias node appears in tests/reproducible_flake_baseline.txt. just check surfaced one unrelated pre-existing fmt failure in src/sase/sdd/_store_link.py (untouched by this phase, introduced by commit 51f6369b3, likely a ruff-version/lock-drift issue) — recorded as PROPOSED FOLLOW-UP on this bead rather than fixed here to keep scope to pooled-alias isolation. No --epic-symbol entries for this phase.

## Dependencies

- **Blocks:** [sase-th.7](sase-th.7.md) ◐ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-th.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-th.5.md) | [sase-th.5](sase-th.5.md) | 0 |
