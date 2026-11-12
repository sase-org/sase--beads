# Bead: sase-1se.1 — sase-core: managed-root precedence and exception-scoped never-restart markers

[Bead Pages](../README.md) / [sase-1se](README.md) / sase-1se.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bq](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bq.md) · **Assignee:** `sase-1se.1` · **Size:** medium
**Created:** 2026-11-12 06:15:58 EST · **Closed:** 2026-11-12 06:48:55 EST
**Plan:** [202611/auto\_restart\_update\_skew\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/auto_restart_update_skew_fixes.md)

## Description

core-origin-precedence: in sase-core, a traceback file under a managed root counts as managed origin even when the agent workspace contains that root (self-hosted editable installs), and never-restart markers are scanned over exception text instead of the raw log tail whenever exception evidence exists.

## Notes

[2026-11-12T11:48:55Z · sase-1se.1] core-origin-precedence done in sase-core 81ef2192: origin_is_workspace_only gives managed roots precedence (self-hosted overlap relaunches tier1 cannot_import_name), never_restart_reason scans exception text when exception evidence exists (052959 log-tail Permission denied no longer vetoes; log-only rows keep tail scan). 3 existing workspace-veto tests re-keyed to genuine workspace-only layouts; 5 new tests added. sase tool run check gate: succeeded exit=0.

## Dependencies

- **Blocks:** [sase-1se.4](sase-1se.4.md) ◐ · ⧖ 2026-11-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1se.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1se.1/README.md) | [sase-1se.1](sase-1se.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1se.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1se.1/README.md

<!-- sase:referenced-by:end -->
