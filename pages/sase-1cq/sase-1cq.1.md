# Bead: sase-1cq.1 — Move the core pin and finish the stranded sase-1ck.4.1 landing

[Bead Pages](../README.md) / [sase-1cq](README.md) / sase-1cq.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u6.md) · **Assignee:** `sase-1cq.1` · **Size:** small
**Created:** 2026-09-29 17:21:20 EDT
**Plan:** [202609/cross\_repo\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202609/cross_repo_landing.md)

## Description

stranded_landing: ratchet sase-core-revision.txt past 0541387 and 1ad57ea, verify the +1 attachment tests, then close epic sase-1ck.4.1 and its parent phase sase-1ck.4 and mark note_cli.md done.

## Notes

[2026-09-29T21:45:11Z · sase-1cq.1] PROPOSED FOLLOW-UP: just symvision flags 6 unused public symbols in src/sase/bead/attachment_attachment_presentation.py and cli_attachment.py (format_attachment_dims/size, handle_bead_attachment_list/path, note_label_attachment_suffix, total_attachment_count); reproduces identically on clean base tree, unrelated to pin move

[2026-09-29T21:45:26Z · sase-1cq.1] PROPOSED FOLLOW-UP correction: file is src/sase/bead/attachment_presentation.py (typo in prior note had a doubled prefix)

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cq.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cq.1/README.md) | [sase-1cq.1](sase-1cq.1.md) | 0 |
