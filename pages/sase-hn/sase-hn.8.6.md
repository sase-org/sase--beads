# Bead: sase-hn.8.6 — Repair the Patch/stitch terminology gate and finish the test-tree sweep

[Bead Pages](../README.md) / [sase-hn.8](sase-hn.8.md) / sase-hn.8.6

**Status:** ◎ claimed · **Type:** ▸ plan · **Tier:** epic · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-hn.8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hn.8.land/README.md) · **Assignee:** `sase-hn.8.6.land--code`
**Created:** 2026-08-09 04:14:49 EDT
**Plan:** [202608/patch\_audit\_gate\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202608/patch_audit_gate_repair.md)

## Previously Closed

> ↺ Closed 2026-08-09T11:28:45Z · done
>
> (none)
>
> Reopened 2026-08-09T11:31:21Z by `sase bead open`

## Description

The Patch/stitch terminology gate passes on an ordinary checkout and in CI, the audit can report a defect anywhere under tests/ and smoke/ instead of rubber-stamping them, the test tree says Patch and stitch, and epic sase-hn.8 is closed with its plan marked done.

## Notes

[2026-08-09T11:28:45Z · sase-hn.8.6.land] Landing verified all four child phases and their full note histories: gate repair preserves tolerant routine lint and strict explicit audit behavior; the non-TUI and ACE TUI test sweeps use canonical Patch/stitch helpers and explicit retained-boundary annotations; and content-aware tests/smoke classification is now unconditional with the temporary flag removed. Reviewed epic commits 4a855032f, 684eddd2d, 7feb0b84b, and fbd1714d6 and the resulting Justfile, audit implementation, contract tests, and test tree. No child contains a PROPOSED FOLLOW-UP entry, so no follow-up task was warranted or declined. Integration audit from first epic commit 4a855032f through HEAD found only the epic's four child commits; master and origin/master are identical, so there are no later non-epic or base-branch changes to adapt, duplicate, or resolve. Independent verification passed: 12 focused audit tests; strict audit across main, sase-core, sase-github, sase-telegram, sase-nvim, and chezmoi with zero defects/stale rules/missing repos; git diff --check; just check-full including all lint, validation, non-visual tests, and flake baseline; and just test-visual with 570 passed, 1 skipped and unchanged PNG goldens.

[2026-08-09T11:31:33Z · sase-hn.8.6.land] DISCOVERED ISSUE: Post-start integration commit 1659154a7 restores legacy workspace-provider hookspec argument names correctly, but its new contract test leaves eight changespec_file/changespec_parent occurrences unclassified by the content-aware Patch/stitch audit. The compatibility boundary is intentional and already documented globally; add audit-visible local legacy-boundary annotations without weakening classifier rules, then rerun focused/full verification and repeat the landing close sequence.

[2026-08-09T11:31:43Z · sase-hn.8.6.land] DISCOVERED ISSUE: Post-start integration commit 1659154a7 restores legacy workspace-provider hookspec argument names correctly, but its new contract test leaves eight changespec_file/changespec_parent occurrences unclassified by the content-aware Patch/stitch audit. The compatibility boundary is intentional and already documented globally; add audit-visible local legacy-boundary annotations without weakening classifier rules, then rerun focused/full verification and repeat the landing close sequence.

[2026-08-09T11:44:43Z · wa] DISCOVERED ISSUE: Independent reproduction during unrelated glossary alias-label implementation on 2026-08-09. 'just check' passed fmt, keep-sorted, Ruff, mypy, pyscripts, test-wait, and changelog gates, then failed _lint-patch-stitch-terminology with eight unclassified legacy workspace-provider hookspec tokens in tests/test_workspace_provider_hookspec.py:88,89,126,135,240,245,251,257 (changespec_file / changespec_parent). This matches the existing post-start integration note for commit 1659154a7 and belongs to this Patch/stitch audit repair; no standalone task bead created.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-hn.8.6.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-hn.8.6.land.md) | [sase-hn.8.6](sase-hn.8.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`11cd863`](https://github.com/sase-org/sase/commit/11cd8634d6be9acd2c0e1b6fa5ff8fe5779a08ed) | test: annotate legacy workspace hook arguments | [sase-hn.8.6](sase-hn.8.6.md) | 2026-08-09 07:48:10 EDT |
