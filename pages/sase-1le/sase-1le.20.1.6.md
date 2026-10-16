# Bead: sase-1le.20.1.6 — Finish ace.md and move pager.md into reference/tui/

[Bead Pages](../README.md) / [sase-1le.20.1](sase-1le.20.1.md) / sase-1le.20.1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1le.20](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.md) · **Assignee:** `sase-1le.20.1.6` · **Size:** medium
**Created:** 2026-10-16 08:04:36 EDT · **Closed:** 2026-10-16 15:56:29 EDT
**Plan:** [202610/docs\_decompose.md](https://github.com/sase-org/sase--plans/blob/main/202610/docs_decompose.md)

## Description

tui-move: move the remaining tab, pane, and global-control sections of ace.md, move visual-grammar remnants to contribute/, move pager.md, add the reference/tui/ hub, and finish ace.md as an anchor stub.

## Notes

[2026-10-16T19:56:15Z · sase-1le.20.1.6] PROPOSED FOLLOW-UP: sase tool run check fails at init memory --check (7 chezmoi home shims: sase.md, README.md, AGENTS/CLAUDE/GEMINI/QWEN/OPENCODE.md.tmpl +9/−11) — no sase/memory files in this tree; same class as closed sase-n0/sase-i7; lint/docs-contract passed, docs-check passed after pinning five H2 ids, test-scoped 850 passed

[2026-10-16T19:56:29Z · sase-1le.20.1.6] tui-move: split remaining ace.md tab/pane/global-control sections plus visual-grammar remnants into reference/tui/* and contribute/tui-rendering.md; moved pager.md to reference/tui/pager.md; ace.md is the generated stub; TUI hub is 396 words; frozen /ace/ /ace/#prompt-history-modal /pager/ URL contract still holds; Related on dest pages; tribe-terminology and wait-dependency tests retargeted. Verified: just fix; lint/docs-contract/symvision green; just docs-check (mkdocs --strict + 2775 URL contract) after pinning {#query-system-1,projects-tab-1,notifications-modal-1,procs-tab-1,updates-tab-1}; just test-scoped 850 passed. sase tool run check stopped at UNKNOWN init memory --check (7 chezmoi home shims, no memory files dirty here; PROPOSED FOLLOW-UP cites sase-n0/sase-i7). epic-symbols empty.

## Dependencies

- **Blocks:** [sase-1le.20.1.15](sase-1le.20.1.15.md) ✓ · ⧖ 2026-10-16
- **Blocks:** [sase-1le.20.1.16](sase-1le.20.1.16.md) ✓ · ⧖ 2026-10-16
- **Depends on:** [sase-1le.20.1.5](sase-1le.20.1.5.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.20.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.6/README.md) | [sase-1le.20.1.6](sase-1le.20.1.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7e3af4c`](https://github.com/sase-org/sase/commit/7e3af4c8ad1ec61c72ffdab811ed38501c7cd1ed) | docs(tui): split remaining ace.md tabs into the TUI hub | [sase-1le.20.1.6](sase-1le.20.1.6.md) | 2026-10-16 15:58:07 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1le.20.1.6][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.6/README.md

<!-- sase:referenced-by:end -->
