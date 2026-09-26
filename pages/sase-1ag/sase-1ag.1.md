# Bead: sase-1ag.1 — Restore shared project-tag selection and LSP edits

[Bead Pages](../README.md) / [sase-1ag](README.md) / sase-1ag.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1w](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.1w.md) · **Assignee:** `sase-1ag.1` · **Size:** medium
**Created:** 2026-09-26 07:27:39 EDT · **Closed:** 2026-09-26 08:00:33 EDT
**Plan:** [202609/restore\_project\_completion\_placement.md](https://github.com/sase-org/sase--plans/blob/main/202609/restore_project_completion_placement.md)

## Description

core: restore target-position insertion in sase-core and verify the Rust accept and LSP contracts.

## Notes

[2026-09-26T12:00:04Z · sase-1ag.1] PROPOSED FOLLOW-UP: sase-core `sase tool run check` gate fails on 6 pre-existing clippy style lints (manual_range_contains, nonminimal_bool) in agent_runtime.rs, agent_scan/index/maintenance.rs, fleet_owner_facts.rs, provider_usage/mod.rs, tool_run/store/triage.rs — flagged lines identical in HEAD, none in phase files; needs a clippy-cleanup stitch

[2026-09-26T12:00:33Z · sase-1ag.1] Restored target-position insertion in sase-core project_tag accept: trigger removed, row lands at earliest same-segment workspace target or segment leading position (frontmatter/ws/directive-aware), caret after insertion, LSP primary on trigger with nonoverlapping additional edits and coincident merge. Verified: sase_core project_tag 30/30, editor::completion 84/84, sase_core_py project_tag 8/8, sase_xprompt_lsp lib 168/168, fmt check clean; full check gate blocked only by 6 pre-existing clippy lints in untouched files (recorded as follow-up). No epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-1ag.2](sase-1ag.2.md) ◐ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1ag.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ag.1/README.md) | [sase-1ag.1](sase-1ag.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@24e8f58`](https://github.com/sase-org/sase-core/commit/24e8f5894f2f4c977ab637c29579b6e12f647820) | fix(core): restore target-position project-tag selection and LSP edits | [sase-1ag.1](sase-1ag.1.md) | 2026-09-26 08:01:58 EDT |
