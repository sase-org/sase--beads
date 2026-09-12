# Bead: sase-zw.6 — Share Git objects across managed workspace checkouts

[Bead Pages](../README.md) / [sase-zw](README.md) / sase-zw.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ka](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ka.md) · **Assignee:** `sase-zw.6` · **Size:** large
**Created:** 2026-09-12 13:26:45 EDT · **Closed:** 2026-09-12 19:26:06 EDT
**Plan:** [202609/bound\_sase\_disk\_footprint.md](https://github.com/sase-org/sase--plans/blob/main/202609/bound_sase_disk_footprint.md)

## Description

wsobjects: stop every managed checkout from carrying its own full copy of the primary's pack, and retrofit the existing checkouts.

## Notes

[2026-09-12T23:25:35Z · sase-zw.6] PROPOSED FOLLOW-UP: investigate broad-suite/order flakiness in tests/main/test_var_integration.py::test_var_cli_end_to_end_refreshes_index_and_round_trips_machine_outputs and tests/test_agent_load_tiering_harness.py::test_load_tiering_oracle_reports_under_selecting_candidate_filter. During this phase, both just check and just check-full full-suite lanes failed these tests under heavy concurrent load, but the same tests passed repeatedly when rerun directly, under xdist -n8, and with the cost/global-leak plugins.
PROPOSED FOLLOW-UP: fix sase monitor start project inference for managed checkouts whose .sase/checkout.json project_name is the display name `sase` while agent artifacts live under canonical project key gh_sase-org__sase. Monitor start could not bind this phase because it looked for agent artifacts in project `sase`.

[2026-09-12T23:26:06Z · sase-zw.6] Implemented shared Git object borrowing for managed workspaces: new Git object-sharing helper layer, shared clone/repair/dissociation paths, workspace.share_git_objects config/schema/docs, `sase workspace compact`, completion snapshot updates, and focused tests for clone/compact/repair/parser behavior. Verification: focused workspace-provider/main/parser/completion/github-cli tests passed; git diff --check passed; real checkout #33 compacted from 1,946,907,024 local object bytes to 15,815,380 bytes (1,931,091,644 bytes reclaimed), with fsck/fetch/status/install validation passing and captured just install exiting 0. `sase bead epic-symbols sase-zw.6` reported no entries. Broad verification caveat: `just check` and `just check-full` full-suite lanes both reached the full pytest lane but failed the same unrelated/order-sensitive tests under load; those failing tests passed repeatedly when rerun directly, under xdist, and with the cost/global-leak plugins. Monitor handoff was attempted but blocked by the project-name/canonical-key alias issue recorded as a proposed follow-up.

## Dependencies

- **Blocks:** [sase-zw.7](sase-zw.7.md) ◐ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zw.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zw.6.md) | [sase-zw.6](sase-zw.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4460e13`](https://github.com/sase-org/sase/commit/4460e13c4465fa36f2394f88a0723d67d7bb5970) | feat(workspace): share git objects across checkouts | [sase-zw.6](sase-zw.6.md) | 2026-09-12 19:57:44 EDT |
