# Bead: sase-ad.1 — Resolve the committing run's own agent name

[Bead Pages](../README.md) / [sase-ad](README.md) / sase-ad.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ad.1` · **Size:** medium
**Created:** 2026-07-28 11:43:33 UTC · **Closed:** 2026-07-28 12:12:21 UTC
**Plan:** [202607/fix\_family\_agent\_publication.md](https://github.com/sase-org/sase--plans/blob/main/202607/fix_family_agent_publication.md)

## Description

identity: make commit-time agent attribution resolve the running member's name rather than the stale lane/family name held in the process environment, so footer links and publication requests both name a real run.

## Notes

[2026-07-28T12:11:56Z · sase-ad.1] Implemented commit-time agent resolution so the current run's agent_meta.json name takes precedence over a stale process-level SASE_AGENT_NAME, while preserving the environment fallback. Added family-member workflow coverage for the exact global label, families/...#member-code link, and ms--code publication request, plus non-family coverage. Verification: 56 targeted tests passed; just lint, just fmt-check, and git diff --check passed. just check was run twice: the product suite reached 22,895 passes, with only unrelated parallel-suite flakes (frontmatter panel and suite-capacity SIGKILL) that both passed in isolation. After an external workspace rebase refreshed the plans sidecar, standalone just validate reports 229 pre-existing prompt/plan-link errors outside this phase.

## Dependencies

- **Blocks:** [sase-ad.5](sase-ad.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ad.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ad.1/README.md) | [sase-ad.1](sase-ad.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`b201c92`](https://github.com/sase-org/sase/commit/b201c9200c8954b36c226dde675af52fd7b1b66d) | fix(commit): attribute family member runs correctly (sase-ad.1) | [sase-ad.1](sase-ad.1.md) | 2026-07-28 12:15:18 |
