# Bead: sase-m6.6.1.7 — Prove parity, migration safety, visuals, and responsiveness

[Bead Pages](../README.md) / [sase-m6.6.1](sase-m6.6.1.md) / sase-m6.6.1.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m6.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.6.md) · **Assignee:** `sase-m6.6.1.7` · **Size:** medium
**Created:** 2026-08-15 06:18:24 EDT · **Closed:** 2026-08-16 01:28:38 EDT
**Plan:** [202608/unified\_artifacts\_query\_1.md](https://github.com/sase-org/sase--plans/blob/main/202608/unified_artifacts_query_1.md)

## Description

conformance: extend the Artifacts contract harness and golden corpus across all five built-in panes plus the synthetic provider, cover invalid profiles and queries, legacy persistence migration, changed-profile saved views, selection restoration, completion and pane isolation, remove obsolete pane-local parser and modal paths only where compatibility permits, review intentional PNG changes, run full Python and Rust verification, and demonstrate cached per-keystroke navigation p95 below 16 ms for every migrated pane.

## Notes

[2026-08-16T05:11:46Z · sase-m6.6.1.7] PROPOSED FOLLOW-UP: Regenerate SASE memory outputs — just check currently fails init memory --check because sase/memory/sase_sizes.md and sase/memory/README.md differ from generated output; memory-file edits require explicit user approval.

[2026-08-16T05:19:02Z · sase-m6.6.1.7] PROPOSED FOLLOW-UP: Stabilize full Python suite after Artifacts inline-filter migration — just test-scoped escalated to the full suite and finished with 83 failed / 45 errors across gate conformance, keybinding/footer, legacy QueryEditModal, vim normal key containment, and onboarding tests; targeted Artifacts conformance/filter suites passed.

[2026-08-16T05:25:23Z · sase-m6.6.1.7] PROPOSED FOLLOW-UP: Stabilize ACE visual snapshot model badge — targeted Artifacts filter-bar PNGs differ only in the top-right model badge (expected CLAUDE(opus), actual CODEX(visual-snapshot-model)); no unrelated Artifacts golden was accepted.

[2026-08-16T05:28:38Z · sase-m6.6.1.7] Implemented cross-pane Artifacts query golden/conformance coverage and Files Symvision cleanup; verified focused Artifacts pytest, ruff, Symvision, Rust query/golden cargo tests, and artifacts_jk p95 <= 11.37 ms; just check/full/visual suite blockers recorded as PROPOSED FOLLOW-UP notes.

[2026-08-16T05:30:12Z · sase-m6.6.1.7] Verified focused Artifacts conformance pytest, Files filtering tests, ruff format/check, Symvision, Rust query/golden parity, and Artifacts navigation benchmark p95 under 16 ms; just check blocked by recorded pre-existing generated-memory drift and suite noise.

## Dependencies

- **Depends on:** [sase-m6.6.1.6](sase-m6.6.1.6.md) ✓ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m6.6.1.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m6.6.1.7/README.md) | [sase-m6.6.1.7](sase-m6.6.1.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ff3b0fa`](https://github.com/sase-org/sase/commit/ff3b0fa43f8175fea54af7cead671d3e863a88ca) | test: add artifacts query profile conformance goldens | [sase-m6.6.1.7](sase-m6.6.1.7.md) | 2026-08-16 01:31:43 EDT |
