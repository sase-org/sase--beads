# Bead: sase-1ig.3 — Context-aware reinstall remedies in runtime code

[Bead Pages](../README.md) / [sase-1ig](README.md) / sase-1ig.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ym](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ym.md) · **Assignee:** `sase-1ig.3` · **Size:** small
**Created:** 2026-10-08 18:23:29 EDT · **Closed:** 2026-10-08 20:41:25 EDT
**Plan:** [202610/just\_install\_pypi\_dev\_venv.md](https://github.com/sase-org/sase--plans/blob/main/202610/just_install_pypi_dev_venv.md)

## Description

remedies: add one install-context helper that picks `sase update`, `just install-dev`, or `just install-venv` and route every src/ reinstall hint (core/rust.py, query facades, doctor, completion finalizer) through it; doctor's import-root-drift warning stops suggesting a global reinstall.

## Notes

[2026-10-09T00:41:13Z · sase-1ig.3--1] PROPOSED FOLLOW-UP: just check symvision stage fails identically on clean base (41 unused-symbol rows, none in remedies files; output byte-identical with and without this phase); full just check also exceeds 1h largely in _setup waiting on shared sase-core wheel build lock

[2026-10-09T00:41:25Z · sase-1ig.3--1] install_remedy helper added and all src reinstall hints routed through it; verified: 35 targeted pytest pass, ruff check+format clean on 10 touched files, mypy clean on 7 src files, live remedy resolves to just install-venv in checkout venv; just-check symvision failure byte-identical on clean base so pre-existing (recorded as follow-up); no epic-symbols for this bead

## Dependencies

- **Depends on:** [sase-1ig.1](sase-1ig.1.md) ✓ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ig.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ig.3.md) | [sase-1ig.3](sase-1ig.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fa0de34`](https://github.com/sase-org/sase/commit/fa0de348ee9930ce9b90c50cb967ee1c044210e8) | feat(remedies): context-aware reinstall remedies in runtime code (sase-1ig.3) | [sase-1ig.3](sase-1ig.3.md) | 2026-10-08 20:43:28 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ig.3--1][1] | check epic symbols and remaining scope | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ig.3.md

<!-- sase:referenced-by:end -->
