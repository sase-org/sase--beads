# Bead: sase-am.1 — Restore completed-run signal and unbreak lint

[Bead Pages](../README.md) / [sase-am](README.md) / sase-am.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-am.1` · **Size:** small
**Created:** 2026-07-28 22:05:51 UTC · **Closed:** 2026-07-28 22:16:45 UTC
**Plan:** [202607/ci\_flakiness\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202607/ci_flakiness_redesign.md)

## Description

ci-signal-restore: stop cancelling in-flight master runs, skip CI on the release-please branch, disable matrix fail-fast, add the missing beads sidecar to the lint environment, pin keep-sorted, and file beads for the two observed flaky tests.

## Notes

[2026-07-28T22:16:45Z · sase-am.1] Phase 1 (ci-signal-restore) landed in .github/workflows/ci.yml: concurrency now uses cancel-in-progress: ${{ github.ref != 'refs/heads/master' }} so master runs reach a terminal conclusion while PR refs keep latest-wins; all 12 jobs carry the release-please--branches--master skip condition; test matrix gets fail-fast: false; lint checks out the sase-org/sase--beads sidecar at sase/repos/beads (repo name confirmed via gh repo view) and the sdd-store heredoc gained the matching beads entry; keep-sorted pinned to v0.8.0 with the Go-bin cache key changed from hashFiles(ci.yml) to go-bin-keep-sorted-v0.8.0-linux-amd64. Verified: root-caused the lint failure in run 30333749829 -- 'init repo --check failed' with '+ create sase/repos/beads', and the agents sidecar only emits an informational 'skipped agents sidecar planning' line, so no agents checkout was added; the checked-out beads sidecar already contains README.md and assets/beads-directory-map.png. ci.yml parses under yaml.safe_load with all 12 jobs carrying the if: and fail-fast false on test. just install + just test green (23282 passed, 7 skipped); just lint green. Two pre-existing, unrelated failures remain in just validate (init skills --check chezmoi drift, plan links validate errors on 202607/prompts/ci_flakiness_redesign.md and fix_ci_core_clippy_and_minimum.md) -- confirmed identical with the change stashed. Plan step 6 (file beads for the two flaky tests) was NOT done: the launching instructions explicitly forbade creating new beads.

## Dependencies

- **Blocks:** [sase-am.2](sase-am.2.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-am.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-am.1/README.md) | [sase-am.1](sase-am.1.md) | 0 |
