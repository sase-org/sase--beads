# Bead: sase-z4.6.5.1 — Make Rust candidate lineage authoritative at admission

[Bead Pages](../README.md) / [sase-z4.6.5](sase-z4.6.5.md) / sase-z4.6.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-z4.6.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-z4.6.land.md) · **Assignee:** `sase-z4.6.5.1` · **Size:** medium
**Created:** 2026-09-10 13:23:41 EDT · **Closed:** 2026-09-10 15:47:15 EDT
**Plan:** [202609/weighted\_capacity\_final\_acceptance.md](https://github.com/sase-org/sase--plans/blob/main/202609/weighted_capacity_final_acceptance.md)

## Description

admission-authority: connect the Rust runner-capacity candidate decision and durable claim lineage through scan metadata and the locked Python admission path, then integrate the later capacity-only scan mode without losing predecessor ownership.

## Notes

[2026-09-10T19:30:24Z · sase-z4.6.5.1--2] PROPOSED FOLLOW-UP: tests/test_pooled_alias_single_consumption.py has 5 pre-existing failures on origin/master unrelated to admission-authority (confirmed via git stash -u against clean master by a prior member of this agent family) — pool member selection returns wrong provider/model (e.g. expects claude/opus, gets claude/sonnet), suggesting pool rotation or default_config.yml drift. Needs its own bug bead.

[2026-09-10T19:30:47Z · sase-z4.6.5.1--2] PROPOSED FOLLOW-UP: just check's lint (feature flags) gate now hard-fails repo-wide because flag bead sase-z0 ('Retire link_events', owned by agent family sase-yy.4) is still OPEN more than 24h after its registry definition (FeatureFlag.link_events) was already removed from src/ — check_feature_flags rule 8 escalates from warning to error once the landing grace expires. Confirmed unrelated to admission-authority: none of this phase's changed files touch flags/artifact-links code, just validate's static check_feature_flags --static passes cleanly, and origin/master is 5 commits ahead with further artifact-links commits (f5a3f5c9, abdcb86d) showing that epic is actively landing on a different lineage. Needs sase-z0 either closed or its registry definition restored by that epic owner; blocks just check for every agent in this shared repo until resolved.

[2026-09-10T19:46:41Z · sase-z4.6.5.1--3] PROPOSED FOLLOW-UP: tests/test_workflow_executor.py::TestShouldHitl (test_inherited_model_override_beats_step_model_directive, test_prompt_step_chat_history_includes_step_metadata) also fail on clean origin/master (confirmed via git stash -u) — both expect a specific model (gemini-3-flash-preview, o3) but resolve to "sonnet" instead. Same symptom as the already-filed pooled-alias pre-existing bug (wrong provider/model resolved); likely shares a root cause in model/pool resolution. Unrelated to admission-authority. Also observed tests/sdd/test_artifact_link_derivation.py::test_a_second_pass_over_the_same_documents_is_idempotent fail only under full test-scoped run but pass in isolation on both this branch and clean master — an order-dependent flake, not a regression from this phase.

[2026-09-10T19:47:15Z · sase-z4.6.5.1--3] All just-check gates verified individually: fmt, ruff, mypy, symvision, toobig, pyscripts, test-waits, changelog, patch-stitch-terminology, validate, validate-committed-plans, and the full test-scoped suite (40338 passed) all pass. lint (feature flags) fails only due to unrelated pre-existing orphaned bead sase-z0 (filed as PROPOSED FOLLOW-UP). test-scoped's 8 failures are all diagnosed as pre-existing/unrelated: 5 pooled-alias tests + 2 test_workflow_executor.py tests confirmed via git stash -u to fail identically on clean origin/master (shared symptom: model resolution returns 'sonnet' instead of requested model — filed as PROPOSED FOLLOW-UP), plus 1 order-dependent flake (test_artifact_link_derivation.py) that passes in isolation on both this branch and master. Schema-version regression (AGENT_ARTIFACT_INDEX_SCHEMA_VERSION 26->27) fixed by vendoring the already-authored sase-core Rust changes via just rust-install. No epic-symbol leftovers. sase-core repo changes left uncommitted for host-owned finalizer.

## Dependencies

- **Blocks:** [sase-z4.6.5.2](sase-z4.6.5.2.md) ✓ · ⧖ 2026-09-10
- **Blocks:** [sase-z4.6.5.3](sase-z4.6.5.3.md) ◐ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-z4.6.5.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-z4.6.5.1.md) | [sase-z4.6.5.1](sase-z4.6.5.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3260f6a`](https://github.com/sase-org/sase/commit/3260f6a42b5f6ae22a5cab4473aacd7c6e2ebac1) | feat(runner-slots): make Rust candidate lineage authoritative at admission | [sase-z4.6.5.1](sase-z4.6.5.1.md) | 2026-09-10 15:49:06 EDT |
| sase-core | [`sase-core@120556a`](https://github.com/sase-org/sase-core/commit/120556af3243255921d640845d07686b544dca69) | feat(agent-scan): add runner\_claim\_owner\_key wire field and lineage lookup | [sase-z4.6.5.1](sase-z4.6.5.1.md) | 2026-09-10 15:51:20 EDT |
