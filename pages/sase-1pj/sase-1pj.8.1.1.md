# Bead: sase-1pj.8.1.1 — Make plan, questions, and pipe commands stage unconditionally

[Bead Pages](../README.md) / [sase-1pj.8.1](sase-1pj.8.1.md) / sase-1pj.8.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pj.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.8.md) · **Assignee:** `sase-1pj.8.1.1` · **Size:** medium
**Created:** 2026-11-02 20:59:31 EST · **Closed:** 2026-11-02 21:40:58 EST
**Plan:** [202611/retire\_staged\_handoff\_kill\_path.md](https://github.com/sase-org/sase--plans/blob/main/202611/retire_staged_handoff_kill_path.md)

## Description

command-staging: remove legacy branches from plan, questions, and pipe entry points and migrate their command tests.

## Notes

[2026-11-03T02:11:42Z · sase-1pj.8.1.1] PROPOSED FOLLOW-UP: Fix multi-hop staged pipe adoption — tests/fakey/test_pipe_e2e.py reaches adoption on the second pipe handoff, but shared adoption rejects persisted agent fakey-e2e--1 because the active runner context still identifies fakey-e2e; restore the two-hop integration coverage when the runtime adoption path is repaired.

[2026-11-03T02:40:58Z · sase-1pj.8.1.1] Removed legacy non-staged branches from plan, questions, and pipe; migrated command tests and refreshed parser-derived CLI docs, completion snapshot, and footprint catalog. The focused command/artifact suite passes (149 tests), git diff --check is clean, and epic-symbols reports no leftovers. Recorded the existing multi-hop staged adoption identity mismatch as a proposed follow-up.

## Dependencies

- **Blocks:** [sase-1pj.8.1.4](sase-1pj.8.1.4.md) ✓ · ⧖ 2026-11-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.8.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.8.1.1/README.md) | [sase-1pj.8.1.1](sase-1pj.8.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f425458`](https://github.com/sase-org/sase/commit/f4254582d85133bb649f097cf7b5a5bad26a5803) | feat(cli): stage plan, questions, and pipe handoffs unconditionally | [sase-1pj.8.1.1](sase-1pj.8.1.1.md) | 2026-11-02 21:42:09 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pj.8.1.1][1] | Verify the assigned phase bead was closed | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.8.1.1/README.md

<!-- sase:referenced-by:end -->
