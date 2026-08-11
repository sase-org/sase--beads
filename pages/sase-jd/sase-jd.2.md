# Bead: sase-jd.2 — Pull-request provider seam

[Bead Pages](../README.md) / [sase-jd](README.md) / sase-jd.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xp](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xp/README.md) · **Assignee:** `sase-jd.2` · **Size:** medium
**Created:** 2026-08-10 19:13:42 EDT · **Closed:** 2026-08-10 19:54:50 EDT
**Plan:** [202608/external\_artifact\_ingestion.md](https://github.com/sase-org/sase--plans/blob/main/202608/external_artifact_ingestion.md)

## Description

pr_seam: add PullRequestWire, vcs_list_pull_requests, and split list/read/mutate capability probes to the VCS provider boundary, implement them in sase-github over gh pr list, extend the in-memory fake, and add provider_id to IssueWire.

## Notes

[2026-08-10T23:54:50Z · sase-jd.2] Added PullRequestWire, vcs_list_pull_requests hookspec, and split supports_issue_listing/reads/mutations + supports_pull_requests capability probes to the VCS provider boundary (_types.py, _hookspec.py, _base.py, _plugin_manager.py, _registry.py, __init__.py); extended the in-memory fake in testing.py with PR support and configurable partial capability; added provider_id to IssueWire; implemented vcs_list_pull_requests in sase-github over gh pr list --state all (merged_at distinct from closed_at confirmed). Verified: sase-github's full test suite (195 tests) + ruff/mypy/format clean; sase-core's just check lint gates clean (fmt, ruff, mypy, pyscripts, test-waits, changelog, terminology) and the diff-scoped test lane (8958 passed, 5 skipped) clean. The one just-check lint failure (stale symvision --epic-symbol for closed bead sase-j3) is pre-existing staleness already fixed on origin/master, unrelated to this change.

## Dependencies

- **Blocks:** [sase-jd.5](sase-jd.5.md) ◐ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-jd.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jd.2/README.md) | [sase-jd.2](sase-jd.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`498ef31`](https://github.com/sase-org/sase/commit/498ef310f611443e2a583ae1528107e99b176a69) | feat(vcs-provider): add pull-request listing seam and split issue capability probes | [sase-jd.2](sase-jd.2.md) | 2026-08-10 19:55:43 EDT |
