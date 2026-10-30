# Bead: sase-1pu.5.1.3 — Add bounded report-and-apply repair for already-published runs

[Bead Pages](../README.md) / [sase-1pu.5.1](sase-1pu.5.1.md) / sase-1pu.5.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pu.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.5.md) · **Assignee:** `sase-1pu.5.1.3` · **Size:** medium
**Created:** 2026-10-29 20:35:52 EDT · **Closed:** 2026-10-30 03:05:17 EDT
**Plan:** [202610/published\_run\_state\_convergence.md](https://github.com/sase-org/sase--plans/blob/main/202610/published_run_state_convergence.md)

## Description

bounded-repair: implement the bounded state-reconciliation service and sase agent sync --repair-states mode specified below. Resolve exact local evidence for already-published runs, update only their state and derived projections, re-evaluate after upstream changes, and expose a resumable report cursor. Test read-only preview, bounds, hidden-clone ownership, publication races, failure recovery, and idempotence with temporary repositories.

## Notes

[2026-10-30T06:29:48Z · sase-1pu.5.1.3--1] WORK COMPLETE, CLOSE BLOCKED BY EPIC-SYMBOL GUARD (needs land-then-close): implemented bounded report-and-apply repair in src/sase/agents_sync/publication_state_repair.py with sase agent sync --repair-states/--state-limit/--state-after routing through src/sase/agents/cli_sync.py, src/sase/main/parser_agent_sync.py, src/sase/main/parser_root_args.py plus docs/reference/cli/agent.md and footprint catalog regen. VERIFIED: 19 temp-repo tests in tests/agents_sync/test_publication_state_repair.py + 3 CLI tests in tests/agents_sync/test_cli.py; pytest on both files = 72 passed in ~24s; ruff clean; mypy clean on both touched source files; just _lint-symvision green with the working-tree Justfile; recorded check run d437d7ae882a5d2031516fc1c0087ddc passed every fmt/lint/docs stage. BLOCKER: sase bead close refuses because origin/master Justfile still carries sase-1pu.5.1.3(select_agent_run_state_window), sase-1pu.5.1.3(AgentRunStateWindowRowWire), sase-1pu.5.1.3(agent_run_state_wire_schema_version); the working tree already drops those rows (all three symbols are wired up in the new service) and re-keys repair symbols to sase-1pu.5.1.4. LANDER: after host finalizers land this tree, re-run sase bead epic-symbols sase-1pu.5.1.3 (expect empty) then sase bead close sase-1pu.5.1.3 --note with the evidence above. PROPOSED FOLLOW-UP: full just check green on this diff was never observed — the Justfile edit escalates test selection to FULL_SUITE (5498 files) and the verify monitor 3q84vqn0djkj timed out at its 1h budget; core-floor-probe blocked_unpublished in the recorded run is advisory/pre-existing (sase-core checkout ahead of the pin, no action needed).

[2026-10-30T07:05:17Z · sase-1pu.5.1.3--1] Closed by explicit `sase stitch create -B close` after create_commit landed 5c14ac6a54 ("feat(agents-sync): add bounded report-and-apply repair for published run states"). The commit author requested bead completion after verifying the bead scope. Reopen with `sase bead open sase-1pu.5.1.3` if more work remains.

## Dependencies

- **Depends on:** [sase-1pu.5.1.2](sase-1pu.5.1.2.md) ✓ · ⧖ 2026-10-29
- **Blocks:** [sase-1pu.5.1.4](sase-1pu.5.1.4.md) ○ · ⧖ 2026-10-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pu.5.1.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.5.1.3.md) | [sase-1pu.5.1.3](sase-1pu.5.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5c14ac6`](https://github.com/sase-org/sase/commit/5c14ac6a54abce25f040ad491d817aaef9aec495) | feat(agents-sync): add bounded report-and-apply repair for published run states | [sase-1pu.5.1.3](sase-1pu.5.1.3.md) | 2026-10-30 03:00:33 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pu.5.1.3--1][1] | check closure state after host land | 22 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.5.1.3.md

<!-- sase:referenced-by:end -->
