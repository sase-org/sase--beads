# Bead: sase-1t3.4 — One checkout root for trust enforcement and acknowledgment

[Bead Pages](../README.md) / [sase-1t3](README.md) / sase-1t3.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.62.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.62.linker.w0.md) · **Assignee:** `sase-1t3.4` · **Size:** medium
**Created:** 2026-11-16 07:57:55 EST
**Plan:** [202611/tui\_storm\_trust\_heap\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202611/tui_storm_trust_heap_recovery.md)

## Description

trust-root: make enforcement and `sase config trust` derive the same checkout root and identity for canonical `<repo>/sase/sase.yml` configs, so primaries and numbered workspaces match their project acknowledgment. Handles the legacy key per the trust_ack_compat decision.

## Notes

[2026-11-16T13:50:06Z · sase-1t3.4] Cutover: identity keys change from checkout:v1:<root>/sase to the real checkout (project:v1 for registered primaries/workspaces, checkout:v1:<repo> for unregistered). Bryan must re-run `sase config trust allow` once in the primary checkout on each host that had a legacy ack (athena; apollo/mac if they hold legacy keys). After that, every registered numbered workspace inherits it. No compatibility branch; old keys are ignored.

[2026-11-16T13:51:10Z · sase-1t3.4] Verified: owning_checkout_root_for_config returns <repo> for canonical sase/sase.yml (VCS/canonical tie-break; discover_project_root unchanged). Enforcement and sase config trust share identity, logical path, and digest for primary, numbered workspace, unregistered, symlink, and repo-named-sase. Collision fails closed. Cutover ignores checkout:v1:<root>/sase. Skip hint names sase config trust allow for the primary. No leftover --epic-symbol entries. Focused unit tests passed; just check is the remaining gate.

## Dependencies

- **Blocks:** [sase-1t3.14](sase-1t3.14.md) ◐ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.3](sase-1t3.3.md) ✓ · ⧖ 2026-11-16
- **Blocks:** [sase-1t3.7](sase-1t3.7.md) ◐ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.4.md) | [sase-1t3.4](sase-1t3.4.md) | 0 |
