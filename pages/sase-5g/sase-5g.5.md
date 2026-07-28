# Bead: sase-5g.5 — Phase 5: agent\_family YAML: custom roles as data

[Bead Pages](../README.md) / [sase-5g](README.md) / sase-5g.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5g.5`
**Created:** 2026-07-06 06:19:11 UTC · **Closed:** 2026-07-06 11:17:44 UTC
**Plan:** [202607/dynamic\_agent\_families\_v2.md](https://github.com/sase-org/sase--plans/blob/main/202607/dynamic_agent_families_v2.md)

## Notes

COMMIT: b1e037c91

[2026-07-27T21:38:13Z · sase-a1.land] [2026-07-06T11:15:11Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Phase 5 complete: added file-backed kind: agent_family YAML loading/validation, active custom-role discovery in xprompt roots, xprompt-list catalog visibility, inactive bundled improve_plan/tester examples plus prompt templates, and workflow-loader skipping for agent_family YAML. Extended the standard-chain evaluator with custom role transitions, visit caps, auto run/skip policy, role snapshots in metadata, and role_completed after-code spawning. Wired approved plan flows to after: plan roles and role_completed(code) to after: code roles using existing follow-up artifacts and v1 metadata. Added underscore custom-role suffix support and a Python compatibility fallback when the linked Rust family-parent resolver binding is absent. Tests added/updated for loader validation, unknown prompt refs, auto policy, caps, after-plan and after-code runner integration, and %n(foo, improve_plan). Verification: just install; focused pytest for custom definitions/standard evaluator/dynamic attach; just check.

## Dependencies

- **Depends on:** [sase-5g.3](sase-5g.3.md) ✓
- **Depends on:** [sase-5g.4](sase-5g.4.md) ✓
- **Blocks:** [sase-5g.6](sase-5g.6.md) ✓
- **Blocks:** [sase-5g.8](sase-5g.8.md) ✓
- **Blocks:** [sase-5g.9](sase-5g.9.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-5g.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-5g.5/README.md) | [sase-5g.5](sase-5g.5.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`72fc527`](https://github.com/sase-org/sase/commit/72fc527b2286b8eea4e122cda332f13b24f97455) | feat: add file-backed custom agent-family roles (sase-5g.5) | [sase-5g.5](sase-5g.5.md) | 2026-07-06 11:18:16 |
