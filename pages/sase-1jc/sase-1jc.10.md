# Bead: sase-1jc.10 — Stabilize provider instruction and execution channels

[Bead Pages](../README.md) / [sase-1jc](README.md) / sase-1jc.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zb.md) · **Assignee:** `sase-1jc.10` · **Size:** medium
**Created:** 2026-10-09 22:28:26 EDT · **Closed:** 2026-10-10 16:15:21 EDT
**Plan:** [202610/retire\_all\_feature\_flags.md](https://github.com/sase-org/sase--plans/blob/main/202610/retire_all_feature_flags.md)

## Description

provider-instructions: Follow phase 10 and the shared removal checklist. Retire muse_synchronous_shell, grok_rules_delivery, claude_helper_channel, and instruction_shadow_render; close sase-178, sase-1gv, sase-1gw, and sase-1h4. Keep synchronous Muse execution, root Grok rules, supported Claude helper channels/guards, and fail-open shadow rendering. Delete flag resolution and disabled variants without converting shadow rendering into a new delivery cutover.

## Notes

[2026-10-10T19:18:32Z · sase-1jc.10] PROPOSED FOLLOW-UP: Update sase/memory/macros.md to describe typed Proc launches as unconditional (epic decision macro_memory=no skipped it)

[2026-10-10T19:18:37Z · sase-1jc.10] PROPOSED FOLLOW-UP: Update sase/memory/tui_perf.md rule 14 to describe refresh tokens as unconditional (epic decision refresh_memory=no skipped it)

[2026-10-10T20:15:02Z · sase-1jc.10] PROPOSED FOLLOW-UP: just check (tool run 4eaa003b821f1662ef67348ea1bb89a8) shows 4 failed + 1 error, all pre-existing on the clean base tree: test_contract_manifest_matches_marker_selection + test_node_finder_snapshot ImportError (epic sase-1jc note #6, sase-1jc.6 leftover), test_tracked_marker_path_passing_sites_are_reviewed (fails identically on base), plus triage-FLAKY test_bob_dry_run_canonical_report_has_no_digest_suffix and test_tui_app_import_stays_under_startup_budget

[2026-10-10T20:15:21Z · sase-1jc.10] Retired muse_synchronous_shell, grok_rules_delivery, claude_helper_channel, instruction_shadow_render: removed 4 registry members/definitions, made Muse --enable-shell-tool + sync directive + 600s ceiling unconditional, Grok --rules always sent, Claude guard+template always on (probe-gated template kept), shadow render unconditional on artifacts-dir (fail-open, still shadow-only). Closed dossiers sase-178, sase-1gv, sase-1gw, sase-1h4. Verified: tools/check_feature_flags exit 0, schema regenerated, 137 focused tests pass, just check (tool run 4eaa003b821f1662ef67348ea1bb89a8) has only base-identical pre-existing failures (recorded as follow-up). No --epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-1jc.11](sase-1jc.11.md) ✓ · ⧖ 2026-10-09
- **Depends on:** [sase-1jc.9](sase-1jc.9.md) ✓ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jc.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.10/README.md) | [sase-1jc.10](sase-1jc.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2c9f761`](https://github.com/sase-org/sase/commit/2c9f76121008a07b7c8be248ebbddae983f45b1c) | feat(providers): retire provider-instructions sunset flags | [sase-1jc.10](sase-1jc.10.md) | 2026-10-10 16:17:29 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:6h--1][1] | Concurrent epic closed flag beads that are failing this workspace just check | 1 |
| read-by | [agent:sase-1jc.10][2] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1jm.2.1.6--1][3] | Check whether the existing provider instruction phase tracks the stale feature-flag definitions reported by just check | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.6h.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.10/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.2.1.6.md

<!-- sase:referenced-by:end -->
