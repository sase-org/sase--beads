# Bead: sase-bc.1 — Add \`bob highlights create \<md\_file\>\` to bob-cli

[Bead Pages](../README.md) / [sase-bc](README.md) / sase-bc.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-bc.1` · **Size:** medium
**Created:** 2026-07-30 17:32:49 UTC · **Closed:** 2026-07-30 17:48:28 UTC
**Plan:** [202607/commit\_file\_hooks.md](https://github.com/sase-org/sase--plans/blob/main/202607/commit_file_hooks.md)

## Description

highlights-create: add a Rust clap subcommand to the bob-cli highlights group that converts a markdown file into a beautiful, TOC-indexed PDF under ~/bob/lib/chat/ via a pandoc shell-out, embeds the page-1 /Text Highlights marker annotation with lopdf so `bob highlights scan` later creates the Obsidian ref note, and ships polished colored success/failure output, docs, and tests.

## Notes

[2026-07-30T17:51:51Z · sase-bc.1] Implemented and pushed bob highlights create in commit 4f72d29; verified title fallback, safe output/ref-type derivation, marker validation, overwrite and sidecar refusals, dry-run no writes, pandoc failure diagnostics, real pandoc/xelatex rendering with PDF outlines and page-1 marker, doctor/help/docs/install-smoke coverage, and full just all (370 unit, 230 CLI, 27 Dataview parity, 31 Tasks parity, real-vault parity, doc tests).

## Dependencies

- **Blocks:** [sase-bc.4](sase-bc.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-bc.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-bc.1/README.md) | [sase-bc.1](sase-bc.1.md) | 0 |
