# Bead: sase-1ck.5.1.3 — Placement, pre-publication upload, and outbox

[Bead Pages](../README.md) / [sase-1ck.5.1](sase-1ck.5.1.md) / sase-1ck.5.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ck.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ck.5.md) · **Assignee:** `sase-1ck.5.1.3` · **Size:** medium
**Created:** 2026-09-29 17:24:38 EDT · **Closed:** 2026-09-29 18:50:51 EDT
**Plan:** [202609/private\_attachment\_store.md](https://github.com/sase-org/sase--plans/blob/main/202609/private_attachment_store.md)

## Description

upload: place attachments with core policy and -L/--local-only, upload after the bead commit and before bead publication, and persist a durable outbox that attachment push and bead sync can drain.

## Notes

[2026-09-29T22:49:31Z · sase-1ck.5.1.3] PROPOSED FOLLOW-UP: symvision _lint-symvision gate is red on the clean base tree (identical failure with changes stashed): _kitty_graphics_support imported in src/sase/doctor/checks_deep_terminal.py and _roster_for_issue imported from sase.bead.cli_attachment (via attachment_resolve.py). Pre-existing, not caused by the upload phase.

[2026-09-29T22:50:51Z · sase-1ck.5.1.3] Upload phase done: placement via core attachment_placement with git tier and -L/--local-only on note/close/update/+1/attach; post-commit upload before bead publication with require_upload pre-append path; durable outbox at projects/<key>/attachment-upload-outbox.json drained opportunistically, in bead sync, and via bead attachment push (also promotes local-only). Verified: 6 new tests in tests/test_bead/test_attachment_upload.py pass, neighbor suites (attach verbs, note attachments, git store, CAS: 69 tests) pass, ruff and mypy clean, epic-symbols clean. Pre-existing symvision red on clean base recorded as follow-up.

## Dependencies

- **Depends on:** [sase-1ck.5.1.1](sase-1ck.5.1.1.md) ✓ · ⧖ 2026-09-29
- **Depends on:** [sase-1ck.5.1.2](sase-1ck.5.1.2.md) ✓ · ⧖ 2026-09-29
- **Blocks:** [sase-1ck.5.1.4](sase-1ck.5.1.4.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ck.5.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ck.5.1.3/README.md) | [sase-1ck.5.1.3](sase-1ck.5.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c8796af`](https://github.com/sase-org/sase/commit/c8796af46d5e1d95bfd3aaad337602cfa4fd44f4) | feat(bead): placement, pre-publication upload, and attachment outbox | [sase-1ck.5.1.3](sase-1ck.5.1.3.md) | 2026-09-29 18:54:21 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ck.5.1.3][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1ck.land][2] | Need the child notes to cross-check follow-up triage | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ck.5.1.3/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ck.land/README.md

<!-- sase:referenced-by:end -->
