# Bead: sase-as.8 — Plan search and CLI over document-sidecar roles

[Bead Pages](../README.md) / [sase-as](README.md) / sase-as.8

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-as.8` · **Size:** medium
**Created:** 2026-07-29 14:31:26 UTC · **Closed:** 2026-07-29 15:24:21 UTC
**Plan:** [202607/artifact\_tranche\_zero\_and\_generic\_sidecar\_roles.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_tranche_zero_and_generic_sidecar_roles.md)

## Description

plan-search-roles: make the Python plan-search facade discover every configured document-sidecar root and pass them to the core as labeled corpora, and make `sase plan search --kind` and its result styling accept any discovered role rather than a fixed four-value choice list.

## Notes

[2026-07-29T15:24:21Z · sase-as.8] Implemented role-labeled document corpora in the Python facade, project-aware arbitrary --kind validation/help, deterministic arbitrary-role styling, and updated model docs/tests. Verified 87 focused facade/CLI/render/parser/integration tests pass; formatting, Ruff, mypy, pyscripts, Symvision, and size checks pass. Full just test: 23,618 passed, 7 skipped; only 3 unrelated ACE Axe-description PNG golden mismatches remained and reproduced serially. just check reached repository validation, which remains blocked by pre-existing stale generated provider skills and missing prompt backlinks in three July plan artifacts.

## Dependencies

- **Depends on:** [sase-as.5](sase-as.5.md) ✓
- **Depends on:** [sase-as.7](sase-as.7.md) ✓
- **Blocks:** [sase-as.9](sase-as.9.md) ✓
