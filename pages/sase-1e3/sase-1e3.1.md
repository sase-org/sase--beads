# Bead: sase-1e3.1 — Repo foundation, packaging, CI, and release automation

[Bead Pages](../README.md) / [sase-1e3](README.md) / sase-1e3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3z](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3z.md) · **Assignee:** `sase-1e3.1` · **Size:** medium
**Created:** 2026-10-01 14:42:39 EDT · **Closed:** 2026-10-01 15:02:58 EDT
**Plan:** [202610/sase\_listen.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_listen.md)

## Description

scaffold: build the sase-listen package skeleton. That covers every runtime dependency declared up front, the config loader, the CLI command registry with stubs, and the docs site skeleton. Add CI, PR-title, docs-deploy, and release-please plus PyPI publish workflows, then set the GitHub description, topics, homepage, Pages, and workflow permissions.

## Notes

[2026-10-01T19:01:14Z · sase-1e3.1] PROPOSED FOLLOW-UP: Org policy blocks GITHUB_TOKEN PR creation and can_approve_pull_request_reviews, so release-please cannot open the 0.1.0 PR; add a SASE_RELEASE_TOKEN repo secret with PR-write permission (per plan phase-7 note) and re-run the Publish workflow

[2026-10-01T19:02:06Z · sase-1e3.1] PROPOSED FOLLOW-UP: Coverage is at ~60% with fail_under=50 (scaffold floor); the pipeline phase must raise fail_under to 90 per the plan

[2026-10-01T19:02:58Z · sase-1e3.1] Scaffold landed (c35e6e2): packaging+lock, config/paths impl+tests, CLI registry with offline doctor/config, module+docs stubs, CI green, Docs green, wheel builds and twine-checks clean, sase tool run check green; GitHub description/topics/homepage/Pages/pypi-env set; release-please PR blocked by org policy (noted as follow-up)

## Dependencies

- **Blocks:** [sase-1e3.3](sase-1e3.3.md) ◐ · ⧖ 2026-10-01
- **Blocks:** [sase-1e3.4](sase-1e3.4.md) ◐ · ⧖ 2026-10-01
- **Blocks:** [sase-1e3.5](sase-1e3.5.md) ◐ · ⧖ 2026-10-01

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1e3.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1e3.1/README.md) | [sase-1e3.1](sase-1e3.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.38.cld][1] | Check phase progress/notes for sase-listen user-facing research | 1 |
| read-by | [agent:research.38.grk][2] | Need child phase scope for sase-listen user-facing research | 1 |
| read-by | [agent:research.38.mus][3] | research sase-listen scope | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.38.cld/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.38.grk/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.38.mus/README.md

<!-- sase:referenced-by:end -->
