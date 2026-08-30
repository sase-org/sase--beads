# Bead: sase-vs.2 — Carry approval waits into the tale coder prompt

[Bead Pages](../README.md) / [sase-vs](README.md) / sase-vs.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ga](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ga.md) · **Assignee:** `sase-vs.2` · **Size:** small
**Created:** 2026-08-30 07:21:59 EDT · **Closed:** 2026-08-30 07:59:02 EDT
**Plan:** [202608/approval\_wait\_argument.md](https://github.com/sase-org/sase--plans/blob/main/202608/approval_wait_argument.md)

## Description

tale_coder_wait: give `PlanApprovalResult` wait fields and stamp a canonical `%wait(...)` directive onto the approved tale's coder successor prompt.

## Notes

[2026-08-30T11:58:29Z · sase-vs.2] PROPOSED FOLLOW-UP: just rust-lsp-install copies from sase-core/target/release and misses cargo config target-dir /mnt/poseidon/cargo-target, leaving a stale .venv sase-xprompt-lsp that fails ACE/LSP wait-range parity

[2026-08-30T11:59:02Z · sase-vs.2] PlanApprovalResult now carries wait_agents/wait_beads from the translated gate response (lists of non-empty strings only). prepare_accepted_plan_successor stamps canonical %wait via set_prompt_wait when either tuple is non-empty and leaves the empty case unrewritten. Golden coder-prompt tests cover agents-only, beads-only, mixed, and empty; rewritten prompts still parse to %model:@small, #gh:sase, and @plan.md. just check green.

## Dependencies

- **Blocks:** [sase-vs.4](sase-vs.4.md) ◐ · ⧖ 2026-08-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-vs.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vs.2/README.md) | [sase-vs.2](sase-vs.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6e0e586`](https://github.com/sase-org/sase/commit/6e0e5860b0bcf4e1b08a50e68a72c32c62e1c5bd) | feat(plan-approval): stamp approval waits onto the tale coder successor prompt | [sase-vs.2](sase-vs.2.md) | 2026-08-30 08:00:09 EDT |
