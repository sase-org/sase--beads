# Bead: sase-13t.4 — Pre-flight PyPI quota guard and headroom reporting

[Bead Pages](../README.md) / [sase-13t](README.md) / sase-13t.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.11](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.11.md) · **Assignee:** `sase-13t.4` · **Size:** small
**Created:** 2026-09-20 08:29:32 EDT · **Closed:** 2026-09-20 14:00:42 EDT
**Plan:** [202609/pypi\_quota\_and\_release\_publishing.md](https://github.com/sase-org/sase--plans/blob/main/202609/pypi_quota_and_release_publishing.md)

## Description

preflight: check remaining project storage before uploading, fail with an actionable message instead of a mid-upload 400, and surface headroom in the job summary.

## Notes

[2026-09-20T18:00:42Z · sase-13t.4] Added .github/scripts/pypi_quota.py (stdlib) + publish-job step 'Check PyPI storage headroom' before Publish to PyPI: fails pre-upload with used/incoming/limit/overflow and pointer to docs/pypi-retention.md; writes used/free/approx-remaining-releases to GITHUB_STEP_SUMMARY; PyPI API errors are warn-and-continue; already-uploaded files (skip-existing heal) not counted as incoming; limit is single PYPI_PROJECT_LIMIT_BYTES workflow env (test asserts it matches pypi_retention.py). 14 new unit tests; ./scripts/check.sh (fmt, clippy, cargo test, 37 script tests) green; smoke-ran against live PyPI (2.04 GiB used) for both fit and overflow paths. Workflow YAML parses. Not verified in a real GH Actions run (that is sase-13t.6).

## Dependencies

- **Depends on:** [sase-13t.3](sase-13t.3.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-13t.5](sase-13t.5.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-13t.6](sase-13t.6.md) ◐ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-13t.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-13t.4/README.md) | [sase-13t.4](sase-13t.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@9b3ade4`](https://github.com/sase-org/sase-core/commit/9b3ade44031ddd6a98d983065a89abc34930334e) | ci(release): fail the PyPI publish before upload when the project quota cannot fit it | [sase-13t.4](sase-13t.4.md) | 2026-09-20 14:02:02 EDT |
