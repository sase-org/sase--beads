# Bead: sase-bv.2 — Add the Python attribution resolver and creator plumbing

[Bead Pages](../README.md) / [sase-bv](README.md) / sase-bv.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-bv.2` · **Size:** small
**Created:** 2026-07-31 13:12:36 UTC · **Closed:** 2026-07-31 14:17:11 UTC
**Plan:** [202607/bead\_created\_by\_attribution.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_created_by_attribution.md)

## Description

attribution: add the `sase.bead.attribution` module that resolves the acting agent's durable global name and a plan's recorded proposer, thread `created_by` through the bead mutation facade and `BeadProject.create`, and surface `proposed_by` on the Python validated-plan dataclass.

## Notes

[2026-07-31T14:15:44Z · sase-bv.2] PROPOSED FOLLOW-UP: ACE PNG visual snapshots are stale on master — 53 of 393 `just test-visual` cases fail on a clean checkout with a ~1-row vertical layout shift (see .pytest_cache/sase-visual diffs); likely goldens not regenerated after 146982d14 (tribe description block).

[2026-07-31T14:15:51Z · sase-bv.2] PROPOSED FOLLOW-UP: tests/test_xprompt_model_completion.py::test_model_completion_catalog_reflects_real_builtin_model_metadata fails on a clean checkout — provider description now renders lowercase "codex (gpt53spark)" where the test expects "Codex (gpt53spark)"; sase-core metadata drift.

[2026-07-31T14:15:59Z · sase-bv.2] PROPOSED FOLLOW-UP: sase.bead.prefix_policy.is_safe_bead_prefix was public with no non-test consumer and failed symvision on master; made it private (_is_safe_bead_prefix) here to unblock `just check` — unrelated to this phase.

[2026-07-31T14:17:11Z · sase-bv.2] Added src/sase/bead/attribution.py (acting_agent_name / plan_proposed_by / resolve_bead_creator), threaded created_by through bead_mutation_facade.create and BeadProject.create, and surfaced proposed_by on the Python validated-plan dataclass. Verified: 13 new resolver tests (incl. explicit SASE_AGENT=1 hazard case + agent_meta fallback), BeadProject.create round-trip of explicit created_by, owner fallback, and phase inheritance from the parent epic, plus a plan_validate test asserting proposed_by round-trips and the updated tale schema field order. just lint fully green (symvision epic-symbol entries added under sase-bv for the not-yet-consumed public resolvers). Pre-existing master failures noted as follow-ups: 53 stale ACE PNG goldens and one model-completion description-case test.

## Dependencies

- **Depends on:** [sase-bv.1](sase-bv.1.md) ✓
- **Blocks:** [sase-bv.3](sase-bv.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-bv.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-bv.2/README.md) | [sase-bv.2](sase-bv.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`578e4f5`](https://github.com/sase-org/sase/commit/578e4f5c6499c32d21468734e142ff1c6d092eac) | feat(bead): resolve the acting agent as a bead creator | [sase-bv.2](sase-bv.2.md) | 2026-07-31 14:18:10 |
