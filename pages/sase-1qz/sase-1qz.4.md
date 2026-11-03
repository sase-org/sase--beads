# Bead: sase-1qz.4 — The stop protocol and \`sase agent hijack\`

[Bead Pages](../README.md) / [sase-1qz](README.md) / sase-1qz.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.33.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.33.linker.w0.md) · **Assignee:** `sase-1qz.4` · **Size:** medium
**Created:** 2026-11-02 17:42:15 EST · **Closed:** 2026-11-03 06:33:27 EST
**Plan:** [202611/agent\_hijack.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack.md)

## Description

stop: create the agent_hijack beta flag. Implement the ordered stop orchestrator: eligibility, record and intent, pin, durable signal, fallback settlement, survivors, lost race, then evidence and a strict snapshot before `held`. Expose it through `sase ops agent persist-hijack` and `sase agent hijack`.

## Notes

[2026-11-03T11:33:03Z · sase-1qz.4--2] PROPOSED FOLLOW-UP: full-check flakes under load — test_panel_shell_pilot (3), test_snippets_panel debounce, test_sudo_ledger_settlement defer/wait, test_app_import_budget, test_bump_microbench (2.265us vs 2us cap); each passes on solo retry or quiet clean base, no hijack code overlap

[2026-11-03T11:33:12Z · sase-1qz.4--2] PROPOSED FOLLOW-UP: publish glossary:agent-hijack strand at land time per epic DECISIONS glossary_term=yes (strand does not exist yet)

[2026-11-03T11:33:27Z · sase-1qz.4--2] stop protocol landed and verified: agent_hijack beta flag, ordered stop orchestrator stop_agent_for_hijack, sase agent hijack and persist-hijack ingress, 23 stop/ledger/help/snapshot tests green, help+snapshot fixed for new subcommands, full-check lint clean with only unrelated flaky timing failures passing on retry or clean base, epic-symbols clean

## Dependencies

- **Depends on:** [sase-1qz.3](sase-1qz.3.md) ✓ · ⧖ 2026-11-02
- **Blocks:** [sase-1qz.5](sase-1qz.5.md) ◐ · ⧖ 2026-11-02
- **Blocks:** [sase-1qz.8](sase-1qz.8.md) ◐ · ⧖ 2026-11-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1qz.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1qz.4.md) | [sase-1qz.4](sase-1qz.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f163ba7`](https://github.com/sase-org/sase/commit/f163ba74c0dc2a237133e5af68b5ad8fd72ce789) | feat(agent-hijack): add ordered stop orchestrator with hijack ingress | [sase-1qz.4](sase-1qz.4.md) | 2026-11-03 06:35:53 EST |
