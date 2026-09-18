# Bead: sase-12z.3 — Make every generated screenshot change reviewable

[Bead Pages](../README.md) / [sase-12z](README.md) / sase-12z.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0mx](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0mx.md) · **Assignee:** `sase-12z.3` · **Size:** medium
**Created:** 2026-09-18 10:39:53 EDT · **Closed:** 2026-09-18 13:57:16 EDT
**Plan:** [202609/fix\_tui\_screenshots.md](https://github.com/sase-org/sase--plans/blob/main/202609/fix_tui_screenshots.md)

## Description

change-reports: extend the existing visual report pipeline to consume the run manifest and report created, updated, and stale screenshots, preserving before images, grouped diffs, contact sheets, JSON, CI annotations, and durable per-run output on successful updates as well as failures.

## Notes

[2026-09-18T17:57:16Z · sase-12z.3] Implemented manifest-backed visual screenshot reports, per-run report publication before apply, latest-report pointer, update grouping/contact sheets, created/updated/stale artifacts, and failure/refusal report records. Verified: focused pytest for render/fix/apply report paths passed (56 passed), just fix passed, just check passed, and sase bead epic-symbols sase-12z.3 reported no --epic-symbol entries.

## Dependencies

- **Depends on:** [sase-12z.2](sase-12z.2.md) ✓ · ⧖ 2026-09-18
- **Blocks:** [sase-12z.4](sase-12z.4.md) ✓ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-12z.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-12z.3/README.md) | [sase-12z.3](sase-12z.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3fc37d5`](https://github.com/sase-org/sase/commit/3fc37d5ffb24043ec95a1f7015f7baef1de819af) | feat(visual): report screenshot maintenance manifests | [sase-12z.3](sase-12z.3.md) | 2026-09-18 13:59:13 EDT |
