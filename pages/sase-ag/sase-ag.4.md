# Bead: sase-ag.4 — Header writes at propose, commit, and post-commit

[Bead Pages](../README.md) / [sase-ag](README.md) / sase-ag.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ag.4` · **Size:** medium
**Created:** 2026-07-28 13:49:24 UTC · **Closed:** 2026-07-28 15:34:00 UTC
**Plan:** [202607/plan\_header\_provenance.md](https://github.com/sase-org/sase--plans/blob/main/202607/plan_header_provenance.md)

## Description

write-points: seed PROMPT and PARENT when a plan is proposed and committed, stop stamping the parent frontmatter property, and refresh the named plan's header best-effort after each primary commit.

## Notes

[2026-07-28T15:33:55Z · sase-ag.4] Implemented plan header writes across proposal, named-plan commit, commit hooks, and post-primary-commit refresh. Proposal/commit now seed PROMPT and PARENT header sections without parent frontmatter; post-commit refresh updates AGENTS and COMMITS under the plans-repo write lock, commits only changed bytes, and remains strictly best-effort. Added regression coverage, including fenced Markdown header examples in the linked Rust parser. Verification: SASE_PYTEST_WORKERS=8 just check passed; cargo fmt --all -- --check, cargo test -p sase_core artifact_link --lib (13 passed), and cargo test --workspace passed in linked sase-core; git diff --check passed in both repos.

## Dependencies

- **Depends on:** [sase-ag.1](sase-ag.1.md) ✓
- **Depends on:** [sase-ag.2](sase-ag.2.md) ✓
- **Depends on:** [sase-ag.3](sase-ag.3.md) ✓
- **Blocks:** [sase-ag.5](sase-ag.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ag.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ag.4/README.md) | [sase-ag.4](sase-ag.4.md) | 2 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@22fb5ba`](https://github.com/sase-org/sase-core/commit/22fb5bad2fb11d7e7f49abb4250e151d744ff20d) | fix(plan): ignore fenced header examples (sase-ag.4) | [sase-ag.4](sase-ag.4.md) | 2026-07-28 15:35:30 |
| [`9701511`](https://github.com/sase-org/sase/commit/97015111b388e663506d996a2d9c6a7511af0eda) | feat(sdd)!: write plan provenance headers (sase-ag.4) | [sase-ag.4](sase-ag.4.md) | 2026-07-28 15:36:40 |
