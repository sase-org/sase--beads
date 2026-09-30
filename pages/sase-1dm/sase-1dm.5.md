# Bead: sase-1dm.5 — sase tool stats command, rendering, and docs

[Bead Pages](../README.md) / [sase-1dm](README.md) / sase-1dm.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u4.md) · **Assignee:** `sase-1dm.5` · **Size:** medium
**Created:** 2026-09-30 16:20:11 EDT · **Closed:** 2026-09-30 19:54:32 EDT
**Plan:** [202609/tool\_stats\_demand.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_stats_demand.md)

## Description

stats-cli: pin the core, add the Python facade and the sase tool stats subcommand with its JSON envelope and human tables, and document stats plus how its fields measure the parked E6, E7, and E8 reconsider conditions.

## Notes

[2026-09-30T23:54:03Z · sase-1dm.5] PROPOSED FOLLOW-UP: just check symvision gate fails on clean base too (NEW get_unread_set_generation in ace/tui plus 6 KNOWN); unrelated to stats-cli, needs triage owner

[2026-09-30T23:54:32Z · sase-1dm.5] stats-cli landed: facade tool_run_stats_report, sase tool stats -a/-d/-j/-t with JSON+host and Rich tables plus single-group STAGES/ROUTES/PROVIDERS/TREND and signal lines, docs in tool.md/cli.md/configuration.md. Verified: 18 tests pass (new test_stats_report incl e2e, import-weight, completion snapshot no drift), live -j and -t check render on athena (backtest 74pct/31.6x), exit 2 on bad -d and 0 on empty. just check otherwise green except symvision NEW+6 KNOWN reproduced identically on clean base (noted as follow-up).

## Dependencies

- **Depends on:** [sase-1dm.2](sase-1dm.2.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1dm.4](sase-1dm.4.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1dm.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1dm.5/README.md) | [sase-1dm.5](sase-1dm.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`be6daf9`](https://github.com/sase-org/sase/commit/be6daf95d156f7df1a95d2ac3055ff400fd4cad2) | feat(tool): add sase tool stats report command | [sase-1dm.5](sase-1dm.5.md) | 2026-09-30 19:57:19 EDT |
