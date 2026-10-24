# Bead: sase-1nf.14.1.4 — Skip unchanged row rendering and Option replacement

[Bead Pages](../README.md) / [sase-1nf.14.1](sase-1nf.14.1.md) / sase-1nf.14.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nf.14](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.14.md) · **Assignee:** `sase-1nf.14.1.4` · **Size:** medium
**Created:** 2026-10-24 13:37:44 EDT · **Closed:** 2026-10-24 14:26:57 EDT
**Plan:** [202610/measured\_tui\_gc\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/measured_tui_gc_fixes.md)

## Description

render-allocation: remove unconditional AgentList row invalidation when complete render inputs are unchanged, preserve visual updates, and measure Strip churn.

## Notes

[2026-10-24T18:26:57Z · sase-1nf.14.1.4] patch_row peeks the render cache at the patch boundary and skips invalidate/replace_option_prompt when the full render inputs are unchanged at the same painted width (skip iff cache hit, so output parity holds by construction); per-row bookkeeping still updated, changed inputs repaint via the existing path, width changes repaint, stale per-identity entries are invalidated on miss, and try_remove_rows prunes removed identities. Probe (100 repeated unchanged patches, real Textual harness): replaces/assembles/full-formats 100/100/100 -> 0/0/0, uncollectable-gc delta 0. New regression tests: zero-replacement skip with prompt identity and no uncollectable garbage; repaint on selection/status/tier-style/fleet/width change. Caller audit: panel paint-skip and fleet projection-skip already cover unchanged rosters, no caller change. just check: all lint gates green (ruff, mypy, symvision, keep-sorted, etc.); scoped lane 57339 passed with 1 unrelated zsh-completion PTY timeout under host load (load1~33), green in isolation on both base and patched trees. sase bead epic-symbols reports no leftovers.

## Dependencies

- **Blocks:** [sase-1nf.14.1.6](sase-1nf.14.1.6.md) ◐ · ⧖ 2026-10-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.14.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.14.1.4/README.md) | [sase-1nf.14.1.4](sase-1nf.14.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0d11a11`](https://github.com/sase-org/sase/commit/0d11a115dbfda1669ccccca0fe9ba5987807afd3) | feat(ace): skip unchanged AgentList row rendering and Option replacement | [sase-1nf.14.1.4](sase-1nf.14.1.4.md) | 2026-10-24 14:29:00 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nf.14.1.4][1] | full phase scope | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.14.1.4/README.md

<!-- sase:referenced-by:end -->
