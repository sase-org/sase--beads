# Bead: sase-56.1 — Phase 1: Directive registry migration (Rust core + Python parser + backend contract)

[Bead Pages](../README.md) / [sase-56](README.md) / sase-56.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-56.1`
**Created:** 2026-06-23 22:33:38 UTC · **Closed:** 2026-06-23 23:20:29 UTC
**Plan:** [202606/auto\_approve\_menu\_and\_tale\_directive.md](https://github.com/sase-org/sase--plans/blob/main/202606/auto_approve_menu_and_tale_directive.md)

## Notes

COMMIT: fff7ea07d

[2026-07-27T21:37:05Z · sase-a1.land] [2026-06-23T23:15:50Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Phase 1 complete. Rust (sase-core editor/directive.rs): %plan repurposed to normal-plan auto-approval, %tale added (alias %t), %time dropped %t alias, %approve/%a moved to hidden DEPRECATED_ALIASES still resolving to plan; cargo tests green. Python: _directive_types (drop approve from known, add plan+tale, aliases p/t/a/approve, _DEPRECATED_DIRECTIVE_ALIASES, tale field), directives.py (approve from 'plan' key, tale, has_deferred_start drops %t), directive_completion hints/desc + hide deprecated aliases, run_agent_directives tale block, plan_approve_handler PlanAutoApprovalAction+normalize tale, bead/work.py emits %plan, pylimit xprompt %plan. Docs updated. Tests updated/added; just lint+mypy+fmt green. Pre-existing unrelated failures: 8 invoke_agent tests fail only due to user config llm_provider.default_effort=xhigh (proven via git stash, independent of this change).

## Dependencies

- **Blocks:** [sase-56.2](sase-56.2.md) ✓
- **Blocks:** [sase-56.3](sase-56.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-56.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-56.1/README.md) | [sase-56.1](sase-56.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`4b22421`](https://github.com/sase-org/sase/commit/4b224219c1e52b68e163409b91f7b2c16b870361) | feat(directives)!: add %tale directive and repurpose %plan for plan auto-approval (sase-56.1) | [sase-56.1](sase-56.1.md) | 2026-06-23 23:22:07 |
