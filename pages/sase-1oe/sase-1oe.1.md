# Bead: sase-1oe.1 — release.yml finds the previous release in a throwaway venv and fails loudly on real errors

[Bead Pages](../README.md) / [sase-1oe](README.md) / sase-1oe.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.14h](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.14h.md) · **Assignee:** `sase-1oe.1` · **Size:** medium
**Created:** 2026-10-26 08:35:12 EDT · **Closed:** 2026-10-26 09:40:15 EDT
**Plan:** [202610/unblock\_e2\_release\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202610/unblock_e2_release_cutover.md)

## Previously Closed

> ↺ Closed 2026-10-26T13:23:02Z · done
>
> (none)
>
> Reopened 2026-10-26T13:25:59Z by `sase bead open`

## Description

resolver: release.yml's previous-release resolver moves into tools/exercise_release, dry-runs each candidate in a throwaway uv venv instead of the externally managed --system interpreter, shows uv's stderr, and stops on errors that are not resolution failures. The SC2012 dist counts in the build step are replaced too.

## Notes

[2026-10-26T13:22:42Z · sase-1oe.1] LOCAL PROOF: exercise_release previous-version --candidate-version 0.18.2 ran against live PyPI with HOME relocated and UV_PYTHON_INSTALL_DIR pinned, selected 0.18.1, and wrote previous_version=0.18.1. A dry-run forced through uv --system --python /usr/bin/python3.13 reproduced uv’s externally managed refusal; resolver tests confirm interpreter, external-management, and network/index errors stop with ::error:: and are not skipped. Focused tests: 50 passed. actionlint .github/workflows/release.yml and git diff --check passed. sase tool run check b866ef7cd3ce609c6f45a7ca8cb18ea8 passed (exit 0; scoped tests 15m 41s). Full run-leg N-1 path not run: this checkout is version 0.18.1 and contains no candidate 0.18.2 dist artifact.

[2026-10-26T13:23:02Z · sase-1oe.1] Implemented the previous-version resolver in tools/exercise_release using a throwaway managed-Python venv, explicit failure classification, and GitHub output; replaced SC2012 dist counts. Live PyPI proof selected 0.18.1 for 0.18.2; focused tests (50), actionlint, diff check, and sase tool run check b866ef7cd3ce609c6f45a7ca8cb18ea8 passed. Epic-symbol audit was empty.

[2026-10-26T13:40:10Z · sase-1oe.1] LOCAL PROOF: previous-version live against PyPI for candidate 0.18.2 selected 0.18.1 with stdout exactly previous_version=0.18.1. Forced externally-managed failure (fake uv shim) exits 3 with ::error::UV_RESOLVE_FAILED naming externally-managed-environment. Focused tests: tests/test_exercise_release.py + tests/test_github_actions_release.py, 52 passed. actionlint clean, git diff --check clean, sase tool run check ec071904e2538c912805981ac962e6dc passed. Full run-leg N-1 path not run: this checkout is version 0.18.1 with no candidate 0.18.2 dist artifact.

[2026-10-26T13:40:15Z · sase-1oe.1] Resolver moved into tools/exercise_release previous-version (throwaway uv venv, no --system; resolution failures skip with stderr tail, all other failures stop with ::error::). release.yml prev step calls the subcommand and appends previous_version to GITHUB_OUTPUT; UV_PYTHON_INSTALL_DIR pinned pre-relocation so uv reuses the managed 3.12; SC2012 dist counts replaced with nullglob arrays. Verified: focused tests pass, actionlint clean, sase tool run check ec071904e2538c912805981ac962e6dc passed, live PyPI proof selected 0.18.1 for 0.18.2, epic-symbols empty.

## Dependencies

- **Blocks:** [sase-1oe.4](sase-1oe.4.md) ◐ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1oe.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1oe.1/README.md) | [sase-1oe.1](sase-1oe.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`72a1e3a`](https://github.com/sase-org/sase/commit/72a1e3a18eabfaca84c45a03feac447caaadb842) | feat(release): resolve previous release in a throwaway uv venv | [sase-1oe.1](sase-1oe.1.md) | 2026-10-26 09:41:46 EDT |
