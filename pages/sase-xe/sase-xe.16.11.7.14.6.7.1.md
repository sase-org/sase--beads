# Bead: sase-xe.16.11.7.14.6.7.1 — Preserve workspace and remote targeting through approved admission

[Bead Pages](../README.md) / [sase-xe.16.11.7.14.6.7](sase-xe.16.11.7.14.6.7.md) / sase-xe.16.11.7.14.6.7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0jc](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0jc.md) · **Assignee:** `sase-xe.16.11.7.14.6.7.1` · **Size:** medium
**Created:** 2026-09-11 09:46:26 EDT · **Closed:** 2026-09-11 11:12:34 EDT
**Plan:** [202609/launch\_recovery\_and\_xe\_closeout.md](https://github.com/sase-org/sase--plans/blob/main/202609/launch_recovery_and_xe_closeout.md)

## Description

launch-targets: repair the Rust typed launch round trip and Python approved dispatch path, including remote identity and durable receipt handling; prove the reviewed project and machine are the actual execution targets.

## Notes

[2026-09-11T15:12:34Z · sase-xe.16.11.7.14.6.7.1] Verified launch-targets: typed AgentUnitWire now keeps per-unit workspace_provider/workspace_reference and dispatch_target through parse, digest, approval preview, and dispatch reconstruction; plan-wide selected_project no longer replaces a unit's #gh/#git tag. Approved admission routes remote units through dispatch/launch.py (stable fingerprint request_id, no local/home fallback) and local units through launch_agents_from_cwd. Gateway omits bridge name when the prompt already has %id; source dispatch no longer injects an operation-derived name on top of prompt identity. Coverage: sase_core agent_launch + gateway fleet_launch_omits_bridge_name_when_prompt_has_id; Python tests/test_launch_admission_remote_targets.py (incident prompt, mixed local/remote, offline, dirty-source refusal, duplicate operation key, uncertain receipt), test_dispatch_launch identity injection, test_mobile_agent_launch_text matching/conflicting %id, test_direct_typed_launch. sase-core fmt-check and clippy --workspace passed. just check lint passed except pre-existing live flag beads sase-z6/sase-z9 owned by later/other work.

## Dependencies

- **Blocks:** [sase-xe.16.11.7.14.6.7.3](sase-xe.16.11.7.14.6.7.3.md) ◐ · ⧖ 2026-09-11
- **Blocks:** [sase-xe.16.11.7.14.6.7.4](sase-xe.16.11.7.14.6.7.4.md) ◐ · ⧖ 2026-09-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.11.7.14.6.7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.11.7.14.6.7.1/README.md) | [sase-xe.16.11.7.14.6.7.1](sase-xe.16.11.7.14.6.7.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5428b99`](https://github.com/sase-org/sase/commit/5428b994392987a7155d9661112ae6fba7aac67e) | fix(agent-launch): preserve workspace and remote targeting through approved admission | [sase-xe.16.11.7.14.6.7.1](sase-xe.16.11.7.14.6.7.1.md) | 2026-09-11 11:14:05 EDT |
| sase-core | [`sase-core@4775e9e`](https://github.com/sase-org/sase-core/commit/4775e9eb2caf3a493fe18fba9ee7a946ecfaff9a) | fix(agent-launch): preserve per-unit workspace refs and remote dispatch through typed admission | [sase-xe.16.11.7.14.6.7.1](sase-xe.16.11.7.14.6.7.1.md) | 2026-09-11 11:42:33 EDT |
