# Bead: sase-z4.6.5.4.6.3 — Establish and verify the published minimum-version cohort

[Bead Pages](../README.md) / [sase-z4.6.5.4.6](sase-z4.6.5.4.6.md) / sase-z4.6.5.4.6.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-z4.6.5.4.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-z4.6.5.4.land.md) · **Assignee:** `sase-z4.6.5.4.6.3` · **Size:** medium
**Created:** 2026-09-12 06:29:18 EDT
**Plan:** [202609/weighted\_capacity\_lifecycle\_and\_release.md](https://github.com/sase-org/sase--plans/blob/main/202609/weighted_capacity_lifecycle_and_release.md)

## Description

published-proof: establish real containing releases through existing automation, run clean wheel-only positive and negative smoke checks without skipped research acceptance, and preserve the flag-retirement evidence.

## Notes

[2026-09-14T01:38:39Z · sase-z4.6.5.4.6.3] PROPOSED FOLLOW-UP: sase-research-artifacts tests/test_xprompt_loading.py and the install-smoke-published-minimum job in its publish.yml call extract_prompt_directives() directly on freshly expanded research_swarm segments containing %wait:research.{@1}.slot dependency references, outside the family-name-reservation context real launches get from plan_typed_launch_units (which resolves waits via logical unit ids, not concrete names). In a hermetic environment (fresh SASE_HOME, e.g. real CI or `SASE_HOME=$(mktemp -d) python -c ...`), require_latest_agent_name_template raises AgentNameTemplateNotFoundError for the final/image segments because no research.N.cdx/.cld sibling name is pre-registered; it only passes on hosts with incidental leftover agent-name history (why it looked green locally in this epols package-contract phase). Reproduced independently of any weighted-capacity dependency-window issue: research release PR #2 CI run 34788131668 fails both check(3.12)/check(3.13) on exactly this error post package-contract fix, and this is unrelated to queue capacity/weight syntax (it is the %wait: dependency directive, not %queue). This blocks establishing a containing research-plugin release regardless of the SASE/core compatibility floor. Pre-existing and orthogonal to weighted-capacity; fixing it needs either seeding reserved sibling names before calling extract_prompt_directives in that test/smoke code, or switching that test/smoke code to the same plan_typed_launch_units path production and the SASE-side fakey test already use.

[2026-09-14T11:33:17Z · sase-z4.6.5.4.6.3] PROGRESS/BLOCKED 2026-09-14: rechecked the published cohort and repaired the current research release-gate failure, but the phase cannot honestly close yet. PyPI/Python 3.12 pip index and PyPI JSON show sase-core-rs latest 0.34.26, sase latest 0.17.1, and sase-research-artifacts latest 0.2.0. SASE tags/releases still stop at v0.17.1; release PR #299 for 0.17.2 is open/mergeable and its release-core-floor-smoke job in run 34808126877 passed on 2026-09-14, but no v0.17.2 tag, GitHub release, or package-index version exists. Research tags/releases still stop at v0.2.0; release PR #2 for 0.3.0 is open/mergeable but CI run 34788131668 failed check 3.12 and canceled check 3.13 with six tests/test_xprompt_loading.py failures from AgentNameTemplateNotFoundError on research.{@1}.cdx while direct-parsing rendered segments. I patched sase-research-artifacts to keep raw four-segment queue text assertions while using plan_typed_launch_units on the rendered batch for queue/directive assertions in tests/test_xprompt_loading.py, tests/test_wheel_contract.py, and the publish.yml published-minimum smoke; tests/test_ci_install_contract.py now guards that production-path smoke shape. Verified in the research repo: just test tests/test_xprompt_loading.py tests/test_ci_install_contract.py -> 27 passed; just check -> ruff, mypy, and 48 tests passed; just test-wheel tests/test_wheel_contract.py -> 4 passed. Verified in SASE: tools/probe_core_floor --advisory --json -> status ok, declared_floor 0.34.26; scratch uv install of sase==0.17.2 with sase-core-rs==0.34.23 fails unsatisfiable because sase 0.17.2 is not published; rg weighted_queue_capacity in SASE src/tests/pyproject/default_config/.github finds none; sase-z5 remains closed for the earlier administrative flag retirement; sase bead epic-symbols sase-z4.6.5.4.6.3 reports no entries. Not closing this phase because the required positive published wheel-only minimum cohort cannot be installed until SASE 0.17.2 and the research plugin 0.3.0 actually publish.

## Dependencies

- **Depends on:** [sase-z4.6.5.4.6.1](sase-z4.6.5.4.6.1.md) ✓ · ⧖ 2026-09-12
- **Depends on:** [sase-z4.6.5.4.6.2](sase-z4.6.5.4.6.2.md) ✓ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-z4.6.5.4.6.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-z4.6.5.4.6.3/README.md) | [sase-z4.6.5.4.6.3](sase-z4.6.5.4.6.3.md) | 2 |
| [bbugyi200.athena.toobig-5c.agent.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-5c.agent.0/README.md) | [sase-z4.6.5.4.6.3](sase-z4.6.5.4.6.3.md) | 1 |
| [bbugyi200.athena.toobig-5c.commit.0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.toobig-5c.commit.0.md) | [sase-z4.6.5.4.6.3](sase-z4.6.5.4.6.3.md) | 1 |
| [bbugyi200.athena.toobig-5c.disk\_footprint.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-5c.disk_footprint.0/README.md) | [sase-z4.6.5.4.6.3](sase-z4.6.5.4.6.3.md) | 1 |
| [bbugyi200.athena.toobig-5c.followup.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-5c.followup.0/README.md) | [sase-z4.6.5.4.6.3](sase-z4.6.5.4.6.3.md) | 1 |
| [bbugyi200.athena.toobig-5c.resume.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-5c.resume.0/README.md) | [sase-z4.6.5.4.6.3](sase-z4.6.5.4.6.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1690400`](https://github.com/sase-org/sase/commit/1690400b2fe8e3f6afd421cc16f896ad6ef79198) | fix(capacity): ratchet published core floor and fix stale zero-capacity fakey assertion | [sase-z4.6.5.4.6.3](sase-z4.6.5.4.6.3.md) | 2026-09-13 21:41:25 EDT |
| sase | [`620d872`](https://github.com/sase-org/sase/commit/620d872547a6980374e6814e28fa164e24597558) | refactor(core): split disk footprint module | [sase-z4.6.5.4.6.3](sase-z4.6.5.4.6.3.md) | 2026-09-14 00:03:03 EDT |
| sase | [`2863ed2`](https://github.com/sase-org/sase/commit/2863ed2f19a2431baeff25cca3f943f44e3e81c8) | refactor(finalizers): split commit finalizer helpers | [sase-z4.6.5.4.6.3](sase-z4.6.5.4.6.3.md) | 2026-09-14 00:43:42 EDT |
| sase | [`f486b2e`](https://github.com/sase-org/sase/commit/f486b2efa105bc40b9baaf669ed1bdb9fab848f6) | refactor(monitor): split followup helpers | [sase-z4.6.5.4.6.3](sase-z4.6.5.4.6.3.md) | 2026-09-14 02:21:05 EDT |
| sase | [`f36cc14`](https://github.com/sase-org/sase/commit/f36cc145c0cc49bb74370420a7f66b5d24a587f0) | refactor(monitor): split resume.py into focused modules | [sase-z4.6.5.4.6.3](sase-z4.6.5.4.6.3.md) | 2026-09-14 02:49:46 EDT |
| sase | [`9dbc850`](https://github.com/sase-org/sase/commit/9dbc8500624654c43156beea025b0e9dbfcb3caa) | refactor(ops): split agent command helpers | [sase-z4.6.5.4.6.3](sase-z4.6.5.4.6.3.md) | 2026-09-14 04:14:07 EDT |
| sase-research-artifacts | [`sase-research-artifacts@9b36ea8`](https://github.com/sase-org/sase-research-artifacts/commit/9b36ea887ccca087fc0e548cd49a8f6dc508fc13) | fix(research): plan swarm queue release smokes | [sase-z4.6.5.4.6.3](sase-z4.6.5.4.6.3.md) | 2026-09-14 07:35:05 EDT |
