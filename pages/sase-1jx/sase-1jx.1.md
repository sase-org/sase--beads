# Bead: sase-1jx.1 — sase-github traps the wizard would hit

[Bead Pages](../README.md) / [sase-1jx](README.md) / sase-1jx.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.49.linker.w1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.49.linker.w1.md) · **Assignee:** `sase-1jx.1` · **Size:** small
**Created:** 2026-10-11 11:13:44 EDT · **Closed:** 2026-10-11 11:38:34 EDT
**Plan:** [202610/new\_project\_wizard.md](https://github.com/sase-org/sase--plans/blob/main/202610/new_project_wizard.md)

## Description

gh-hygiene: in sase-github, bound `git clone` with a timeout, make `projects_base()` honor SASE_HOME, stop `ws_detect_workflow_type` from claiming non-GitHub hosts, and correct the stale `github_orgs` SSH/HTTPS docs.

## Notes

[2026-10-11T15:38:19Z · sase-1jx.1] PROPOSED FOLLOW-UP: sase-github suite shows 92 pre-existing failures where sase_core_rs is unbuilt (rust binding ImportError); identical on clean base tree, needs CI with built extension

[2026-10-11T15:38:34Z · sase-1jx.1] gh-hygiene done in sase-github: git clone now bound by clone_git_timeout (SASE_GITHUB_CLONE_TIMEOUT override, default max(600s, core network timeout)) with per-attempt cleanup and timeout failures in the same remediation error; projects_base uses sase.core.paths.sase_projects_dir so SASE_HOME is honored; ws_detect_workflow_type returns None for non-GitHub hosts; github_orgs SSH/HTTPS docs corrected in configuration.md, architecture.md, README.md and sase.schema.json. Verified: 8 new tests pass, ruff and mypy clean, full-suite failures byte-identical to clean base (92 pre-existing sase_core_rs env failures).

## Dependencies

- **Blocks:** [sase-1jx.5](sase-1jx.5.md) ✓ · ⧖ 2026-10-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.1/README.md) | [sase-1jx.1](sase-1jx.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fa897ce`](https://github.com/sase-org/sase/commit/fa897ced7232bd775f434e838b8b6d876da4826c) | docs(sase): correct github\_orgs description to owner completion plus PR gating, not clone transport | [sase-1jx.1](sase-1jx.1.md) | 2026-10-11 11:43:37 EDT |
| sase-github | [`sase-github@ad4827c`](https://github.com/sase-org/sase-github/commit/ad4827c5e97ece193a715cbd4d4933989e0e8d0b) | fix(sase-github): bound git clone with timeout, honor SASE\_HOME, narrow host detection, fix github\_orgs docs | [sase-1jx.1](sase-1jx.1.md) | 2026-10-11 11:48:38 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jx.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.1/README.md

<!-- sase:referenced-by:end -->
