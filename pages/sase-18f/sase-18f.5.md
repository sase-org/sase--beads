# Bead: sase-18f.5 — Ignore cache-only script directories in the pyscripts lint

[Bead Pages](../README.md) / [sase-18f](README.md) / sase-18f.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0rh.md) · **Assignee:** `sase-18f.5` · **Size:** xsmall
**Created:** 2026-09-24 17:18:58 EDT · **Closed:** 2026-09-24 18:02:04 EDT
**Plan:** [202609/green\_just\_check.md](https://github.com/sase-org/sase--plans/blob/main/202609/green_just_check.md)

## Description

pyscripts-stale-dirs: make tools/pyscripts-260801 ignore scripts/ and tools/ directories with no collectable files, such as a `__pycache__`-only leftover from a rename, so reused workspaces stop failing Rule 2. Add a regression test.

## Notes

[2026-09-24T22:02:04Z · sase-18f.5] Verified tools/pyscripts-260801 ignores cache-only directories and passes with stale tests/ace/tui/tools/__pycache__ present. Added regression test in tests/test_pyscripts_tool.py.

## Dependencies

- **Blocks:** [sase-18f.9](sase-18f.9.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18f.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.5/README.md) | [sase-18f.5](sase-18f.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4b3699f`](https://github.com/sase-org/sase/commit/4b3699f0dc3242c723f498c654f643cec5f337d0) | fix: ignore cache-only script directories in pyscripts lint | [sase-18f.5](sase-18f.5.md) | 2026-09-24 18:03:38 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-18f.5][1] | Verify bead was closed | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.5/README.md

<!-- sase:referenced-by:end -->
