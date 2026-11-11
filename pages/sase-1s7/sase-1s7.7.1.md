# Bead: sase-1s7.7.1 — The steward, the release branch's generated docs, and the publish jobs no longer block the release

[Bead Pages](../README.md) / [sase-1s7.7](sase-1s7.7.md) / sase-1s7.7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1s7.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1s7.land.md) · **Assignee:** `sase-1s7.7.1` · **Size:** medium
**Created:** 2026-11-11 03:22:29 EST · **Closed:** 2026-11-11 03:43:18 EST
**Plan:** [202611/release\_0\_19\_0\_unblock.md](https://github.com/sase-org/sase--plans/blob/main/202611/release_0_19_0_unblock.md)

## Description

train-fixes: stop pin_changed comparing exact core pins, regenerate release_announce.html in publish.yml's sync-release-metadata job, and give release.yml's publish and confirm jobs a setup-uv step, with tests and docs.

## Notes

[2026-11-11T08:43:18Z · sase-1s7.7.1] train-fixes done. (1) tools/_release_watch_facts.py: pin_changed is now source_pin != master_pin only; dropped the exact_pin != master_core_pin clause and the master_core_pin read; exact_public_core_pin retained for the Rust policy. (2) .github/workflows/publish.yml sync-release-metadata now runs python tools/render_applicability after uv lock and includes docs/overrides/generated/release_announce.html in the diff check and git add. Confirmed on a scratch checkout of origin/release-please--branches--master (manifest 0.19.0, partial stale at v0.18.1) that render_applicability is the only version-bump-stale renderer; other check diffs there were bare-worktree prettier artifacts. (3) .github/workflows/release.yml publish and confirm gained astral-sh/setup-uv@v4 with cache options after checkout. Audit: every other uv-invoking job (build, exercise-legs, confirm-install) already had setup-uv; stash/exercise/qualify jobs use only preinstalled python3/gh/curl. Tests: new FakePrGithub contract cases in tests/_release_watch_facts_contract_cases.py (exact-pin drift -> pin_changed False/stale_head False; source-pin drift -> True; ahead/diverged -> stale_head True) collected by new tests/test_release_watch_pr_context.py, which also proves a drifted-exact-pin snapshot (0.44.2 == core-ensure pick, pin_changed False) reaches releasable with merge proposed-not-executed and no metadata refresh (fails pre-fix: pin_changed True -> waiting/metadata-refresh; old release.yml fails new audit in exactly publish+confirm). Extended tests/test_github_actions_publish.py, added test_release_every_uv_job_installs_uv_first to tests/test_github_actions_release.py, and test_stale_partial_fails_check_until_rerendered to tests/test_render_applicability.py. Docs: two sentences in docs/contribute/release-train.md. just fix clean; sase tool run check 49aa7c2fddd733a0c28391bcd7b6e0ae succeeded; just toobig clean. epic-symbols empty.

## Dependencies

- **Blocks:** [sase-1s7.7.2](sase-1s7.7.2.md) ◐ · ⧖ 2026-11-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1s7.7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1s7.7.1/README.md) | [sase-1s7.7.1](sase-1s7.7.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`474b11f`](https://github.com/sase-org/sase/commit/474b11f90de686290cecdef95644fbea247c736d) | fix(release-train): steward pin check, release-branch docs, and train uv setup | [sase-1s7.7.1](sase-1s7.7.1.md) | 2026-11-11 03:44:47 EST |
