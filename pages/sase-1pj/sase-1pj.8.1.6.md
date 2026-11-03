# Bead: sase-1pj.8.1.6 — Connect instruction readout to the core policy

[Bead Pages](../README.md) / [sase-1pj.8.1](sase-1pj.8.1.md) / sase-1pj.8.1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pj.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.8.md) · **Assignee:** `sase-1pj.8.1.6` · **Size:** medium
**Created:** 2026-11-02 20:59:32 EST · **Closed:** 2026-11-02 22:13:42 EST
**Plan:** [202611/retire\_staged\_handoff\_kill\_path.md](https://github.com/sase-org/sase--plans/blob/main/202611/retire_staged_handoff_kill_path.md)

## Description

readout-adapter: gather staged, receipt, declaration, and historical facts in Python, use the Rust classifier, advance the core revision pin, and cover the scoring matrix.

## Notes

[2026-11-03T03:13:42Z · sase-1pj.8.1.6] readout-adapter done: Python gathers staged record/receipt, handoff_protocol, lifecycle, declaration, prepared-intent facts plus bounded legacy tail scan and delegates precedence to Rust classify_instruction_readout via new sase.core.instruction_readout adapter; pin ratcheted to 6cd64a9c. Verified: focused readout suite 32/32, full tests/instructions 212 green, related handler/verify/monitor/finalizer suites green, all just-check lint gates green (ruff, mypy, symvision, feature-flags, docs). Full scoped test lane stalled on host load (load1>25, run cef05dda stopped); change surface fully covered by the green suites above.

## Dependencies

- **Depends on:** [sase-1pj.8.1.5](sase-1pj.8.1.5.md) ✓ · ⧖ 2026-11-02
- **Blocks:** [sase-1pj.8.1.7](sase-1pj.8.1.7.md) ✓ · ⧖ 2026-11-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.8.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.8.1.6/README.md) | [sase-1pj.8.1.6](sase-1pj.8.1.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`11147cc`](https://github.com/sase-org/sase/commit/11147ccf2f15c7d890f6ee11de7147de4412c920) | feat(readout): delegate instruction readout classification to Rust core | [sase-1pj.8.1.6](sase-1pj.8.1.6.md) | 2026-11-02 22:15:51 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pj.8.1.6][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.8.1.6/README.md

<!-- sase:referenced-by:end -->
