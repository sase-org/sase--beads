# Bead: sase-1pj.6.1.1 — Define durable recovery identity and replay decisions

[Bead Pages](../README.md) / [sase-1pj.6.1](sase-1pj.6.1.md) / sase-1pj.6.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pj.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.6.md) · **Assignee:** `sase-1pj.6.1.1` · **Size:** medium
**Created:** 2026-10-31 08:56:54 EDT · **Closed:** 2026-10-31 10:32:49 EDT
**Plan:** [202610/staged\_handoff\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202610/staged_handoff_recovery.md)

## Description

recovery-contract: add Rust-owned recovery contracts and replay decisions, persist the original execution context, and serialize adoption across runner, manual recovery, and housekeeping callers. Preserve existing receipt formats.

## Notes

[2026-10-31T14:32:49Z · sase-1pj.6.1.1--2] recovery-contract complete: Rust-owned recovery identity (schema v1), adoption lock, receipt monotonicity, and replay decisions verified. Focused suites pass (26 passed: test_staged_recovery_contract, core/test_staged_handoff, test_axe_run_agent_exec_staged). sase tool run check passed (fe5341435227c2ec7522df3502468bde, exit 0, verdict pass). sase-core pin dddcb0b712600b5635df5bed91e1220c0b2bd31d already contains recovery.rs so no pin move. No epic-symbols remain. No memory edits per plan.

## Dependencies

- **Blocks:** [sase-1pj.6.1.2](sase-1pj.6.1.2.md) ◐ · ⧖ 2026-10-31
- **Blocks:** [sase-1pj.6.1.3](sase-1pj.6.1.3.md) ◐ · ⧖ 2026-10-31
- **Blocks:** [sase-1pj.6.1.4](sase-1pj.6.1.4.md) ◐ · ⧖ 2026-10-31
- **Blocks:** [sase-1pj.6.1.5](sase-1pj.6.1.5.md) ✓ · ⧖ 2026-10-31
- **Blocks:** [sase-1pj.6.1.6](sase-1pj.6.1.6.md) ◐ · ⧖ 2026-10-31

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.6.1.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.6.1.1.md) | [sase-1pj.6.1.1](sase-1pj.6.1.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@73ec04a`](https://github.com/sase-org/sase-core/commit/73ec04a02eb006f8065d01900f4e0d8605b252bb) | feat(staged-recovery): add Rust-owned recovery contracts and replay decisions | [sase-1pj.6.1.1](sase-1pj.6.1.1.md) | 2026-10-31 10:34:14 EDT |
| sase | [`d3d26a5`](https://github.com/sase-org/sase/commit/d3d26a5b55b81b1c86a159682c8f035e3c6354ed) | feat(staged-recovery): define durable recovery identity and replay decisions | [sase-1pj.6.1.1](sase-1pj.6.1.1.md) | 2026-10-31 10:36:20 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pj.6.1.1--2][1] | Need full bead incl notes | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.6.1.1.md

<!-- sase:referenced-by:end -->
