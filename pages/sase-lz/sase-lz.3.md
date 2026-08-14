# Bead: sase-lz.3 — Guided pool and fallback builder modal

[Bead Pages](../README.md) / [sase-lz](README.md) / sase-lz.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.014](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.014.md) · **Assignee:** `sase-lz.3` · **Size:** medium
**Created:** 2026-08-14 10:49:37 EDT · **Closed:** 2026-08-14 12:27:12 EDT
**Plan:** [202608/models\_panel\_pool\_authoring.md](https://github.com/sase-org/sase--plans/blob/main/202608/models_panel_pool_authoring.md)

## Description

selector-builder: add a SelectorBuilderModal that assembles selector members from the existing model picker and effort ladder with add, remove, reorder, per-member effort, and pool-versus-fallback toggling, gate member selection against nested selectors, and route a new picker entry row through it into the unchanged preview and write path.

## Notes

[2026-08-14T16:27:12Z · sase-lz.3] Implemented SelectorBuilderModal (add/remove/reorder/per-member effort/pool-vs-fallback toggle, nested-selector member gating) and wired a new picker entry row through it into the existing preview/write path. Verified via just check (fmt, ruff, mypy, pyscripts, keep-sorted, changelog, patch/stitch terminology, symvision, toobig, SASE validation, and the scoped test lane auto-escalated to the full test suite) — exit code 0. Also removed the now-stale 'sase-lz.3(compose_selector)' symvision epic-symbol whitelist entry from the Justfile since compose_selector now has a real consumer in models_panel_selector_builder.py.

## Dependencies

- **Depends on:** [sase-lz.2](sase-lz.2.md) ✓ · ⧖ 2026-08-14
- **Blocks:** [sase-lz.4](sase-lz.4.md) ✓ · ⧖ 2026-08-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-lz.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lz.3/README.md) | [sase-lz.3](sase-lz.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`877465a`](https://github.com/sase-org/sase/commit/877465a5ad4478e9fdc068c3668be928f72daf66) | feat(ace): add guided selector builder modal for model pools | [sase-lz.3](sase-lz.3.md) | 2026-08-14 12:27:54 EDT |
