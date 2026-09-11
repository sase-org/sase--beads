# Bead: sase-zf.1 — Shared agents-live query profile and row adapter

[Bead Pages](../README.md) / [sase-zf](README.md) / sase-zf.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0iy](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0iy.md) · **Assignee:** `sase-zf.1` · **Size:** medium
**Created:** 2026-09-10 18:01:46 EDT · **Closed:** 2026-09-10 18:54:31 EDT
**Plan:** [202609/agents\_query\_unification.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_query_unification.md)

## Description

shared-profile: factor shared agent query field specs out of the Artifacts agents schema, add the agents-live boolean profile and the live-row query adapter, and pin Python/Rust conformance goldens for the new dialect.

## Notes

[2026-09-10T22:53:28Z · sase-zf.1] PROPOSED FOLLOW-UP: investigate ambient verification failures - just check is blocked before tests by feature-flag rule 8 (sase-z0 missing link_events definition); forced just test-scoped escalated to the full suite and ended with unrelated fleet/completion/sidecar/audit failures.

[2026-09-10T22:54:31Z · sase-zf.1] Verified: agents-live targeted Python/query suites passed (54 tests); sase-core just check passed with uv Python LD_LIBRARY_PATH set; git diff --check clean in both repos; epic-symbols clean. Main just check passed fmt/Ruff/mypy then failed unrelated feature-flag rule 8 for sase-z0 link_events.

## Dependencies

- **Blocks:** [sase-zf.2](sase-zf.2.md) ✓ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zf.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zf.1/README.md) | [sase-zf.1](sase-zf.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bfcdc04`](https://github.com/sase-org/sase/commit/bfcdc0416288ba8d9175177ecbdadaf6a3e64c9e) | feat(query): add agents-live profile adapter | [sase-zf.1](sase-zf.1.md) | 2026-09-10 18:56:37 EDT |
| sase-core | [`sase-core@7d6dfcf`](https://github.com/sase-org/sase-core/commit/7d6dfcfa96ec50003df79fc0942726a51bc1db52) | fix(query): quote canonical property values | [sase-zf.1](sase-zf.1.md) | 2026-09-10 18:59:47 EDT |
