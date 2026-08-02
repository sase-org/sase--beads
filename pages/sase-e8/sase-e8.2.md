# Bead: sase-e8.2 — Local commit enumeration in the shared payload inventory

[Bead Pages](../README.md) / [sase-e8](README.md) / sase-e8.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ry](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ry/README.md) · **Assignee:** `sase-e8.2` · **Size:** medium
**Created:** 2026-08-02 14:04:21 UTC · **Closed:** 2026-08-02 14:41:10 UTC
**Plan:** [202608/commit\_ref\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/commit_ref_completion.md)

## Description

core_commits: enumerate each repository checkout's recent revisions with a bounded, timed `git log`, emit rows keyed by a 12-char-floored abbreviated SHA merged across repos in recency order, and drop the `commit` early-out that made the kind unenumerable.

## Notes

[2026-08-02T14:41:10Z · sase-e8.2] Implemented local commit payload enumeration with one-checkout-per-repo bounded git log scans (200 commits, 2s timeout, GIT_OPTIONAL_LOCKS=0), 12-character-floored SHAs, deterministic cross-repo recency merge/ranks, deduplication, 1000-row truncation disclosure, exact age/body/subject rows, and commit early-out removal. Verified focused real-git fixtures (7 tests), cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, cargo test --workspace, and git diff --check all pass.

[2026-08-02T14:47:37Z · sase-e8.2] Implemented local commit payload enumeration with one-checkout-per-repo bounded git log scans (200 commits, 2s timeout, GIT_OPTIONAL_LOCKS=0), 12-character-floored SHAs, deterministic cross-repo recency merge/ranks, deduplication, 1000-row truncation disclosure, exact age/body/subject rows, and commit early-out removal. Verified focused real-git fixtures (7 tests), cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, cargo test --workspace, and git diff --check all pass.

## Dependencies

- **Depends on:** [sase-e8.1](sase-e8.1.md) ✓
- **Blocks:** [sase-e8.3](sase-e8.3.md) ✓
- **Blocks:** [sase-e8.4](sase-e8.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-e8.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-e8.2/README.md) | [sase-e8.2](sase-e8.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase-core | [`sase-core@c66f0ff`](https://github.com/sase-org/sase-core/commit/c66f0ffda73e2f06a2ad0f4b4d5920da9d65a0a6) | feat(editor): enumerate local commit references | [sase-e8.2](sase-e8.2.md) | 2026-08-02 14:48:38 |
