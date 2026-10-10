# Bead: sase-1jm.2.1.4 — agents-archive profile and the in token

[Bead Pages](../README.md) / [sase-1jm.2.1](sase-1jm.2.1.md) / sase-1jm.2.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.2.md) · **Assignee:** `sase-1jm.2.1.4` · **Size:** medium
**Created:** 2026-10-10 07:31:49 EDT · **Closed:** 2026-10-10 08:54:51 EDT
**Plan:** [202610/archive\_corpus.md](https://github.com/sase-org/sase--plans/blob/main/202610/archive_corpus.md)

## Description

profile-token: add the agents-archive query profile and the host-owned in: token, without switching views.

## Notes

[2026-10-10T12:54:40Z · sase-1jm.2.1.4] PROPOSED FOLLOW-UP: check_feature_flags rule 7 — closed flag bead sase-zg still has a surviving agents_unified_query definition; first check of this phase passed this stage

[2026-10-10T12:54:45Z · sase-1jm.2.1.4] PROPOSED FOLLOW-UP: test_agent_run_stops_on_generic_output asserts helper_error vs unknown_item — possible owner sase-1gi

[2026-10-10T12:54:51Z · sase-1jm.2.1.4] Added agents-archive profile (pane_id agents-archive) and host-owned in:{inbox,archive} extraction on the Agents tab and sase agent search. in:archive is valid and does not change inbox rows; mixed queries keep live-compatible remainder; archive-only fields without in:archive and inbox-only fields with in:archive raise the scoped hints. Catalog/Artifacts Agent still reject in: as unknown. Completions live on AgentsFilterBar only. Verified with tests/ace/test_scope_token.py, agents profile/conformance goldens, CLI search, live-query filter, filter-bar injection, and pushdown strip. sase tool run check: our lint (ruff/mypy/symvision) and profile-token tests passed; leftover failures were clean-base (sase-zg flag rule 7, KNOWN import budget/marker audits, FLAKY fakey, NEW sase-1gi helper_error).

## Dependencies

- **Blocks:** [sase-1jm.2.1.5](sase-1jm.2.1.5.md) ◐ · ⧖ 2026-10-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.2.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.2.1.4/README.md) | [sase-1jm.2.1.4](sase-1jm.2.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`18f53d3`](https://github.com/sase-org/sase/commit/18f53d3e57626ac868975005e6d0fb4e720c09ab) | feat(query): add agents-archive profile and host-owned in: token | [sase-1jm.2.1.4](sase-1jm.2.1.4.md) | 2026-10-10 11:40:40 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jm.2.1.4][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.2.1.4/README.md

<!-- sase:referenced-by:end -->
