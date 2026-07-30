# Bead: sase-av.3 — Copy and hand off references from the Artifacts sub-tabs

[Bead Pages](../README.md) / [sase-av](README.md) / sase-av.3

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-av.3` · **Size:** medium
**Created:** 2026-07-29 16:46:36 UTC · **Closed:** 2026-07-29 18:37:13 UTC
**Plan:** [202607/artifact\_refs\_and\_prompt\_bar.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_refs_and_prompt_bar.md)

## Description

copy-ref: give Commits, Plans, Chats, and Bugs copy-mode targets that copy the selected entry's `@`-reference and seed a new agent prompt with it (including marked sets), and show the logical reference beside its resolved path in the Plans and Chats detail surfaces.

## Notes

[2026-07-29T18:37:13Z · sase-av.3] Implemented uniform Artifacts %@ copy-reference and %! new-agent handoff for Commits, Plans, Chats, and Bugs, including visible marked sets and explicit no-reference warnings; added logical Reference-before-Path detail rows for archive plans and chats; synchronized keymaps, footer, command palette, help, docs, tests, and intentional PNG goldens. Verified 91 focused non-visual tests, exact equality for both changed PNG snapshots, the independent concurrency rerun, Symvision, and the full repository gate with COLUMNS=160 just check.

## Dependencies

- **Depends on:** [sase-av.2](sase-av.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-av.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-av.3/README.md) | [sase-av.3](sase-av.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`d16fe1d`](https://github.com/sase-org/sase/commit/d16fe1dcd9abe1bcc0e6b44af0bc98e2b0ad5788) | feat(ace): copy artifact references from artifact tabs | [sase-av.3](sase-av.3.md) | 2026-07-29 18:38:57 |
