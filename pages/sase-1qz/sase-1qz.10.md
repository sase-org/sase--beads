# Bead: sase-1qz.10 — Instruct and Edit through the prompt bar

[Bead Pages](../README.md) / [sase-1qz](README.md) / sase-1qz.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.research.33.linker.w0` · **Assignee:** `sase-1qz.10` · **Size:** medium
**Created:** 2026-11-02 17:42:18 EST · **Closed:** 2026-11-06 16:55:31 EST
**Plan:** [202611/agent\_hijack.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack.md)

## Description

tui_prompt: wire panel keys i and e to the prompt bar. Instruct pre-fills the continuation prompt and submits through recover. Edit pre-fills the original prompt and releases nothing until submit, so cancelling either leaves the agent HIJACKED.

## Notes

[2026-11-06T21:55:04Z · sase-1qz.10] PROPOSED FOLLOW-UP: just check _setup is blocked by a pre-existing sase-core skew (validate_sase_core_rs stale schema got 2 expected 1, checkout 0.43.3 vs pin 0.43.2); reproduces identically on the clean base tree

[2026-11-06T21:55:15Z · sase-1qz.10] PROPOSED FOLLOW-UP: symvision flags pre-existing private import _choice_for_enter_target in _agent_enter_action.py (imported by the tui_panel phase panel helper); reproduces identically on the clean base tree

[2026-11-06T21:55:31Z · sase-1qz.10] Implemented tui_prompt: panel i/e now open the prompt bar instead of coming-soon toasts. Instruct pre-fills the Rust continuation prompt with guidance slot and cursor on the guidance line, submits via persist-recover -a continue with the edited prompt; Edit pre-fills ,x reconstruction, submits via persist-recover -a restart, nothing dismissed at mount, cancel leaves HIJACKED, Edit snapshot failure stashes the draft. Verified: 10 new unit tests pass plus panel/preview/recover suites (32 passed); 6 hijack visual goldens check clean incl TZ=UTC, incl new agent_hijack_instruct_bar_80x24 golden (inspected). just check _setup and symvision failures reproduce identically on the clean base tree (recorded as PROPOSED FOLLOW-UPs).

## Dependencies

- **Blocks:** [sase-1qz.11](sase-1qz.11.md) ✓ · ⧖ 2026-11-02
- **Depends on:** [sase-1qz.9](sase-1qz.9.md) ✓ · ⧖ 2026-11-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1qz.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.10/README.md) | [sase-1qz.10](sase-1qz.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`039c4a8`](https://github.com/sase-org/sase/commit/039c4a858d7ced67bbb89699dcb3d737d9095b85) | feat(ace): wire hijack recovery panel Instruct and Edit through the prompt bar | [sase-1qz.10](sase-1qz.10.md) | 2026-11-06 16:57:29 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:18n][1] | Check in-progress hijack phase notes for deviations from the plan, for a user-facing report | 1 |
| read-by | [agent:research.3a.final][2] | Check active epic phase scopes for conflict screening of task bead recommendations | 1 |
| read-by | [agent:sase-1qz.10][3] | Need full bead including notes | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.18n/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.final/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.10/README.md

<!-- sase:referenced-by:end -->
