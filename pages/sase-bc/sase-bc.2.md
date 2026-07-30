# Bead: sase-bc.2 — file\_hooks config section, matcher, and list CLI

[Bead Pages](../README.md) / [sase-bc](README.md) / sase-bc.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-bc.2` · **Size:** medium
**Created:** 2026-07-30 17:33:06 UTC · **Closed:** 2026-07-30 18:01:49 UTC
**Plan:** [202607/commit\_file\_hooks.md](https://github.com/sase-org/sase--plans/blob/main/202607/commit_file_hooks.md)

## Description

hooks-config: add the `file_hooks` section to the sase config schema and default config, a fail-soft typed loader mirroring mentor_profiles, a wcmatch-based path matcher with negative-glob support, the `sase file-hook list` command, docs, and unit tests. No commit-flow integration yet.

## Notes

[2026-07-30T18:01:49Z · sase-bc.2] Implemented file_hooks schema/defaults, fail-soft provenance-aware typed loading with project-local auto-scoping, wcmatch matching (positive OR, negative veto, negative-only, path boundaries, globstar, dotfiles, project/sidecar/op filters), the human/JSON file-hook list CLI, docs, and tests. Verified 61 focused tests, dedicated reruns of three contention-sensitive suite cases, CLI smoke behavior, and a clean full just check.

[2026-07-30T18:03:11Z · sase-bc.2] Verified 61 focused tests, CLI smoke behavior, isolated contention-sensitive reruns, and a clean full just check with 24,434 tests passing.

## Dependencies

- **Blocks:** [sase-bc.3](sase-bc.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-bc.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-bc.2/README.md) | [sase-bc.2](sase-bc.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`57e41fd`](https://github.com/sase-org/sase/commit/57e41fd860155633e75aa73fc8eac831273bbf22) | feat(config): add file hook configuration and listing | [sase-bc.2](sase-bc.2.md) | 2026-07-30 18:03:44 |
