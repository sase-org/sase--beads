# Bead: sase-m9.2.1.5 — Service cutover and compatibility verification

[Bead Pages](../README.md) / [sase-m9.2.1](sase-m9.2.1.md) / sase-m9.2.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m9.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.2.md) · **Assignee:** `sase-m9.2.1.5` · **Size:** medium
**Created:** 2026-08-15 06:15:08 EDT · **Closed:** 2026-08-15 10:07:14 EDT
**Plan:** [202608/unified\_proc\_shell\_platform\_1.md](https://github.com/sase-org/sase--plans/blob/main/202608/unified_proc_shell_platform_1.md)

## Description

proc-platform-cutover: collapse bead task/epic launch monitoring onto the shared service and audit all remaining proc/monitor writers so new records use the unified lifecycle while legacy readers and control paths remain intact. Verify consistent ids, state, logs, names, and family projections across proc CLI, monitor CLI, agent listings, and current ACE observation without migrating ACE-owned producer APIs reserved for the following parent phase. Exercise concurrent processes, replay/conflict diagnostics, crash recovery at every settlement boundary, reboot and pid reuse, retention of artifacts-owned logs, and old store fixtures. Update the generated monitor skill source and user documentation, run just install and focused suites throughout, then run just check-full via sase monitor with a follow-up action; run visual tests only if existing ACE rendering changes.

## Notes

[2026-08-15T13:52:41Z · sase-m9.2.1.5] PROPOSED FOLLOW-UP: sase monitor start (no --agent given) fails for any phase-bead worker agent whose SASE_AGENT_NAME ends in ".N" with N>=2 (e.g. sase-m9.2.1.5) — default_lane() -> agent_family_base() in src/sase/plan_chain.py misparses the trailing ".5" as a legacy plan-chain feedback-round suffix (_FEEDBACK_SUFFIX_RE matches "[-.](\d+)$" with round>=2) and derives lane "sase-m9.2.1" instead of the agents own name, so promote_agent_to_family then raises FamilyAttachError("Cannot create agent family 'sase-m9.2.1': resolved parent is named 'sase-m9.2.1.5'"). Passing --agent "$SASE_AGENT_NAME" explicitly works around it (bypasses default_lane()). Since bead-phase-worker agent names commonly end in ".2"/".3"/etc for any epic phase beyond the first, this silently breaks self-targeting "sase monitor start" for most phase workers who omit --agent; worth a fix in agent_family_base/_split_agent_family_name (or default_lane) to not treat a hierarchical bead-id-shaped name as a legacy feedback-round suffix.

[2026-08-15T14:07:14Z · sase-m9.2.1.5--1] Audited proc/monitor writer paths and confirmed shared proc-service routing with the ACE proc mirror intentionally excluded, documented named proc shell addressing in docs/cli.md and docs/ace.md, recorded the phase-agent lane-resolution bug as a PROPOSED FOLLOW-UP, and verified focused suites plus check-full with only the known test_settlement_resumes_after_an_injected_crash flake, which passed alone.

[2026-08-15T14:08:43Z · sase-m9.2.1.5--1] Verified proc and monitor writer audit, documented named proc shell addressing in docs/cli.md and docs/ace.md, recorded the phase-worker lane-resolution bug as PROPOSED FOLLOW-UP, and ran check-full with only the known test_settlement_resumes_after_an_injected_crash flake, which passed in isolation.

## Dependencies

- **Depends on:** [sase-m9.2.1.4](sase-m9.2.1.4.md) ✓ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m9.2.1.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.2.1.5.md) | [sase-m9.2.1.5](sase-m9.2.1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6683d4b`](https://github.com/sase-org/sase/commit/6683d4bcc25c173a5a5903e1884271f0acb3f937) | docs: document named proc shell addressing | [sase-m9.2.1.5](sase-m9.2.1.5.md) | 2026-08-15 10:09:31 EDT |
