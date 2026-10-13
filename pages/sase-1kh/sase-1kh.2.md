# Bead: sase-1kh.2 — Make the commit finalizer see raw local commits

[Bead Pages](../README.md) / [sase-1kh](README.md) / sase-1kh.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.7c.f0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.7c.f0.md) · **Assignee:** `sase-1kh.2` · **Size:** medium
**Created:** 2026-10-13 08:22:37 EDT · **Closed:** 2026-10-13 09:41:27 EDT
**Plan:** [202610/protect\_linked\_repo\_work.md](https://github.com/sase-org/sase--plans/blob/main/202610/protect_linked_repo_work.md)

## Description

raw-commit-adopt: record baseline HEAD, detect unrecorded local-only commits, fail the commit finalizer instead of succeeding, and apply the raw_commit_policy branch.

## Notes

[2026-10-13T12:56:07Z · sase-1kh.2] PROPOSED FOLLOW-UP: 8 tests in tests/test_finalizers_live_e2e.py fail identically on the clean base tree in this workspace (bead-keep/close threading x2, protected-baseline push, refusal x2, upheld-deferral x2, deferral-repair) - live stitch lands success but leaves agent.py uncommitted; needs triage as environment/infra vs real regression

[2026-10-13T13:41:27Z · sase-1kh.2--1] raw-commit-adopt done: baseline HEAD + detector + absorb(backstop) with absorb policy. Verified: just _lint-symvision clean (privatized RawCommit->_RawCommit, unpublished_local_commits_message->_unpublished_local_commits_message), ruff+mypy clean, 16 raw-commit tests pass (incl. 2 new foreign-agent exemption tests), 13 discard-guard tests pass (incl. previously-failing already_clean_foreign_race_on_external_is_exempt, fixed by exempting foreign-trailered commits from detector), 25 baseline tests + declaration channel/reconciliation suites pass. 8 live-e2e base-tree failures remain as recorded PROPOSED FOLLOW-UP.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1kh.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1kh.2.md) | [sase-1kh.2](sase-1kh.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`86a343d`](https://github.com/sase-org/sase/commit/86a343de2860e17559cec2a0deb32208615b659b) | feat(finalizers): add raw-commit backstop with foreign-trailer exemption | [sase-1kh.2](sase-1kh.2.md) | 2026-10-13 09:44:51 EDT |
