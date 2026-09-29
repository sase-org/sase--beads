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

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/note_cli.md

<!-- sase:links:end -->

## Description

With the bead_note_attachments beta flag on, inline @path references in bead note text and sase bead attach snapshot files into the local content-addressed store and persist @attachment tokens plus a manifest. With the flag off, note text keeps today's behavior. show, read, JSON, history, list, and path render those snapshots as text. Bytes never enter the bead store, and this work does not upload, fetch, or draw images.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ck.4.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ck.4.1.land/README.md) | [sase-1ck.4.1](sase-1ck.4.1.md) | 0 |
