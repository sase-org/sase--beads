# Bead: sase-1ko.5 — Delivery-plan hook, active delivery, atomic legacy fallback, and helper manifests at the boundary

[Bead Pages](../README.md) / [sase-1ko](README.md) / sase-1ko.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.13.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.13.linker.w0.md) · **Assignee:** `sase-1ko.5` · **Size:** medium
**Created:** 2026-10-13 18:10:35 EDT · **Closed:** 2026-10-13 21:35:33 EDT
**Plan:** [202610/e3\_explicit\_delivery\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202610/e3_explicit_delivery_cutover.md)

## Description

delivery-plan: add the `llm_instruction_delivery` hookspec and the DeliveryPlan model, with declared-legacy built-ins. The boundary resolves the plan, renders the root bundle and (when declared) the helper bundle, validates transport, writes v2 manifests, and exposes the active delivery to adapters. It records session ids and falls back atomically to legacy delivery with a deduplicated notification. Bundle files become 0644.

## Notes

[2026-10-14T01:35:03Z · sase-1ko.5] PROPOSED FOLLOW-UP: ACE TUI session-hints flake — tests/ace/tui/widgets/test_agent_display_agent_session_hints.py::test_agent_session_content_hints_are_full_at_both_levels_and_use_phase_workspace failed NEW in sase tool run check b73e8af74b0282d6269f5f16b28f0364 and reproduced on clean HEAD 96090a52cf (missing src/*-prompt.py); already noted on sase-1kh.1.

[2026-10-14T01:35:10Z · sase-1ko.5] PROPOSED FOLLOW-UP: ACE TUI header-pin flake — tests/ace/tui/widgets/test_agent_header_panel_preview.py::test_bottom_pinned_body_stays_pinned_across_row_count_change failed NEW in the same check and independently of this phase; tracked by sase-1ki.

[2026-10-14T01:35:33Z · sase-1ko.5] delivery-plan landed: llm_instruction_delivery firstresult hook + DeliveryPlan/ActiveInstructionDelivery; all built-in providers declared-legacy (no live behavior change); invoke_with_instructions resolves the plan, renders root/helper when explicit, validates transport, writes v2 manifests (0644), binds active delivery, records session ids, and falls back atomically with deduplicated notify. Smoke: /tmp/sase-1ko.5-smoke/artifacts/instructions/00-claude.json schema_version=2 delivery.status=explicit channel=claude.append_system_prompt_file session_ids=['smoke-session-1']. sase tool run check b73e8af74b0282d6269f5f16b28f0364: delivery-plan tests passed; 2 NEW ACE TUI flakes reproduce on clean HEAD 96090a52cf (sase-1ki, sase-1kh.1 notes) plus 13 KNOWN/1 FLAKY. Post-check fixes: instruction-delivery in _COMMAND_SCRATCH_BUCKETS; TUI import-budget deferred via TYPE_CHECKING/function-level imports in _instruction_boundary.py. Targeted tests after those fixes passed (horizon, import budget, explicit v2+session). sase bead epic-symbols sase-1ko.5: none (current_instruction_delivery/sase_owned_instruction_paths keyed to sase-1ko.7).

## Dependencies

- **Depends on:** [sase-1ko.2](sase-1ko.2.md) ✓ · ⧖ 2026-10-13
- **Blocks:** [sase-1ko.6](sase-1ko.6.md) ✓ · ⧖ 2026-10-13
- **Blocks:** [sase-1ko.7](sase-1ko.7.md) ✓ · ⧖ 2026-10-13
- **Blocks:** [sase-1ko.8](sase-1ko.8.md) ✓ · ⧖ 2026-10-13
- **Blocks:** [sase-1ko.9](sase-1ko.9.md) ◐ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1ko.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ko.5/README.md) | [sase-1ko.5](sase-1ko.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d69cd49`](https://github.com/sase-org/sase/commit/d69cd499dd26b04534b9b4a11af540e14a6c73af) | feat(instructions): land delivery-plan hook and declared-legacy fallback | [sase-1ko.5](sase-1ko.5.md) | 2026-10-13 21:37:34 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ko.5][1] | Need notes remaining work and full description | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ko.5/README.md

<!-- sase:referenced-by:end -->
