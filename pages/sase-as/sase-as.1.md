# Bead: sase-as.1 — Copy mode on every Artifacts sub-tab

[Bead Pages](../README.md) / [sase-as](README.md) / sase-as.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-as.1` · **Size:** medium
**Created:** 2026-07-29 14:30:56 UTC · **Closed:** 2026-07-29 15:01:14 UTC
**Plan:** [202607/artifact\_tranche\_zero\_and\_generic\_sidecar\_roles.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_tranche_zero_and_generic_sidecar_roles.md)

## Description

copy-mode: admit `copy_tab_content` on non-PR Artifacts sub-tabs, dispatch the second copy key on the active sub-tab before falling through to the tab id, add per-sub-tab copy key blocks and real copy menus for Commits, Plans, Chats, and Bugs, and make the COPY footer and its restore path sub-tab aware.

## Notes

[2026-07-29T15:01:14Z · sase-as.1] Implemented per-sub-tab Artifacts copy mode, keymaps, dispatch, footer restore, help/docs, command-palette scoping, and regression coverage. Verified just install; 347 broad Artifacts/keymap tests passed; final focused suite 169 passed; Ruff, mypy, Symvision, and diff checks passed; updated Help PNG golden passes exactly. Full just check reached only unrelated repository validation drift (15 generated provider skills and three missing plan/prompt links). Full visual suite passed 363 with 1 skipped after the intended Help change; five unrelated pre-existing Axe goldens mismatch current Axe rendering.

[2026-07-29T15:02:17Z · sase-as.1] Verified 347 broad Artifacts/keymap tests and a final 169-test focused suite; Ruff, mypy, Symvision, diff checks, and the intended Help visual snapshot passed. Full just check reached unrelated generated-skill/plan-link validation drift, and five unrelated Axe visual mismatches were left unchanged.

## Dependencies

- **Blocks:** [sase-as.2](sase-as.2.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-as.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-as.1/README.md) | [sase-as.1](sase-as.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`7d41d17`](https://github.com/sase-org/sase/commit/7d41d17a02a44aea76dbe7f19d800bb24d0889c9) | feat(ace): add copy mode to artifact sub-tabs | [sase-as.1](sase-as.1.md) | 2026-07-29 15:03:16 |
