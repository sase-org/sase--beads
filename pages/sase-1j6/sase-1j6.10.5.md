# Bead: sase-1j6.10.5 — Make the healer relaunch, settle, and escalate correctly end to end

[Bead Pages](../README.md) / [sase-1j6.10](sase-1j6.10.md) / sase-1j6.10.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1j6.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1j6.land.md) · **Assignee:** `sase-1j6.10.5` · **Size:** medium
**Created:** 2026-10-10 08:09:08 EDT
**Plan:** [202610/finish\_update\_skew\_auto\_restart.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_update_skew_auto_restart.md)

## Description

healer-relaunch: move the sase-core pin past core-fixes, re-classify with the probe witness so a passing probe relaunches, pass real timestamps, escalate expired deferrals, take over stale claims properly, escalate a replacement's second failure as already_restarted, write in-flight recovery states with ledger_key and episode_id, record real from/to revisions in provenance, scrub the provenance env, order -p targets topologically, and prove it with an un-mocked classifier test.

## Dependencies

- **Depends on:** [sase-1j6.10.1](sase-1j6.10.1.md) ◐ · ⧖ 2026-10-10
- **Depends on:** [sase-1j6.10.2](sase-1j6.10.2.md) ◐ · ⧖ 2026-10-10
- **Depends on:** [sase-1j6.10.3](sase-1j6.10.3.md) ◐ · ⧖ 2026-10-10
- **Blocks:** [sase-1j6.10.6](sase-1j6.10.6.md) ◐ · ⧖ 2026-10-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1j6.10.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.10.5/README.md) | [sase-1j6.10.5](sase-1j6.10.5.md) | 0 |
