# Bead: sase-17x.13.3 — Make every Keys-table key behave as specified

[Bead Pages](../README.md) / [sase-17x.13](sase-17x.13.md) / sase-17x.13.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17x.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17x.land.md) · **Assignee:** `sase-17x.13.3` · **Size:** medium
**Created:** 2026-09-24 20:28:43 EDT · **Closed:** 2026-09-24 21:53:22 EDT
**Plan:** [202609/command\_line\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_landing_fixes.md)

## Description

key-behavior: wire ↑/↓ prefix-filtered history. Offer ghost text only at the end of the line. Scope NORMAL mode and Block-nav key capture to their contexts. Add `ctrl+f` menu accept. Limit `R` to confirmation-declined blocks. Keep the draft on the palette `:` hop. Drive keys through the real input in the tests.

## Notes

[2026-09-25T01:53:08Z · sase-17x.13.3--2] PROPOSED FOLLOW-UP: Repair pre-existing extensionless mypy errors in tools/sase_core_wheel_cache (_identity_lock contextmanager return type and acquired_lock annotation) — reproduced by sase tool run check 7089526bb79fed72a7a5dcb8f35b9954 after all 4966 Python sources passed; tracked by sase-18f.4.

[2026-09-25T01:53:22Z · sase-17x.13.3--2] Verified the focused command-line key tests (panel shell, transcript blocks, palette modal, and palette wiring); sase tool run check reached an unrelated clean-base extensionless-mypy failure tracked by sase-18f.4.

## Dependencies

- **Depends on:** [sase-17x.13.2](sase-17x.13.2.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17x.13.4](sase-17x.13.4.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17x.13.5](sase-17x.13.5.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.13.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17x.13.3.md) | [sase-17x.13.3](sase-17x.13.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`543d012`](https://github.com/sase-org/sase/commit/543d012209875d59081f8c4d908168c6687ac4e9) | feat(command-line): complete key behavior contract | [sase-17x.13.3](sase-17x.13.3.md) | 2026-09-24 21:54:35 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17x.13.3--2][1] | Need the assigned phase scope, design references, and closeout status | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17x.13.3.md

<!-- sase:referenced-by:end -->
