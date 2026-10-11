# Bead: sase-1jx.5 — sase-github implements the onboarding hooks

[Bead Pages](../README.md) / [sase-1jx](README.md) / sase-1jx.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.49.linker.w1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.49.linker.w1.md) · **Assignee:** `sase-1jx.5` · **Size:** medium
**Created:** 2026-10-11 11:13:46 EDT · **Closed:** 2026-10-11 17:18:43 EDT
**Plan:** [202610/new\_project\_wizard.md](https://github.com/sase-org/sase--plans/blob/main/202610/new_project_wizard.md)

## Description

gh-provider: implement parse, local candidates, probe, describe creation and create for GitHub, encoding the verified `gh repo create` rules exactly; enrich `gh repo list` fields, report truncation, remedies and the signed-in account.

## Notes

[2026-10-11T21:18:43Z · sase-1jx.5] gh-provider done in sase-github: new workspace/onboarding.py (pure parse of owner/repo, gh:, https/scp/ssh forms with normalization; subprocess-free local discovery from ~/projects/github with origin-identity match and numbered_copy; bounded gh repo view probe with push-permission, sase.yml managed read, auth remedy; creation form per plan table with 24h cached gitignore/license/team lists, enterprise-gated internal, best-effort can_create; remote-only gh repo create with mandatory visibility, exists-via-reprobe, post-create verify/mismatches); completion enriched (id/viewerPermission/isEmpty, host, truncation, auth remedy) and namespaces carry hosts.yml account labeled you; floor raised to sase>=0.18.0 with README/architecture docs. Verified: 327 pytest passed (61 new), ruff check+format and mypy clean, live read-only smoke (probe/namespaces/list/describe incl. 162 gitignore and 13 licenses) good, no epic-symbol leftovers. Note: sase tool run check not used because a fresh sase-github venv cannot resolve sase>=0.18.0 from PyPI (name-squat 0.1.0) without the CI SASE_PYTHON_PATH override; equivalent lint+test ran in the workspace venv. Release ordering: ship sase 0.18.0 with the hookspec symbols before releasing this.

## Dependencies

- **Depends on:** [sase-1jx.1](sase-1jx.1.md) ✓ · ⧖ 2026-10-11
- **Depends on:** [sase-1jx.2](sase-1jx.2.md) ✓ · ⧖ 2026-10-11
- **Blocks:** [sase-1jx.7](sase-1jx.7.md) ◐ · ⧖ 2026-10-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.5/README.md) | [sase-1jx.5](sase-1jx.5.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jx.5][1] | Need full phase scope including notes | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.5/README.md

<!-- sase:referenced-by:end -->
