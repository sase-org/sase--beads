# Bead: sase-1kk.4 — Python dismissed-bundle index becomes a thin adapter over Rust

[Bead Pages](../README.md) / [sase-1kk](README.md) / sase-1kk.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.104](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.104.md) · **Assignee:** `sase-1kk.4` · **Size:** medium
**Created:** 2026-10-13 12:24:29 EDT · **Closed:** 2026-10-13 16:24:51 EDT
**Plan:** [202610/tui\_sigbus\_single\_sqlite\_owner.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_sigbus_single_sqlite_owner.md)

## Description

py-archive-adapter: move the sase-core pin, replace all stdlib sqlite3 use in ace/dismissed_bundle_index with the new bindings while keeping public signatures and degrade semantics, and drop the stopgap dismissed-index lock.

## Notes

[2026-10-13T20:24:51Z · sase-1kk.4--1] Completed the Rust-backed dismissed-bundle adapter and removed the stopgap lock; sase tool run check passed (ToolRun 2ff4fe4cff8f7493facdfa6771d18886, verdict pass, exit 0), including scoped tests; epic-symbols check reported no leftovers.

## Dependencies

- **Depends on:** [sase-1kk.1](sase-1kk.1.md) ✓ · ⧖ 2026-10-13
- **Depends on:** [sase-1kk.2](sase-1kk.2.md) ✓ · ⧖ 2026-10-13
- **Blocks:** [sase-1kk.6](sase-1kk.6.md) ✓ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kk.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kk.4.md) | [sase-1kk.4](sase-1kk.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e8ec9cb`](https://github.com/sase-org/sase/commit/e8ec9cb29138643fb04f3fea9e947de883d9fc75) | refactor(ace): route dismissed bundle index through Rust | [sase-1kk.4](sase-1kk.4.md) | 2026-10-13 17:53:48 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1kk.4--1][1] | Verify the phase close was recorded | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kk.4.md

<!-- sase:referenced-by:end -->
