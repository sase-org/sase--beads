# Bead: sase-1jx.12.1.2 — Configure new repositories with live checks

[Bead Pages](../README.md) / [sase-1jx.12.1](sase-1jx.12.1.md) / sase-1jx.12.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jx.12](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.12.md) · **Assignee:** `sase-1jx.12.1.2` · **Size:** medium
**Created:** 2026-10-12 10:07:51 EDT · **Closed:** 2026-10-12 11:52:22 EDT
**Plan:** [202610/create\_repository\_wizard.md](https://github.com/sase-org/sase--plans/blob/main/202610/create_repository_wizard.md)

## Description

create-configure: implement the create draft and Configure stage, owner and visibility defaults, pure name normalization, debounced off-thread availability and checkout checks, Rust identity previews, and explicit add-instead transition; keep production Create affordances deferred until the complete path lands.

## Notes

[2026-10-12T15:52:11Z · sase-1jx.12.1.2] PROPOSED FOLLOW-UP: KNOWN symvision failure on _load_archive_bundle in actions/agents/_archive_reader.py (witness 12e0a500206437d2397055336b9b9f45) fails `just check` on this tree and the file is untouched by this phase; needs an owner or whitelist entry

[2026-10-12T15:52:22Z · sase-1jx.12.1.2] create-configure implemented and verified: new new_project_create.py (CreateDraft, owner/visibility defaults, pure parse_repo_ref normalization, 300ms debounced off-thread probe/checkout/plan workers with generation guards, lenient effective options into mode=create plans, explicit add-instead only); modal/state/chrome wired with test-only entry, stage-aware paste, Back/Escape handling; 33 focused tests pass (defaults, normalization, collisions, occupied checkouts, stale results, auth failure, add-instead, unmount, bare git); 3 PNG goldens captured and host-independent (incl. TZ=UTC); sase tool run check verdict no_new_failures (sole failure is the pre-existing KNOWN symvision item, noted as follow-up); epic-symbols clean

## Dependencies

- **Depends on:** [sase-1jx.12.1.1](sase-1jx.12.1.1.md) ✓ · ⧖ 2026-10-12
- **Blocks:** [sase-1jx.12.1.3](sase-1jx.12.1.3.md) ✓ · ⧖ 2026-10-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.12.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.12.1.2/README.md) | [sase-1jx.12.1.2](sase-1jx.12.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3dc675f`](https://github.com/sase-org/sase/commit/3dc675fffe0d5027be31ed47ffb1517fe237d228) | feat(tui): configure new repositories with live checks | [sase-1jx.12.1.2](sase-1jx.12.1.2.md) | 2026-10-12 11:53:56 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jx.12.1.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.12.1.2/README.md

<!-- sase:referenced-by:end -->
