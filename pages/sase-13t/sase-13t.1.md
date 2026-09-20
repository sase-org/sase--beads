# Bead: sase-13t.1 — Reclaim PyPI storage below the limit

[Bead Pages](../README.md) / [sase-13t](README.md) / sase-13t.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.11](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.11.md) · **Assignee:** `sase-13t.1` · **Size:** medium
**Created:** 2026-09-20 08:29:27 EDT · **Closed:** 2026-09-20 13:11:54 EDT
**Plan:** [202609/pypi\_quota\_and\_release\_publishing.md](https://github.com/sase-org/sase--plans/blob/main/202609/pypi_quota_and_release_publishing.md)

## Description

reclaim: confirm no consumer pins a doomed version, build the retention keep/delete list, and drive the human-gated pypi-cleanup deletion until the project is back under 10 GB.

## Notes

[2026-09-20T12:43:57Z · sase-13t.1] Pin audit 2026-09-20 (sase, sase-github, sase-telegram, sase-research-artifacts, sase-core; sase-nvim is not cloned so not grepped): sase floor >=0.34.48; sase-research-artifacts floor >=0.34.23 plus exact ==0.34.23 in its publish smoke test and ==0.33.0 only as a must-fail negative test; sase-telegram has only a stale transitive uv.lock entry (0.32.61) that no CI/Justfile reads (uses uv pip install). Nothing pins below 0.34.19, so keep-newest-30 (0.34.19..0.34.48) is safe. Live PyPI before deletion (after the maintainer hand-deleted 0.34.0-0.34.9): 262 releases / 1308 files / 10.06 GB, 0.68 GB free. Plan: keep 30 = 2.13 GB, delete 232 versions (0.1.2..0.34.18) = 7.93 GB, leaving 8.60 GB free (~118 releases at 72 MB avg; ~27 days at 4.32/day, ~118 days at 1/day). Tool: sase-core .github/scripts/pypi_retention.py (plan/regex/compare/verify) + docs/pypi-retention.md runbook. pypi-cleanup@0.1.10 --query-only selected exactly the generated 232-version list (compare OK).

[2026-09-20T12:45:17Z · sase-13t.1] PROPOSED FOLLOW-UP: preflight (sase-13t.4) must use 10 GiB = 10737418240 bytes as the project limit, not 10e9 - PyPI rejected the upload at ~10.73e9 summed file bytes, i.e. exactly 10 GiB; PROJECT_LIMIT_BYTES in sase-core .github/scripts/pypi_retention.py already encodes this.

[2026-09-20T12:46:12Z · sase-13t.1] PROPOSED FOLLOW-UP: sase-telegram uv.lock pins transitive sase-core-rs 0.32.61 (a version the keep-30 retention deletes); nothing reads the lock today, but refresh it (uv lock --upgrade-package sase-core-rs) before anything starts using uv sync --locked there.

[2026-09-20T13:02:05Z · 12] PyPI deletion gate (custom-fcaeb8b6) FAILED on its first accepted 'delete' attempt at 2026-09-20 08:53 EDT: pypi-cleanup 0.1.10 logged in and reached the first release page, then raised ValueError: No CSFR found in /manage/project/sase-core-rs/release/0.1.2/ — i.e. PyPI served an interstitial (new-device/re-auth) instead of the release management form. deleted 0 of 232 versions; nothing was removed. Re-ran the gate's credential-free dry_run action at 09:00 EDT: still 263 releases / 1313 files / 10.14 GB (94.4% of 10 GiB, 0.60 GB free), and pypi-cleanup --query-only still selects exactly the reviewed 232-version list (compare MATCH, subset-safe). The gate is still pending and answerable, so a retry is safe. Bead NOT closed: the phase goal (back under the limit) is unmet and sase-13t.3 stays blocked. Retry requires a fresh TOTP, so it must be re-answered from the gate form (notification 428e38e5), not via the bare --restart recovery command, which resubmits the delete option with no input and would fail on 'a PyPI username and password are required'.

[2026-09-20T13:44:44Z · sase-13t.1] Session 2026-09-20 09:45 EDT: gate custom-fcaeb8b6 still failed/answerable (no new attempt since the 08:53 CSRF failure); dry_run re-run: MATCH, 232 versions. Live PyPI now 264 releases / 1318 files / 10.22 GB = 95.2% of 10 GiB, 0.52 GB free (~7 releases), because 0.34.66 and 0.34.67 have since published complete (5 files each). Delete list still valid: keep set is now 0.34.19..0.34.48 + 0.34.66 + 0.34.67. Bead NOT closed: deletion needs a fresh TOTP that only the maintainer can enter via the gate form. pypi_retention.py and its runbook were never committed and were gone from the sase-core checkout; restored from the gate bundle's attachments (.github/scripts/pypi_retention.py + docs/pypi-retention.md) as uncommitted changes in sase-core.

[2026-09-20T15:37:34Z · sase-13t.1.f1] Root cause of the failed deletion found. pypi-cleanup 0.1.10 did not hit a CSRF bug: PyPI accepted the password and TOTP, then served its unrecognized-device login-confirmation wall instead of an authenticated session. The tool only checks that the post-login URL is not the login URL, so it walked on and died on the first release page ("No CSFR found in /manage/project/sase-core-rs/release/0.1.2/"). Upstream arcivanov/pypi-cleanup#42 and #49 both resolve by clicking the emailed login-verification link; open PR #48 exists to handle the redirect. Upgrading is NOT a fix: 0.1.10 is still newest stable and 0.1.11.dev20260320034404 is byte-identical in pypi_cleanup/__init__.py. Fix: sign in to pypi.org in a browser, clear the confirmation email, then delete with a fresh TOTP. Recorded in docs/pypi-retention.md (UNCOMMITTED in the sase-core checkout).

[2026-09-20T15:39:25Z · sase-13t.1.f1] PROPOSED FOLLOW-UP: a custom gate whose approved command fails can end up with no reachable entry in the TUI — bug. Gate custom-fcaeb8b6 declared a full shell block (PYPI-DELETE -> PYPI-DELETED, next.fork=family), but no gate-shell row was ever registered: `sase gate list --all` returns 103 rows and none is this gate, and .creation_result.json records continuation_mode="none" while request.json carries the shell block. On top of that both of its notifications are dismissed (428e38e5 the gate itself, 445f1135 the execution-failure), while the equivalent failure notification for the earlier gate custom-c1f4c258 (b7f367d5) is not dismissed. `sase notify apply-state` offers dismiss/mute/read/snooze/unmute but no undismiss, so a dismissed gate notification is unrecoverable. Net effect: the gate is still answerable (acceptance.disposition=accepted_failed, can_supersede=true) but invisible in both the gate list and the notification panel, and the only way back in is `sase gate answer` from the CLI or creating a replacement gate.

## Dependencies

- **Blocks:** [sase-13t.3](sase-13t.3.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-13t.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-13t.1/README.md) | [sase-13t.1](sase-13t.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@f68baeb`](https://github.com/sase-org/sase-core/commit/f68baebef4c3db01c2511c332e775e2d5cdeaace) | ci: add PyPI storage retention tool and runbook for sase-core-rs | [sase-13t.1](sase-13t.1.md) | 2026-09-20 09:48:38 EDT |
