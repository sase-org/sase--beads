# Bead: sase-pt.2 — Exercise SASE\_RELEASE\_TOKEN and open the release PR

[Bead Pages](../README.md) / [sase-pt](README.md) / sase-pt.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.064](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.064.md) · **Assignee:** `sase-pt.2` · **Size:** small
**Created:** 2026-08-18 10:34:47 EDT
**Plan:** [202608/research\_artifacts\_first\_release.md](https://github.com/sase-org/sase--plans/blob/main/202608/research_artifacts_first_release.md)

## Description

release_pr: push one trigger commit to master so the release job runs under the new token, then confirm release-please opens the repo's first release PR instead of failing with the "GitHub Actions is not permitted to create or approve pull requests" error.

## Notes

[2026-08-18T15:01:05Z · sase-pt.2] TOKEN DIAGNOSIS: trigger commit a5a6b1b (docs: mention the optional wait argument on #research_swarm) is on origin/master. Publish run 32151591839 failed in 5s on the release job: `release-please failed: Bad credentials`. This is HTTP 401, not the previous `GitHub Actions is not permitted to create or approve pull requests` error, so the workflow did use secrets.SASE_RELEASE_TOKEN (repo secret present, updated 2026-08-18T14:25:10Z) rather than falling back to GITHUB_TOKEN. Secret name matches sase-github; publish.yml token expression is identical; sase-github published v0.2.5 today with the same arrangement. Org and repo workflow permissions still have can_approve_pull_request_reviews=false. Conclusion: the secret value is invalid (expired, revoked, truncated, or not a GitHub PAT). Cannot read it back. workflow_dispatch skips the release job, so another master push is required after the user replaces the secret. No PR opened. Staged RP branch still at 3b82a0d. Agreed first version remains v0.2.0 (option A). Asking the user to update SASE_RELEASE_TOKEN.

[2026-08-18T15:04:08Z · sase-pt.2] TOKEN STILL INVALID AFTER "UPDATE": pushed a second trigger commit (23367af, docs: state Python/sase version requirements in README). Publish run 32152110050 failed in 12s with the identical `release-please failed: Bad credentials` error. Checked `gh api repos/sase-org/sase-research-artifacts/actions/secrets/SASE_RELEASE_TOKEN`: created_at and updated_at are BOTH still 2026-08-18T14:25:10Z -- the exact same timestamp recorded in the prior diagnosis before the user said the token was updated. GitHub recorded no new secret write. Asking the user again rather than re-pushing, since another push against the same bad credential will only fail the same way.

[2026-08-18T15:11:03Z · sase-pt.2] TOKEN STILL 401 AFTER THIRD TRIGGER: honored both user answers (token updated; GitHub timestamp supposedly stale) and pushed trigger 7be097a (docs: mention just test-wheel in the agent build commands). Publish run 32152534076 failed in 11s with the identical `release-please failed: Bad credentials` error. GitHub still reports SASE_RELEASE_TOKEN created_at=updated_at=2026-08-18T14:25:10Z — unchanged through all three post-secret Publish runs (32151591839 / a5a6b1b, 32152110050 / 23367af, 32152534076 / 7be097a). No org secret, no pypi-env secret. Token is being injected (not empty GITHUB_TOKEN fallback): CI run 32152534558 also failed at checkout of public sase-org/sase with `could not read Username` because actions/checkout used the same invalid PAT. Pre-secret CI on 24daa87 was green. sase-github SASE_RELEASE_TOKEN is a different secret (updated 2026-06-08T17:32:20Z) and still publishes. Staged RP branch still at 3b82a0d. No PR opened. Will not push another trigger until updated_at actually changes or a different token source is specified.

[2026-08-18T15:16:09Z · sase-pt.2] HONORED DO-NOT-PUSH: Q3 answer was re-save the secret first. Re-checked gh api repos/sase-org/sase-research-artifacts/actions/secrets/SASE_RELEASE_TOKEN: created_at=updated_at=2026-08-18T14:25:10Z still (unchanged through runs 32151591839 / a5a6b1b, 32152110050 / 23367af, 32152534076 / 7be097a). No org secret, no pypi-env secret. No PR opened. Staged RP branch still 3b82a0d (v0.2.0). Polling GitHub for a new updated_at before any fourth trigger commit.

[2026-08-18T15:20:14Z · sase-pt.2--4] WAIT MONITOR FALSE-NEGATIVE: previous poller died in 2s because /bin/sh has no $SECONDS (Illegal number), then printed SECRET_UNCHANGED. Independent re-check of gh api repos/sase-org/sase-research-artifacts/actions/secrets/SASE_RELEASE_TOKEN still reports created_at=updated_at=2026-08-18T14:25:10Z. No fourth trigger. Asking user to confirm the repo Actions secret was actually re-saved (or name a different token source).

[2026-08-18T15:51:40Z · sase-pt.2] SECRET UPDATED: SASE_RELEASE_TOKEN updated_at is now 2026-08-18T15:36:13Z (was 2026-08-18T14:25:10Z through the three failed post-secret Publish runs). No org/pypi-env secret. No PR yet. Pushing a fourth trigger now that GitHub recorded a real secret write.

## Dependencies

- **Depends on:** [sase-pt.1](sase-pt.1.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pt.3](sase-pt.3.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pt.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pt.2/README.md) | [sase-pt.2](sase-pt.2.md) | 4 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-research-artifacts | [`sase-research-artifacts@a5a6b1b`](https://github.com/sase-org/sase-research-artifacts/commit/a5a6b1b65dbf0c67e8375cc9c15b2a8604122f4d) | docs: mention the optional wait argument on #research\_swarm | [sase-pt.2](sase-pt.2.md) | 2026-08-18 10:58:08 EDT |
| sase-research-artifacts | [`sase-research-artifacts@23367af`](https://github.com/sase-org/sase-research-artifacts/commit/23367aff1ac6ae588dc290d59886738771e4ad35) | docs: state the Python and sase version requirements in the README | [sase-pt.2](sase-pt.2.md) | 2026-08-18 11:03:10 EDT |
| sase-research-artifacts | [`sase-research-artifacts@7be097a`](https://github.com/sase-org/sase-research-artifacts/commit/7be097a70a2fda19868116404c7febec185175a2) | docs: mention just test-wheel in the agent build commands | [sase-pt.2](sase-pt.2.md) | 2026-08-18 11:07:20 EDT |
| sase-research-artifacts | [`sase-research-artifacts@46dc0d3`](https://github.com/sase-org/sase-research-artifacts/commit/46dc0d34cd119cba58e6a6bd07bae632196d609f) | docs: note that the sase 0.17 floor is not on PyPI yet | [sase-pt.2](sase-pt.2.md) | 2026-08-18 11:52:30 EDT |
