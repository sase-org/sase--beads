# Bead: sase-4j.5 — End-To-End Launch Readiness Audit

[Bead Pages](../README.md) / [sase-4j](README.md) / sase-4j.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-4j.5`
**Created:** 2026-06-09 22:44:09 UTC · **Closed:** 2026-06-10 00:42:07 UTC
**Plan:** /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase\_11/sdd/plans/202606/p0\_onboarding.md

## Notes

COMMIT: f4bcb42e3

[2026-07-27T21:33:36Z · sase-a1.land] [2026-06-10T00:40:56Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Launch readiness audit closeout (2026-06-09):
- PyPI: latest is still 0.1.0 (stale). v0.1.4 release exists (release-please) and its build + install-smoke jobs passed, but the publish job of Release run 27245... (gh run 27244950800) failed: trusted-publishing token exchange rejected with invalid-publisher. PyPI project 'sase' has no trusted publisher matching repo:sase-org/sase, workflow release.yml, environment pypi. External account-level blocker: configure the trusted publisher on pypi.org, then 'gh run rerun 27244950800 --failed' to publish the already-built 0.1.4 dist.
- Clean-install smoke (isolated UV_TOOL_DIR): PyPI install delivers 0.1.0 with no 'sase version'/'sase doctor' and old 'run --help' (documents the blocker). Built 0.1.4 wheel from the run's dist artifact in a fresh venv: 'sase core health' OK, 'sase version' reports sase 0.1.4 + sase-core-rs 0.1.2, 'sase doctor -C llm.default -v' with no provider on PATH gives actionable ERROR with per-provider install hints and 'auth: not verified (doctor is read-only)' wording, 'sase run --help' shows [PROMPT] plus both beginner examples.
- Reader journey: README, docs home, blog index, series hub, launch essay, and quickstart all route to the one quickstart; mkdocs nav has Getting Started above The Basics; sase.sh serves docs home and the quickstart (HTTP 200, quickstart CTAs present). Provider-readiness wording consistent across doctor/README/quickstart; source install demoted to Development.
- Checks: just check, just docs-check, just docs-pdf-check all pass. No file edits made (no stale docs found).
- P0 criteria: all met except 'public install gets current command surface' which is blocked solely by the PyPI trusted-publisher config above. No P1/P2 follow-ups added per instructions.

## Dependencies

- **Depends on:** [sase-4j.4](sase-4j.4.md) ✓
