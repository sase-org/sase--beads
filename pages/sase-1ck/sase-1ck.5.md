# Bead: sase-1ck.5 — Private attachments sidecar, upload outbox, and lazy fetch

[Bead Pages](../README.md) / [sase-1ck](README.md) / sase-1ck.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tv](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tv.md) · **Assignee:** `sase-1ck.5` · **Size:** large
**Created:** 2026-09-29 08:13:41 EDT · **Closed:** 2026-09-29 20:29:40 EDT
**Plan:** [202609/bead\_note\_attachments.md](https://github.com/sase-org/sase--plans/blob/main/202609/bead_note_attachments.md)

## Description

shared_store: add the reserved private attachments-private sidecar role (repo <project>--attachments-private, a hidden bare partial clone), the git BlobStore written with plumbing, and placement with explicit -L local-only. Add pre-publication uploads with an outbox fallback, capped lazy fetch, availability badges, attachment push, and a doctor check.

## Notes

[2026-09-29T14:02:36Z · 33] SCOPE AMENDMENT (2026-09-29, research:202609/bead_attachment_audience/bead_attachment_audience.md §8): the role is now attachments-private (repo <project>--attachments-private), and the plain attachments name is reserved for a future public store; sase-github --private creation and visibility-reporting preflight landed separately, so don't reimplement them, only add the sase-side preflight test; the store stays private-only, and phases never create real GitHub repos; the epic plan's Phase 5 carries the details.

[2026-09-30T00:30:36Z · sase-1ck.5.1.land] Phase verification (tale lazy_attachment_discovery closeout): epic sase-1ck.5.1 work matches this phase scope — hidden bare attachments-private sidecar, git blob store, placement with -L / pre-publication upload / outbox / attachment push, capped lazy fetch (now fully lazy on show/read via discover flag), availability badges, and the project.attachment_store doctor check. Phase auto-closed with the epic close; parent epic sase-1ck left open for its land agent.

## Dependencies

- **Depends on:** [sase-1ck.4](sase-1ck.4.md) ✓ · ⧖ 2026-09-29
- **Blocks:** [sase-1ck.6](sase-1ck.6.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ck.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ck.5.md) | [sase-1ck.5](sase-1ck.5.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:33--1][1] | verify | 1 |
| read-by | [agent:research.n.cld][2] | Check progress of attachment wire and shared-store phases to judge whether a visibility field can be added early | 1 |
| read-by | [agent:research.n.final][3] | Check whether the private attachments sidecar phase covers sase-github private repo creation and role naming | 2 |
| read-by | [agent:research.n.mus][4] | Research private sidecar phase scope for public attachment alternative | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.33.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.n.cld/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.n.final/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.n.mus/README.md

<!-- sase:referenced-by:end -->
