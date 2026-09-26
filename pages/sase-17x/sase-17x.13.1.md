# Bead: sase-17x.13.1 — Move the sase-core CI pin past CommandLineGrammar

[Bead Pages](../README.md) / [sase-17x.13](sase-17x.13.md) / sase-17x.13.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17x.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17x.land.md) · **Assignee:** `sase-17x.13.1` · **Size:** xsmall
**Created:** 2026-09-24 20:28:40 EDT · **Closed:** 2026-09-24 20:57:35 EDT
**Plan:** [202609/command\_line\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_landing_fixes.md)

## Description

core-pin: ratchet `sase-core-revision.txt` to sase-core's remote HEAD so CI builds a core that exposes `CommandLineGrammar`, then prove the pinned-bindings check passes.

## Notes

[2026-09-25T00:57:35Z · sase-17x.13.1] Ratcheted sase-core-revision.txt 20ac645a7541 -> 83153645fe14 (contains 1bdadab CommandLineGrammar, verified via merge-base --is-ancestor). tools/check_sase_core_rs_bindings passes (all 695 bindings, exit 0). tests/completion/test_command_line_grammar.py: 4 passed. No epic-symbol leftovers. Pin change left uncommitted in working tree for host-owned finalizer.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.13.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.13.1/README.md) | [sase-17x.13.1](sase-17x.13.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d0df63a`](https://github.com/sase-org/sase/commit/d0df63a234329eec8414203bcae58e1671d7618d) | chore(core): ratchet sase-core pin to 83153645fe14 for CommandLineGrammar | [sase-17x.13.1](sase-17x.13.1.md) | 2026-09-24 20:59:41 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17x.13.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.13.1/README.md

<!-- sase:referenced-by:end -->
