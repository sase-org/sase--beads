# Bead: sase-1jc.11 — Stabilize sudo requests, provider drains, and autonomy records

[Bead Pages](../README.md) / [sase-1jc](README.md) / sase-1jc.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zb.md) · **Assignee:** `sase-1jc.11` · **Size:** medium
**Created:** 2026-10-09 22:28:27 EDT · **Closed:** 2026-10-10 16:59:13 EDT
**Plan:** [202610/retire\_all\_feature\_flags.md](https://github.com/sase-org/sase--plans/blob/main/202610/retire_all_feature_flags.md)

## Description

runtime-controls: Follow phase 11 and the shared removal checklist. Retire agent_sudo_requests, provider_drain, and autonomy_record_only; close sase-111, sase-sx, and sase-1j0. Remove beta refusal/no-drain/legacy-write branches. Preserve typed sudo review safeguards, automatic durable drains and current toasts, canonical autonomy writes, legacy read projection, and the plan-flow marker. Finish with an empty production registry.

## Notes

[2026-10-10T20:44:46Z · sase-1jc.11] PROPOSED FOLLOW-UP: Update sase/memory/macros.md temporary beta/rollout wording for now-unconditional typed sudo Proc launches (epic decision macro_memory=no skipped it)

[2026-10-10T20:44:51Z · sase-1jc.11] PROPOSED FOLLOW-UP: Update sase/memory/tui_perf.md rule 14 flag condition for now-unconditional refresh tokens while preserving performance requirements (epic decision refresh_memory=no skipped it)

[2026-10-10T20:44:56Z · sase-1jc.11] PROPOSED FOLLOW-UP: symvision NEW finding hint_lines in src/sase/ace/tui/modals/update_failure_geometry.py fails just check identically on the clean base tree (verified via stashed just _lint-symvision run); no bead tracks it

[2026-10-10T20:59:13Z · sase-1jc.11] Retired agent_sudo_requests, provider_drain, autonomy_record_only: production registry is empty (FeatureFlag members [] / definitions {}), dossiers sase-111/sase-sx/sase-1j0 closed. Deleted sudo/feature.py and all beta/no-drain/legacy-write branches; preserved typed sudo review, automatic durable drains with toasts, canonical autonomy writes, legacy read projection, and plan-flow marker. Schema regenerated; docs updated (framework help examples and saved-state reconciliation left for clean-slate phase). Verified: sase tool run check green except symvision hint_lines which fails identically on the clean base tree (recorded as PROPOSED FOLLOW-UP); all touched suites pass (sudo, drain, autonomy contract/record, modal, notification, enforcement, exec-retry, main CLI, feature_flags, doctor, terminology); epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1jc.10](sase-1jc.10.md) ✓ · ⧖ 2026-10-09
- **Blocks:** [sase-1jc.12](sase-1jc.12.md) ✓ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jc.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.11/README.md) | [sase-1jc.11](sase-1jc.11.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5235b17`](https://github.com/sase-org/sase/commit/5235b172744fdccc4a529945528f71a17ef89292) | feat(flags): retire runtime-controls flags agent\_sudo\_requests, provider\_drain, autonomy\_record\_only | [sase-1jc.11](sase-1jc.11.md) | 2026-10-10 17:00:43 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jc.11][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.11/README.md

<!-- sase:referenced-by:end -->
