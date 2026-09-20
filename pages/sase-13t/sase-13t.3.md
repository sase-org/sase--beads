# Bead: sase-13t.3 — Gate on file-set completeness and heal the partial 0.34.48 release

[Bead Pages](../README.md) / [sase-13t](README.md) / sase-13t.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.11](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.11.md) · **Assignee:** `sase-13t.3` · **Size:** medium
**Created:** 2026-09-20 08:29:31 EDT · **Closed:** 2026-09-20 13:45:49 EDT
**Plan:** [202609/pypi\_quota\_and\_release\_publishing.md](https://github.com/sase-org/sase--plans/blob/main/202609/pypi_quota_and_release_publishing.md)

## Description

heal: replace the version-existence publish gate with an expected-file-set check, top up the partial 0.34.48 release, and get the tagged backlog through 0.34.66 published complete.

## Notes

[2026-09-20T17:44:23Z · sase-13t.3] PROPOSED FOLLOW-UP: a yanked workspace version makes the completeness gate rebuild forever - the plan requires files to be non-yanked, but PyPI never accepts a re-upload of a yanked filename, so needs_publish stays true and every push/6-hourly run builds five artifacts whose publish is a skip-existing no-op; decide whether yanked should count as present (with a warning) or stay as specified, and document the 'bump the version' remedy (already in docs/pypi-retention.md).

[2026-09-20T17:45:49Z · sase-13t.3] Verified 2026-09-20. (1) Gate: publish-plan now calls .github/scripts/pypi_release_files.py status, which reads the single workflow-level EXPECTED_DIST_SUFFIXES list (5 entries: manylinux_2_28 x86_64/aarch64, universal2, win_amd64, .tar.gz) and prints absent|partial|complete; needs_publish = tag exists AND state != complete, so a version that exists with a missing/yanked file now heals. The publish job also runs 'pypi_release_files.py dist' so dist/ must match the list one-to-one (matrix/gate drift fails before upload); skip-existing preserved. 23 stdlib unit tests (incl. synthetic 0.34.48 partial response: missing win_amd64+sdist -> partial; complete; yanked; drift) pass via new 'scripts/check.sh script-test' (in 'all' and a ci.yml job); full 'just check' green. Against live PyPI with the workflow's real yaml-parsed set: 0.34.48 partial, 0.34.66/67/68/69 complete, 0.34.10 absent. (2) Heal: dispatched Release-plz run 35525574065 (dry_run=false build_wheels=true publish_pypi=true expected_version=0.34.48) - all jobs green, twine check PASSED x5, publish skipped the 3 existing wheels and uploaded win_amd64 + sdist; PyPI JSON now lists 5 files for 0.34.48, status=complete. (3) Backlog: workspace versions 0.34.66-0.34.69 published complete (5 files each) through the normal path. 0.34.49-0.34.65 were tagged but are intentionally NOT republished: the gate is scoped to the workspace version, they are superseded by 0.34.66+, sase floor is >=0.34.48, and ~1.3 GB of quota is not worth spending on them. Caveats: the gate/script/ci/doc changes are uncommitted in the sase-core working tree (host finalizer lands them), so the new gate has not yet run in CI on master - the 0.34.48 heal used the old workflow's manual path, which bypasses the gate; the dispatch also ran the release-plz merge job (open release PR #309 = v0.34.70), as any dispatch with dry_run=false does; PyPI JSON is briefly CDN-stale after upload (re-query before judging a heal). Docs: docs/pypi-retention.md 'Healing a partial release'. epic-symbols: none for this phase.

## Dependencies

- **Depends on:** [sase-13t.1](sase-13t.1.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-13t.4](sase-13t.4.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-13t.6](sase-13t.6.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-13t.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-13t.3/README.md) | [sase-13t.3](sase-13t.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@a4c4e65`](https://github.com/sase-org/sase-core/commit/a4c4e65c21159ba9e7195db91c7e32d92bf76d0a) | ci(release): gate PyPI publishing on file-set completeness, not version existence | [sase-13t.3](sase-13t.3.md) | 2026-09-20 13:47:36 EDT |
