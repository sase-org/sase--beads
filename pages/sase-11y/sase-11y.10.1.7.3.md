# Bead: sase-11y.10.1.7.3 — Delete the scheduler options the service path ignores

[Bead Pages](../README.md) / [sase-11y.10.1.7](sase-11y.10.1.7.md) / sase-11y.10.1.7.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.1.land.md) · **Assignee:** `sase-11y.10.1.7.3` · **Size:** small
**Created:** 2026-09-21 03:59:15 EDT · **Closed:** 2026-09-21 04:14:22 EDT
**Plan:** [202609/service\_host\_sunset\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_sunset_finish.md)

## Description

scheduler-cli: remove `-A/-H/-q/-z` from `sase scheduler start|restart` and their `sase axe` aliases and remove `restart -j`, keeping those overrides on `sase scheduler run`, then regenerate the CLI spec and completion snapshots.

## Notes

[2026-09-21T08:14:22Z · sase-11y.10.1.7.3] Removed -A/-H/-q/-z from scheduler start|restart and axe start|restart aliases, removed -j from scheduler/axe restart; overrides stay on scheduler run, -j stays on scheduler/axe status. Reworded start/stop/restart help to describe the service-host request. Renamed add_scheduler_overrides to private _add_scheduler_overrides per symvision. Regenerated cli_spec.json via just sync-completion-spec. Extended tests/main/test_parser_service_scheduler.py (flag absence, run/status retention, argparse-error assertions, help wording). Verified: 114 tests pass incl. completion snapshot/emit suites; live CLI rejects restart --json and start -A, run -h still documents overrides. sase tool run check is clean except the two plan-exempted sase-14j symvision items (bead_touch_glyph, ordered_bead_verb_chips). Grep found no in-repo or tools/ callers passing the removed flags.

## Dependencies

- **Blocks:** [sase-11y.10.1.7.5](sase-11y.10.1.7.5.md) ✓ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.7.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.10.1.7.3/README.md) | [sase-11y.10.1.7.3](sase-11y.10.1.7.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ff7efa0`](https://github.com/sase-org/sase/commit/ff7efa0190c8902f0282315ff54d9401943e9f69) | refactor(scheduler-cli): drop service-ignored options from scheduler start\|restart | [sase-11y.10.1.7.3](sase-11y.10.1.7.3.md) | 2026-09-21 04:16:32 EDT |
