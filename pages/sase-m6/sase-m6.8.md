# Bead: sase-m6.8 — The declarative ref.pane block

[Bead Pages](../README.md) / [sase-m6](README.md) / sase-m6.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.01u](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.01u.md) · **Assignee:** `sase-m6.8` · **Size:** large
**Created:** 2026-08-14 17:06:16 EDT · **Closed:** 2026-08-16 14:43:07 EDT
**Plan:** [202608/artifacts\_pane\_contract.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_pane_contract.md)

## Description

declare: add the Python-side ref.pane block and its presentation digest so a sidecar declares row template, sort, facets, grouping and empty state as data, and ship it in the research provider.

## Notes

[2026-08-16T18:43:07Z · sase-m6.8] Implemented declarative ref pane support and updated the research provider. Verified focused SASE pane/contract tests passed, research plugin just check passed, and repo just check reached only unrelated stale bead stats golden after lint gates; check-full monitor launch was blocked by existing monitor artifact issue.

## Dependencies

- **Blocks:** [sase-m6.10](sase-m6.10.md) ◐ · ⧖ 2026-08-14
- **Depends on:** [sase-m6.7](sase-m6.7.md) ✓ · ⧖ 2026-08-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m6.8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.8.md) | [sase-m6.8](sase-m6.8.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ae3c862`](https://github.com/sase-org/sase/commit/ae3c86249e73b24d3807842ac91cc22fb81f4683) | feat(artifacts): support declarative ref pane presentation | [sase-m6.8](sase-m6.8.md) | 2026-08-16 14:44:54 EDT |
| sase-research-artifacts | [`sase-research-artifacts@24daa87`](https://github.com/sase-org/sase-research-artifacts/commit/24daa876b135cce8969bbcfc309d15632f2fbaf6) | feat(provider): declare research artifact pane metadata | [sase-m6.8](sase-m6.8.md) | 2026-08-16 14:45:47 EDT |
