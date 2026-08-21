# Bead: sase-s0.2 — Host catalog and ACE prompt experience

[Bead Pages](../README.md) / [sase-s0](README.md) / sase-s0.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-rr.land.w1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-rr.land.w1.md) · **Assignee:** `sase-s0.2` · **Size:** medium
**Created:** 2026-08-21 20:34:59 UTC · **Closed:** 2026-08-21 21:45:47 UTC
**Plan:** [202608/final\_directive\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/final_directive_completion.md)

## Description

host_prompt_experience: derive cached completion rows from effective finalizer config and integrate responsive, polished ACE completion.

## Notes

[2026-08-21T21:43:34Z · sase-s0.2] PROPOSED FOLLOW-UP: live flag bead sase-ro still names retired pluggable_finalizers with no registry definition, so just check flag lint fails repo-wide — close or retarget that flag bead

[2026-08-21T21:43:50Z · sase-s0.2] PROPOSED FOLLOW-UP: tests/contract_manifest.txt has 54 entries against a 53-entry budget (extra tests/test_xprompt_workflow_schema.py); this is on HEAD and unrelated to host %final completion

[2026-08-21T21:44:06Z · sase-s0.2] PROPOSED FOLLOW-UP: tests/main/test_skills_handler.py::test_skills_inventory_reports_retired_deletion_drift failed once in a full-suite run then passed on rerun — likely a flake

[2026-08-21T21:45:47Z · sase-s0.2] Host catalog and ACE %final argument completion: config-token catalog builder in policy order; helper-bridge finalizer-catalog fail-closed envelope with schema v1 and mixed-version extras ignored; ACE warms inventory off-thread on mount, maps Rust candidates into FinalizerCompletionMetadata, and renders required/default/optional/remove/clear rows. %final name completion stays hidden. Verified: 36 targeted tests, PNG goldens at 120x40 and 70x24, just test-visual for those fixtures, fmt/ruff/mypy/symvision, and colon-form ! classification. just check still fails on unrelated live flag bead sase-ro (retired pluggable_finalizers); full-suite escalation had pre-existing contract-manifest budget 54>53 and one flake that passed on rerun.

## Dependencies

- **Depends on:** [sase-s0.1](sase-s0.1.md) ✓ · ⧖ 2026-08-21
- **Blocks:** [sase-s0.3](sase-s0.3.md) ◐ · ⧖ 2026-08-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-s0.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s0.2/README.md) | [sase-s0.2](sase-s0.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f88c9ed`](https://github.com/sase-org/sase/commit/f88c9eded9ea9b6395415d27ecd4a9babb5c970c) | feat(completion): add host %final catalog and ACE argument completion | [sase-s0.2](sase-s0.2.md) | 2026-08-21 21:46:53 UTC |
