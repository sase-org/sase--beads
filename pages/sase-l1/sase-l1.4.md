# Bead: sase-l1.4 — The --next action survives a failed claim transfer

[Bead Pages](../README.md) / [sase-l1](README.md) / sase-l1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zo](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zo.md) · **Assignee:** `sase-l1.4` · **Size:** medium
**Created:** 2026-08-13 13:38:29 EDT · **Closed:** 2026-08-13 14:52:43 EDT
**Plan:** [202608/monitor\_supervisor\_survival.md](https://github.com/sase-org/sase--plans/blob/main/202608/monitor_supervisor_survival.md)

## Description

followup: stop coupling the follow-up launch to a workspace-claim transfer that can no longer succeed, and give settlement an explicit degraded-launch outcome instead of dropping the follow-up.

## Notes

[2026-08-13T18:51:53Z · sase-l1.4] PROPOSED FOLLOW-UP: SDD hosted link plan refs fail to resolve — `parse_plan_reference("plans:202607/plan_header_provenance.md")` returns kind=`plan`, so `HostedLinkResolver.plan_url()` returns None before branch lookup; reproduced with `tests/sdd/test_hosted_links.py::test_plan_url_resolves_logical_reference_to_blob_url` outside the monitor follow-up scope.

[2026-08-13T18:52:43Z · sase-l1.4] Implemented monitor follow-up launch fallback and explicit settlement outcomes; verified with just install, focused ruff/pytest for monitor follow-up and supervisor tests, and just check passing.

[2026-08-13T18:54:16Z · sase-l1.4] Verified monitor follow-up fallback behavior with focused ruff/pytest and just check passing.

## Dependencies

- **Depends on:** [sase-l1.3](sase-l1.3.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-l1.5](sase-l1.5.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-l1.6](sase-l1.6.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-l1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-l1.4/README.md) | [sase-l1.4](sase-l1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`90b2628`](https://github.com/sase-org/sase/commit/90b26289f73a00fbecc7fba12233ca5bdf661682) | fix(monitor): preserve follow-up launches after claim transfer failure | [sase-l1.4](sase-l1.4.md) | 2026-08-13 14:55:33 EDT |
