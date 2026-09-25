# Bead: sase-19f.3 — sase launch, persistence, admission, and continuation plumbing

[Bead Pages](../README.md) / [sase-19f](README.md) / sase-19f.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1o](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.1o.md) · **Assignee:** `sase-19f.3` · **Size:** medium
**Created:** 2026-09-25 12:24:38 EDT · **Closed:** 2026-09-25 18:01:37 EDT
**Plan:** [202609/queue\_capacity\_multiplier.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_capacity_multiplier.md)

## Description

sase-plumbing: bump the sase-core pin. Then carry `queue_capacity_multiplier` from directive extraction through agent_meta and waiting markers, runner-slot admission records, typed-unit and proc admission, and continuation reauthoring. Update the xprompt and runner-slot docs.

## Notes

[2026-09-25T18:11:01Z · sase-19f.3] PROPOSED FOLLOW-UP: sase/memory/xprompts.md %queue paragraph ("authored positive integer N") should mention <M>x multipliers (e.g. %q(1.5x, w=0.25) resolving against the effective max_running_agents budget)

[2026-09-25T22:01:18Z · sase-19f.3--6] PROPOSED FOLLOW-UP: Symvision fails on the clean base because cli_work_cleanup_selection imports private _OwnerRecordLookup from cli_work_cleanup_targets; make the shared Protocol public or eliminate the cross-file import.

[2026-09-25T22:01:37Z · sase-19f.3--6] Implemented queue_capacity_multiplier plumbing from directive extraction through metadata, waiting/admission records, typed units/proc admission, launch/scan wires, and continuation reauthoring; updated docs and core pin. Rebuilt sase_core_rs, ran 133 focused multiplier tests and just fix. sase tool run check passed formatting, ruff, mypy, and all preceding lint stages but is blocked by an identical clean-base Symvision private-import failure, recorded as a proposed follow-up.

## Dependencies

- **Depends on:** [sase-19f.2](sase-19f.2.md) ✓ · ⧖ 2026-09-25
- **Blocks:** [sase-19f.4](sase-19f.4.md) ✓ · ⧖ 2026-09-25
- **Blocks:** [sase-19f.5](sase-19f.5.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-19f.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-19f.3.md) | [sase-19f.3](sase-19f.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6beedbc`](https://github.com/sase-org/sase/commit/6beedbc118b8e06d92fdb9145d847e21aab87065) | feat(xprompt): add queue capacity multiplier plumbing | [sase-19f.3](sase-19f.3.md) | 2026-09-25 19:20:15 EDT |
