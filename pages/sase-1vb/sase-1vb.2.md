# Bead: sase-1vb.2 — Make bench\_bead.py runnable as a script again

[Bead Pages](../README.md) / [sase-1vb](README.md) / sase-1vb.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ge](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ge.md) · **Assignee:** `sase-1vb.2` · **Size:** xsmall
**Created:** 2026-11-26 06:30:37 EST · **Closed:** 2026-11-26 06:47:44 EST
**Plan:** [202611/green\_github\_actions.md](https://github.com/sase-org/sase--plans/blob/main/202611/green_github_actions.md)

## Description

bench-bead-path: add the repo-root sys.path bootstrap to tests/perf/bench_bead.py and a static guard over every Justfile-invoked perf script.

## Notes

[2026-11-26T11:47:44Z · sase-1vb.2] Verified bead-perf-smoke, tests/perf/test_perf_script_guards.py, and sase tool run check

## Dependencies

- **Blocks:** [sase-1vb.6](sase-1vb.6.md) ◐ · ⧖ 2026-11-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vb.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vb.2/README.md) | [sase-1vb.2](sase-1vb.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a52d432`](https://github.com/sase-org/sase/commit/a52d4328e6878bdf243d0161a6b243a1aba1cbc6) | fix(perf): bootstrap sys.path in bench\_bead.py and add static guard | [sase-1vb.2](sase-1vb.2.md) | 2026-11-26 06:49:22 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1vb.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vb.2/README.md

<!-- sase:referenced-by:end -->
