# Bead: sase-1i5.9.1.1 — Publish a complete sase-core-rs release that contains sase's pin

[Bead Pages](../README.md) / [sase-1i5.9.1](sase-1i5.9.1.md) / sase-1i5.9.1.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1i5.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1i5.9.md) · **Assignee:** `sase-1i5.9.1.1` · **Size:** medium
**Created:** 2026-10-08 14:37:03 EDT
**Plan:** [202610/release\_sase\_core\_and\_plugin\_floors.md](https://github.com/sase-org/sase--plans/blob/main/202610/release_sase_core_and_plugin_floors.md)

## Description

core-release: make sase-core master CI green by applying the recorded event-store doctor expectation fix, cut the release with the documented dry_run=false dispatch, and prove the published tag contains the pin and is complete on PyPI.

## Notes

[2026-10-08T18:56:40Z · sase-1i5.9.1.1] Progress: applied sase-1h8 note-#3 fix (negated issues.jsonl-missing assertion for event stores in bead_read_parity.rs); sase tool run check run 507ed46da93dc9504deb9bc890d58bfb passed exit 0. sase-1h8 noted; epic-symbols clean. Remaining: land fix, wait sase-core CI green, dispatch release-plz dry_run=false (PR #323 head contains pin cd73d968), prove tag+PyPI complete, then close. -r recoverable progress for monitor-chain successor

[2026-10-08T19:11:36Z · sase-1i5.9.1.1--1] Progress: sase-core gate re-run passed exit 0 (tool run 259aede78260ee23de18441791fd59a8) on fix tree. Release PR sase-org/sase-core#323 head 3dce662 contains pin cd73d968 (compare: ahead 3, behind 0). Master CI run 37828594205 in_progress on unrelated commit; fix not yet landed. SUCCESSOR: after host lands fix, wait sase-core CI green on landed commit, re-verify release PR head contains pin, dispatch gh workflow run release-plz.yml --repo sase-org/sase-core -f dry_run=false, prove new sase-core-rs tag contains pin and pypi status complete (5 suffixes, none yanked), run epic-symbols, close bead. -r monitor-chain handoff for release successor

## Dependencies

- **Blocks:** [sase-1i5.9.1.3](sase-1i5.9.1.3.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1i5.9.1.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1i5.9.1.1.md) | [sase-1i5.9.1.1](sase-1i5.9.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@e411a39`](https://github.com/sase-org/sase-core/commit/e411a392bb2ddec27534aea4da1ad69bf2bd86ea) | fix(tests): expect no issues.jsonl-missing warning for event-store bead reads | [sase-1i5.9.1.1](sase-1i5.9.1.1.md) | 2026-10-08 15:13:56 EDT |
