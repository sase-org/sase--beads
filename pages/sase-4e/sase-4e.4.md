# Bead: sase-4e.4 — Phase 4: Add Release Please And First Publish Path To sase-telegram

[Bead Pages](../README.md) / [sase-4e](README.md) / sase-4e.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-4e.4`
**Created:** 2026-06-08 16:31:37 UTC · **Closed:** 2026-06-08 17:24:56 UTC
**Plan:** [202606/automated\_semver\_releases.md](https://github.com/sase-org/sase--plans/blob/main/202606/automated_semver_releases.md)

## Notes

COMMIT: 54e6e65e1

[2026-07-27T21:32:24Z · sase-a1.land] [2026-06-08T17:24:16Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Completed Phase 4 for sase-telegram. Added CI, release-please-config.json, empty bootstrap .release-please-manifest.json with initial-version 0.1.0, and .github/workflows/release.yml with Release Please, uv build, artifact upload, fresh-wheel entry-point smoke, and Trusted Publishing. Release Please local dry-run with a synthetic fix(release) commit proposed chore(master): release 0.1.0, confirming the first public release path does not jump to 0.1.1. Verification: actionlint passed; JSON/YAML syntax passed; uv build produced sdist/wheel; local CI simulation passed on Python 3.12 with just lint plus just test and on Python 3.13 with just test, using workspace-matched sase and sase-core source with sase_core_rs built into the venv. Handoff: pypi.org currently returns 404 for sase-telegram and sase-core-rs; the release workflow intentionally keeps the fresh-wheel entry-point smoke as a publish guard, so the actual Telegram publish should wait until upstream sase/sase-core-rs publishing is ready and PyPI Trusted Publishing environment pypi is configured.

## Dependencies

- **Depends on:** [sase-4e.2](sase-4e.2.md) ✓
- **Blocks:** [sase-4e.6](sase-4e.6.md) ✓
