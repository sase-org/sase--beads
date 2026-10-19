# Bead: sase-1n6.2 — release.yml builds once at the tag and seals the candidate manifest

[Bead Pages](../README.md) / [sase-1n6](README.md) / sase-1n6.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.11y](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.11y.md) · **Assignee:** `sase-1n6.2` · **Size:** medium
**Created:** 2026-10-19 16:40:08 EDT · **Closed:** 2026-10-19 17:34:16 EDT
**Plan:** [202610/e2\_release\_train\_steward.md](https://github.com/sase-org/sase--plans/blob/main/202610/e2_release_train_steward.md)

## Description

exact-build: a new tag-dispatched release.yml with an identity assertion, one build, a sealed candidate manifest stashed on the draft release, a rehearse mode, and the gate for the PyPI publisher and tag policy.

## Notes

[2026-10-19T21:33:40Z · sase-1n6.2] Release-please draft support (verify-only): release-please-action v5 (package.json 5.0.0, bundles release-please ^17.6.1; checkout is 17.11.2) honors draft:true with force-tag-creation:true. Evidence: src/manifest.ts extractReleaserConfig maps config draft -> draft and force-tag-creation -> forceTag (lines ~1406-1407); candidate releases carry both (lines ~1204-1205); createRelease passes {draft, prerelease, forceTag} through (lines ~1326-1335); src/github-api.ts createRelease (lines ~681-702) creates the tag ref at once via git.createRef (ignoring 422 if it exists) then repos.createRelease with draft:true. Next run finds the previous release via tag scan (latestReleaseVersion walks branch tags), and draft releases leave their tags in place. Conclusion: handover can set draft:true + force-tag-creation:true; no fallback needed.

[2026-10-19T21:33:56Z · sase-1n6.2] Live proof status: gh workflow run release.yml --ref master -f mode=rehearse 422s (Workflow does not have workflow_dispatch trigger) because release.yml exists only in this unlanded checkout, not on master. Expected per the tag-frozen-workflow rule; rehearse at master after landing. Local proof instead: sealed a manifest from real repo state (version 0.18.0, master SHA/tree), verify OK (candidate-3def2379...), evaluate exit 2 with qualification/exercise required-evidence-missing as specified. New tests: 22 passed (tests/test_release_candidate.py, tests/test_github_actions_release.py). Contract set: refreshed to 79 entries, cap re-curated 75->79 with measured 130.81s; manifest tests + bounded_drain (flake under load 41, passes in isolation and on base) green. lint_and_test gates in sase tool run check 07b9835b8dfab6b46be4b7d7306f250f: all lint gates green; scoped lane 56703 passed except 4 failures triaged as 2 pre-existing parser_stats goldens (fail identically on clean base) + budget (fixed by re-curation) + 1 load flake (green in isolation).

[2026-10-19T21:34:02Z · sase-1n6.2] PROPOSED FOLLOW-UP: tests/main/test_parser_stats.py goldens (test_project_help_golden, test_project_help_includes_definitions_and_examples) fail on the clean base tree: actual -f/--format rendering differs from the golden (-f, --format vs -f {json,markdown,rich}, --format {json,markdown,rich}), an argparse-version rendering drift unrelated to any epic work. Needs a golden refresh or formatter pin by whoever owns the stats CLI.

[2026-10-19T21:34:16Z · sase-1n6.2] exact-build done: release.yml (workflow_dispatch mode/core_version/rebuild; identity/build/stash owned; not-yet-qualified red gate), tools/release_candidate (seal/verify/observe/show/evaluate/download/core-files/core-suffixes), docs/contribute/release-train.md + nav, release-please draft+force-tag verified in source (action v5 / lib 17.11.2). Verified: 22 new tests pass; seal/verify/evaluate proven on real repo state (evaluate red with required-evidence-missing as specified); contract manifest re-curated to 79 with measured cost; sase tool run check 07b9835b8dfab6b46be4b7d7306f250f all lint gates green, 56703 scoped tests pass with only pre-existing parser_stats goldens (recorded as follow-up) outstanding. No epic-symbol leftovers.

[2026-10-19T21:34:52Z · sase-1n6.2] Human gate raised for the trusted-publisher + tag-policy steps: gate custom-1ab2c0b9-6768-4c64-8568-bc686a0e514c (notification d46dbdbe-b6e5-4fc5-8b17-f32a45ef0465). Check with sase gate show. Step 1: PyPI trusted publisher for sase (sase-org/sase, workflow release.yml, environment pypi). Step 2: v* tag rule on the pypi environment, keeping master until handover. Legacy publish.yml unaffected.

## Dependencies

- **Blocks:** [sase-1n6.4](sase-1n6.4.md) ◎ · ⧖ 2026-10-19
- **Blocks:** [sase-1n6.5](sase-1n6.5.md) ◐ · ⧖ 2026-10-19
- **Blocks:** [sase-1n6.7](sase-1n6.7.md) ◐ · ⧖ 2026-10-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n6.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.2/README.md) | [sase-1n6.2](sase-1n6.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`110214f`](https://github.com/sase-org/sase/commit/110214f51cbe8ea7deb3e08cfa2aa579f00958ac) | feat(release): build once at the tag and seal the candidate manifest | [sase-1n6.2](sase-1n6.2.md) | 2026-10-19 17:36:18 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1n6.1][1] | Check existing follow-ups for the exact parser-help and contract-manifest failures | 1 |
| read-by | [agent:sase-1n6.2][2] | Need phase scope, notes, remaining work | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.2/README.md

<!-- sase:referenced-by:end -->
