# Bead: sase-vs.4 — Accept \`wait\` on the plan gate approval options

[Bead Pages](../README.md) / [sase-vs](README.md) / sase-vs.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ga](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ga.md) · **Assignee:** `sase-vs.4` · **Size:** medium
**Created:** 2026-08-30 07:22:01 EDT · **Closed:** 2026-08-30 09:16:51 EDT
**Plan:** [202608/approval\_wait\_argument.md](https://github.com/sase-org/sase--plans/blob/main/202608/approval_wait_argument.md)

## Description

gate_wait_input: declare `wait` on the tale and epic approval option schemas, validate it in the gate command, and route the parsed result into the coder prompt and the epic launch.

## Notes

[2026-08-30T13:16:51Z · sase-vs.4] Declared wait on tale approve/commit and epic approve input schemas, and wait_agents/wait_beads string arrays on approving result schemas. execute_plan_gate_command parses wait via parse_wait_spec (exit 2 on WaitSpecError). plan_response_json/plan_response_json_for_selection emit wait fields when the selection runs a coder or is an epic approval; commit-only drops them. translate_plan_gate_response copies wait_agents/wait_beads from the approve option result. execute_plan_approval_response parses wait once before mutation, puts the raw spec into tale approve/commit and epic approve input_data on the neutral path, and forwards the parsed spec to plan_response_json and prepare_epic_launch on the legacy path. Epic adapter reconstructs PromptWaitDirective from the merged result and passes it to prepare_epic_launch; launch argv carries --wait. Compatibility: a pre-upgrade plan gate (schema without wait) rejects --set wait= with the ordinary 'no selected option accepts that input' error, not a crash. Golden schema updates for both tiers; command, translation, adapter argv, and tale coder-successor %wait tests. just check green.

## Dependencies

- **Depends on:** [sase-vs.2](sase-vs.2.md) ✓ · ⧖ 2026-08-30
- **Depends on:** [sase-vs.3](sase-vs.3.md) ✓ · ⧖ 2026-08-30
- **Blocks:** [sase-vs.5](sase-vs.5.md) ✓ · ⧖ 2026-08-30
- **Blocks:** [sase-vs.6](sase-vs.6.md) ✓ · ⧖ 2026-08-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-vs.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vs.4/README.md) | [sase-vs.4](sase-vs.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`15be5ac`](https://github.com/sase-org/sase/commit/15be5ac470cafd2f31ba03b511ae11b959c951d6) | feat(plan): accept wait on tale and epic approval options | [sase-vs.4](sase-vs.4.md) | 2026-08-30 09:18:29 EDT |
