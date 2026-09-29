# Bead: sase-1ck.4.1 — Bead note attachment CLI

[Bead Pages](../README.md) / [sase-1ck.4](sase-1ck.4.md) / sase-1ck.4.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ck.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ck.4.md) · **Assignee:** `sase-1ck.4.1.land`
**Created:** 2026-09-29 12:24:46 EDT
**Plan:** [202609/note\_cli.md](https://github.com/sase-org/sase--plans/blob/main/202609/note_cli.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/note_cli.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/note_cli.md

<!-- sase:links:end -->

## Description

With the bead_note_attachments beta flag on, inline @path references in bead note text and sase bead attach snapshot files into the local content-addressed store and persist @attachment tokens plus a manifest. With the flag off, note text keeps today's behavior. show, read, JSON, history, list, and path render those snapshots as text. Bytes never enter the bead store, and this work does not upload, fetch, or draw images.

## Notes

[2026-09-29T19:09:15Z · sase-1ck.4.1.land] LAND AUDIT / FOLLOW-UP TRIAGE (2026-09-29, c2aec595c8): Read all three child beads and their notes, the approved note_cli plan, and the three epic commits. Source has flag-gated note authoring and TUI retry, close/update/attach writers, and text/JSON/history/list/path readers. The child phase 2 report is confirmed: Rust TaskPlusOneEvidenceWire lacks attachments; ordinary +1 rejects manifests, and a snooze wake generates a note without matching attachment tokens. This is remaining work of this epic; a completion tale must add core/Python persistence and presentation, then land. Since first epic commit 7226499078, overlapping source changes are the two other epic commits; intervening ACE/prompt-prediction and test-split changes do not consume or conflict with the new attachment API. Commit eaa4aa4aa7 added an origin launch argument and broke older launch mocks. Proposals: phases .1 note 1, .2 note 2, .3 note 1 terminology audit: reproduced 14 unclassified tokens in the core note-attachment fixture; recorded DISCOVERED ISSUE on active parent epic sase-1ck, so no duplicate task. Phases .1 note 2, .2 note 2, .3 note 3 launch-family failures: reproduced origin TypeError in partial-launch and bead-work tests; created ready CI task sase-1cm. Phase .2 note 2 fast-path failures: two guard nodes reproduced and a create-attribution node passes alone; created ready CI task sase-1cn. Phase .2 note 1 +1 attachments: retained in this epic completion tale. Phase .3 note 2 stale sase-1cj.7/.8 Symvision entries: declined a task because Justfile now keys the entries to still-open sase-1cj; epic-symbols for sase-1ck.4.1 is empty. Phase .3 historical descriptor limitation: parent epic note records the permitted fallback for later assessment.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ck.4.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ck.4.1.land.md) | [sase-1ck.4.1](sase-1ck.4.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6834fa1`](https://github.com/sase-org/sase/commit/6834fa1128b60acd23e607694bd60df0867701a0) | feat(bead): persist task +1 note attachments across read surfaces | [sase-1ck.4.1](sase-1ck.4.1.md) | 2026-09-29 16:54:45 EDT |
| sase-core | [`sase-core@0541387`](https://github.com/sase-org/sase-core/commit/0541387eee01040f95aa59333491ea1484e25a25) | feat(bead): task +1 evidence owns its attachment manifest | [sase-1ck.4.1](sase-1ck.4.1.md) | 2026-09-29 16:58:48 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ck.4.1.1][1] | Need parent epic plan details | 1 |
| read-by | [agent:sase-1ck.4.1.land--1][2] | landing verification follow-up | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ck.4.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ck.4.1.land.md

<!-- sase:referenced-by:end -->
