# Bead: sase-1mk.6 — Fix the New Project create and configure Master Gate races

[Bead Pages](../README.md) / [sase-1mk](README.md) / sase-1mk.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.11b](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.11b.md) · **Assignee:** `sase-1mk.6` · **Size:** medium
**Created:** 2026-10-18 09:58:30 EDT · **Closed:** 2026-10-18 12:02:32 EDT
**Plan:** [202610/ship\_v0\_18\_0\_owned\_blockers.md](https://github.com/sase-org/sase--plans/blob/main/202610/ship_v0_18_0_owned_blockers.md)

## Description

new-project: make the create-collision, configure-review and late-form New Project tests (sase-1mi, sase-1m9) settle deterministically.

## Notes

[2026-10-18T16:02:15Z · sase-1mk.6--1] Phase evidence for sase-1mi and sase-1m9: all 20 targeted stress iterations passed under SASE_PYTEST_WORKERS=8 (8 tests per iteration; monitor 4635dtn421gx). The adjacent sase-1l8 bare-git create PNG snapshot passed its targeted just test-visual check (1 passed; 2 goldens unchanged). just fix passed. sase tool run check 3fac7767a5cc15e7831b634bb2b05a27 passed lint and validation, with only the separately noted known Zsh PTY flake in its scoped test lane.

[2026-10-18T16:02:21Z · sase-1mk.6--1] PROPOSED FOLLOW-UP: Existing READY flake task sase-13a tracks the exact tests/completion/test_zsh_smoke.py::test_alias_sbd_completes_static_bead_tree[sbd show --for-sbd show --format ] timeout. ToolRun 3fac7767a5cc15e7831b634bb2b05a27 saw it fail once under full scoped xdist load (1 failed, 56,424 passed, 17 skipped); the exact test passed on a serial rerun on the unchanged phase tree. Prior clean-base reproductions are recorded on sase-13a; no New Project fix is indicated.

[2026-10-18T16:02:32Z · sase-1mk.6--1] Verified: 20/20 targeted stress iterations passed under 8 workers; adjacent sase-1l8 PNG snapshot passed with 2 goldens unchanged; just fix passed; sase tool run check completed with no lint/validation failures and one known sase-13a Zsh PTY load flake that passed on isolated serial rerun. No epic-symbol entries remain.

## Dependencies

- **Blocks:** [sase-1mk.8](sase-1mk.8.md) ◐ · ⧖ 2026-10-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1mk.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1mk.6.md) | [sase-1mk.6](sase-1mk.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`dabd231`](https://github.com/sase-org/sase/commit/dabd231e82511d41a1a96b9b021d1e6c4322265c) | fix(ace): make New Project form races deterministic | [sase-1mk.6](sase-1mk.6.md) | 2026-10-18 12:03:48 EDT |
