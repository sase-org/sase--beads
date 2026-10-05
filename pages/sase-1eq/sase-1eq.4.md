# Bead: sase-1eq.4 — User syntax, CLI, config, discovery, and the sunset flag

[Bead Pages](../README.md) / [sase-1eq](README.md) / sase-1eq.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0v4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0v4.md) · **Assignee:** `sase-1eq.4` · **Size:** large
**Created:** 2026-10-02 06:51:25 EDT · **Closed:** 2026-10-03 13:11:57 EDT
**Plan:** [202610/xprompts\_to\_macros.md](https://github.com/sase-org/sase--plans/blob/main/202610/xprompts_to_macros.md)

## Description

sase-syntax: create the legacy_xprompt_syntax sunset flag. Switch every user-facing string contract outside the TUI to macro spellings with flag-gated aliases: CLI, config and frontmatter keys, directories, plugin groups, env vars, doctor ids, and skill sources.

## Notes

[2026-10-03T17:13:12Z · sase-1eq.4.1.land] Phase closed via sase-1eq.4.1 landing: child plan sase-1eq.4.1 closed; all five sections (compatibility, config-frontmatter, discovery, cli-doctor, strings-guard) verified; TUI behavior/path/layout adapters, canonical CLI normalization both flag states, stale expectations updated, LSP canonical-first fallback, 21 visual goldens refreshed and passing, focused suites green, live CLI checks pass, check run 2bf7ef819af8c377ea80bac84cc7543e joined to monitor

## Dependencies

- **Depends on:** [sase-1eq.3](sase-1eq.3.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1eq.5](sase-1eq.5.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1eq.6](sase-1eq.6.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1eq.7](sase-1eq.7.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1eq.8](sase-1eq.8.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1eq.9](sase-1eq.9.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.4.md) | [sase-1eq.4](sase-1eq.4.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.4.1.land--1][1] | check parent phase close status for macro cutover follow-up | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.4.1.land.md

<!-- sase:referenced-by:end -->
