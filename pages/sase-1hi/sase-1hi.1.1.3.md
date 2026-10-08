# Bead: sase-1hi.1.1.3 — Match human quotes with Unicode normalization and useful suggestions

[Bead Pages](../README.md) / [sase-1hi.1.1](sase-1hi.1.1.md) / sase-1hi.1.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1hi.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.1.md) · **Assignee:** `sase-1hi.1.1.3` · **Size:** small
**Created:** 2026-10-07 19:00:08 EDT · **Closed:** 2026-10-07 21:03:34 EDT
**Plan:** [202610/core\_plan\_decisions.md](https://github.com/sase-org/sase--plans/blob/main/202610/core_plan_decisions.md)

## Description

quotes: implement the normalized three-word contiguous matcher, deterministic closest-sentence suggestions, dependency integration, and the Python binding and tests.

## Notes

[2026-10-08T01:03:22Z · sase-1hi.1.1.3] PROPOSED FOLLOW-UP: editor directive contract tests fail on clean base — contract_covers_the_audited_directive_matrix and directive_contract_and_completion_bindings expect 6 directives but code lists 7 (extra for_epic); reproduced via git stash on sase-core c089cf17

[2026-10-08T01:03:34Z · sase-1hi.1.1.3] plan_decision_quote_match in sase-core plan/decisions/quote.rs with unicode-normalization 0.1 + unicode-casefold 0.2: NFKC/full non-Turkic casefold/straight quotes-dashes/collapsed ws, 3-word contiguous single-text match, stable overlap suggestions; binding registered with legacy string-array tolerance. Verified: 12 core quote tests + 57 decisions tests pass, 4 py binding tests pass, fmt-check/features/clippy pass via sase tool run check. Full suites: 4605 sase_core + 291 sase_core_py pass; 2 editor-directive failures reproduce identically on clean base, recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-1hi.1.1.2](sase-1hi.1.1.2.md) ✓ · ⧖ 2026-10-07
- **Blocks:** [sase-1hi.1.1.4](sase-1hi.1.1.4.md) ◐ · ⧖ 2026-10-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1hi.1.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1hi.1.1.3/README.md) | [sase-1hi.1.1.3](sase-1hi.1.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@df735e4`](https://github.com/sase-org/sase-core/commit/df735e4296b2211e4f39058dd3cd10905dbcdd11) | feat(sase-core): add plan decision human quote matcher with PyO3 binding | [sase-1hi.1.1.3](sase-1hi.1.1.3.md) | 2026-10-07 21:04:37 EDT |
