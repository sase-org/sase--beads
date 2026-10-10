# Bead: sase-1j6.10 — Finish update-skew agent auto-restart so it is safe and actually relaunches

[Bead Pages](../README.md) / [sase-1j6](README.md) / sase-1j6.10

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1j6.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1j6.land.md) · **Assignee:** `sase-1j6.10.land`
**Created:** 2026-10-10 08:09:05 EDT
**Plan:** [202610/finish\_update\_skew\_auto\_restart.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_update_skew_auto_restart.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/finish_update_skew_auto_restart.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/finish_update_skew_auto_restart.md

<!-- sase:links:end -->

## Description

Complete epic sase-1j6: the update-skew healer really relaunches pre-provider skew deaths once under the same name, touches nothing but skew-shaped failures, never spams or resurrects rows, records honest timestamps and provenance, keeps the episode report live, and leaves just check free of epic-caused failures.

## Notes

[2026-10-10T13:25:09Z · sase-1io.7.6.land] DISCOVERED ISSUE: v0.18.0 cannot publish while master imports auto-restart bindings that are not in the published sase-core-rs. PR 299 release-core-floor-smoke (job 114186958378, run 38043045593, 2026-10-10) failed check_sase_core_rs_bindings against floor 0.37.2, missing advance_auto_restart_ledger, agent_auto_restart_wire_schema_version, auto_restart_lineage_root, auto_restart_recovery_is_in_flight, claim_auto_restart_ledger, classify_agent_failure, and derive_auto_restart_episode. PyPI sase-core-rs is still 0.37.2. This is sase-1j6.10's core wire, not epic sase-1io.7.6. That epic will not edit the healer or cut a core release. Its ship waits until this epic has closed and a published core contains the bindings master imports. Full CI 38029274494 and Master Gate 38053026930 also failed auto-restart tests (including test_collect_journal_updates_bundle_window and test_default_config_matches_public_schema on spare_process_patterns). No duplicate task filed.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1j6.10.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.10.land/README.md) | [sase-1j6.10](sase-1j6.10.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1j6.10.2][1] | Need parent epic decisions, sibling phases, and design context for core-fixes | 1 |
| read-by | [agent:sase-1j6.10.6][2] | parent epic scope | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.10.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.10.6/README.md

<!-- sase:referenced-by:end -->
