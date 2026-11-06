# Bead: sase-1qz.2 — sase-core: escalation policy, continuation prompt, and config

[Bead Pages](../README.md) / [sase-1qz](README.md) / sase-1qz.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.research.33.linker.w0` · **Assignee:** `sase-1qz.2` · **Size:** medium
**Created:** 2026-11-02 17:42:14 EST · **Closed:** 2026-11-02 22:55:26 EST
**Plan:** [202611/agent\_hijack.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack.md)

## Description

core_escalation: add the never-downgrade escalation_target function and the continuation-prompt builder in sase-core with bindings and a pin bump, plus the agent_hijack config section (escalation_ladder, successor_context), its schema, and its accessor in sase.

## Notes

[2026-11-03T02:13:47Z · sase-1qz.2--2] --list

[2026-11-03T03:55:26Z · sase-1qz.2--3] core_escalation verified: sase-core never-downgrade escalation_target + continuation-prompt builder with PyO3 bindings (20 sase_core agent_hijack + 4 sase_core_py binding tests pass); live bindings return schema v1, normalize/escalate/switch/strip all correct. sase agent_hijack config (ladder @large,@xlarge, successor_context fork default) with schema, default_config, rendered docs + footprint catalog; 11 hijack + 24 pin-config sase tests pass; just _lint-symvision, fmt-py, docs-gen, ruff, mypy clean; epic-symbols: none left for sase-1qz.2 (9 symbols whitelisted for sase-1qz.6). Full just check escalates to full suite via Justfile rule and exceeds the turn budget, so verification is the targeted gates above (all green). sase-core pin ratchet past the new core commit deferred to stitch/land; core-floor-probe blocked_unpublished is advisory and pre-existing (27 unreleased caps).

## Dependencies

- **Blocks:** [sase-1qz.6](sase-1qz.6.md) ✓ · ⧖ 2026-11-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1qz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1qz.2.md) | [sase-1qz.2](sase-1qz.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@f1bbb4f`](https://github.com/sase-org/sase-core/commit/f1bbb4f3b81383c06df422c9df9fa13f0ec244f7) | feat(agent-hijack): add escalation policy and continuation-prompt core with bindings | [sase-1qz.2](sase-1qz.2.md) | 2026-11-02 23:27:54 EST |
| sase | [`38c3a3c`](https://github.com/sase-org/sase/commit/38c3a3c5fc92f6c3cb0d9887c7458a9e4666a178) | feat(agent-hijack): add Python escalation policy and continuation-prompt support | [sase-1qz.2](sase-1qz.2.md) | 2026-11-03 02:29:57 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.3a.final][1] | Check active epic phase scopes for conflict screening of task bead recommendations | 1 |
| read-by | [agent:sase-1qz.2--3][2] | Need full bead details and notes | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.final/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qz.2.md

<!-- sase:referenced-by:end -->
