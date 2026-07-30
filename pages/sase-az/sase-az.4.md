# Bead: sase-az.4 — File-kind representations in the artifact-files modal

[Bead Pages](../README.md) / [sase-az](README.md) / sase-az.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-az.4` · **Size:** medium
**Created:** 2026-07-29 23:12:41 UTC · **Closed:** 2026-07-30 01:46:53 UTC
**Plan:** [202607/copy\_as\_palette.md](https://github.com/sase-org/sase--plans/blob/main/202607/copy_as_palette.md)

## Description

files: give the artifact-files modal the same palette on the copy prefix with the full file-kind representation set — @file reference, Markdown link, contents, stored path, source path (origin-labeled, missing-aware), and metadata JSON matching sase artifact show -j — for single rows and marked sets, keeping y/Y as accelerators.

## Notes

[2026-07-30T01:46:53Z · sase-az.4] Implemented and verified the artifact-files Copy as palette: configured-prefix entry, @file refs, Markdown links, capped Markdown contents, explicit stored/source paths, CLI-parity metadata JSON, snapshots, marked-set partial handling, disabled reasons, y/Y accelerators, docs/help, and PNG coverage. Focused registry/modal/fixture suite: 71 passed. PNG golden passed again without update mode. just check passed formatting and all lint stages before stopping on pre-existing plans-sidecar prompt-link validation errors. Full just test reached 24,075 passed and 7 skipped with 3 unrelated parallel timing failures; all 3 passed immediately in isolation.

[2026-07-30T01:48:08Z · sase-az.4] Verified the artifact-files Copy as palette with 71 focused tests and its PNG golden; full suite reached 24,075 passed and 7 skipped with three unrelated timing failures that passed in isolation; formatting and all lint stages passed before pre-existing plans-sidecar prompt-link validation errors stopped just check.

## Dependencies

- **Depends on:** [sase-az.3](sase-az.3.md) ✓
