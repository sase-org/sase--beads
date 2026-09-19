# Bead: sase-11l.5.1 — The %hold prompt directive

[Bead Pages](../README.md) / [sase-11l.5](sase-11l.5.md) / sase-11l.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11l.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.5.md) · **Assignee:** `sase-11l.5.1.land`
**Created:** 2026-09-16 13:44:49 EDT · **Closed:** 2026-09-18 06:18:18 EDT
**Plan:** [202609/hold\_directive\_surface.md](https://github.com/sase-org/sase--plans/blob/main/202609/hold_directive_surface.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/hold_directive_surface.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/hold_directive_surface.md

<!-- sase:links:end -->

## Description

A prompt can arm a durable agent hold with `%hold`, behind the `agent_holds` beta flag. Python, the Rust typed launch planner, and the shared editor contract all parse it the same way. Agent and proc launches arm the hold when they are submitted, excluding their own kin and getting a priority boost. Approval previews list what each hold captures, broad holds need interactive confirmation, and `%hold` is rejected when combined with `%repeat` or `%dispatch`.
