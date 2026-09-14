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

## Dependencies

- **Depends on:** [sase-z4.6.5.4.6.1](sase-z4.6.5.4.6.1.md) ✓ · ⧖ 2026-09-12
- **Depends on:** [sase-z4.6.5.4.6.2](sase-z4.6.5.4.6.2.md) ✓ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-z4.6.5.4.6.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-z4.6.5.4.6.3/README.md) | [sase-z4.6.5.4.6.3](sase-z4.6.5.4.6.3.md) | 1 |
| [bbugyi200.athena.toobig-5c.disk\_footprint.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-5c.disk_footprint.0/README.md) | [sase-z4.6.5.4.6.3](sase-z4.6.5.4.6.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1690400`](https://github.com/sase-org/sase/commit/1690400b2fe8e3f6afd421cc16f896ad6ef79198) | fix(capacity): ratchet published core floor and fix stale zero-capacity fakey assertion | [sase-z4.6.5.4.6.3](sase-z4.6.5.4.6.3.md) | 2026-09-13 21:41:25 EDT |
| sase | [`620d872`](https://github.com/sase-org/sase/commit/620d872547a6980374e6814e28fa164e24597558) | refactor(core): split disk footprint module | [sase-z4.6.5.4.6.3](sase-z4.6.5.4.6.3.md) | 2026-09-14 00:03:03 EDT |
