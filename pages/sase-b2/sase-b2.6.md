# Bead: sase-b2.6 — ACE \`@\` menu payload rows for beads and agents

[Bead Pages](../README.md) / [sase-b2](README.md) / sase-b2.6

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b2.6` · **Size:** medium
**Created:** 2026-07-30 01:33:38 UTC · **Closed:** 2026-07-30 02:39:52 UTC
**Plan:** [202607/bead\_and\_agent\_artifact\_refs.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_and_agent_artifact_refs.md)

## Description

py_ace: add bounded, off-thread bead and agent payload catalogs to the grouped `@` menu, with their own row badges, panel titles, and durable insertions.

## Notes

[2026-07-30T02:39:52Z · sase-b2.6] Implemented bounded off-thread bead and agent completion catalogs with issues.jsonl token caching, 500-row caps, durable global agent insertions, entity panel titles/badges, and known-kind highlighting. Verified focused completion/highlight/rendering tests (62 passed), targeted @-completion PNG snapshot (1 passed unchanged), mypy (2539 source files), ruff/Symvision/toobig, committed-plan validation, and full just test (24119 passed, 7 skipped). just check passed all stages through SASE validation, which stopped only on 8 pre-existing SDD plan/prompt link errors outside this phase.

[2026-07-30T02:40:58Z · sase-b2.6] Verified full suite: 24,119 passed and 7 skipped; focused ACE tests: 62 passed; targeted PNG snapshot unchanged; ruff, mypy, Symvision, and size checks passed. just check stopped only on 8 pre-existing out-of-scope SDD plan-link errors.

## Dependencies

- **Depends on:** [sase-b2.4](sase-b2.4.md) ✓
- **Blocks:** [sase-b2.7](sase-b2.7.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b2.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b2.6/README.md) | [sase-b2.6](sase-b2.6.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`3173dae`](https://github.com/sase-org/sase/commit/3173dae12003cace00cb98563e8c134398bd87fc) | feat(ace): add bead and agent completion catalogs | [sase-b2.6](sase-b2.6.md) | 2026-07-30 02:41:25 |
