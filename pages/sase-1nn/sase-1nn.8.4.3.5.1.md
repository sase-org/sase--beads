# Bead: sase-1nn.8.4.3.5.1 — Repair the current release gate integration failures

[Bead Pages](../README.md) / [sase-1nn.8.4.3.5](sase-1nn.8.4.3.5.md) / sase-1nn.8.4.3.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nn.8.4.3.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.8.4.3.land.md) · **Size:** medium
**Created:** 2026-10-24 22:21:50 EDT · **Closed:** 2026-10-24 23:01:09 EDT
**Plan:** [202610/v0\_18\_1\_release\_integration.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_release_integration.md)

## Description

integrate: preserve recovery evidence outside tracked source, remove stale Symvision exemptions, and repair recurring UI readiness blockers without weakening checks.

## Notes

[2026-10-25T02:54:06Z · sase-1nn.8.4.3.5.1] PHASE UPDATE: recovery evidence preserved and removed from tracked source. Prior artifact file:explicit:0ad1354ad22ce3480a1a422c covered only ~80 entries; built complete archive of all 99 tracked .sase-evidence/ paths plus path/size/SHA256 MANIFEST.txt, verified byte-identical extraction (0 mismatches, 0 working-tree diffs), registered as file:explicit:ddc1ff91f98de4e168df0d63 attached to sase-1nv.5 and this phase. Stored snapshot SHA256 matches source (1c82bbdb...eeda14e). Removed .sase-evidence/ from git (git rm, 99 paths, 0 remain tracked). No live code references .sase-evidence (only historical bead/plan strings, left intact). test_macro_resources_avoid_xprompt_terms now passes. Symvision clean: stale sase-1o5.3(project_question_round) exemption already consumed by sase-1o5.3 (HEAD 393430da55; real consumer at src/sase/question_gate_turn/projection.py:315); remaining 8 entries verified still-needed under still-open sase-1o5/sase-1o5.5. project_question_round binding confirmed in pinned source (origin/master 3156d11f, crates/sase_core_py/src/prelude.rs); published containing release is core-cut phase business (core-floor-probe blocked_unpublished expected here).

[2026-10-25T02:54:20Z · sase-1nn.8.4.3.5.1] PROPOSED FOLLOW-UP: one-off Full CI gate-singleton mount flake — test_epic_plan_modal_renders_no_raw_editor_for_capacity failed once on CI 3.12 leg (Full CI 40138926091 attempt 2, job 121044209959) with missing #gate-singleton-0 during GateBranchControls.on_mount; passes locally in isolation, in full-file batches (17 passed), and across repeats, so not deterministic. GateBranchControls._update_submit_state queries child buttons from on_mount where the author documents DOM exists; single CI occurrence under full-matrix load points to mount/teardown racing, not a product lifecycle violation. Left for owner triage; no code change made.

[2026-10-25T03:00:55Z · sase-1nn.8.4.3.5.1--1] PROPOSED FOLLOW-UP: test_tui_app_import_stays_under_startup_budget exceeds cap by one on clean base (3538 vs 3537) — reproduces with working tree stashed, triage KNOWN witness 0807aefecc59861aee177979c8a6e2be with no owner; unrelated to 99-file evidence removal

[2026-10-25T03:01:09Z · sase-1nn.8.4.3.5.1--1] check 3655c5cefc27e058d22059a60bed98c7: all lint gates pass (ruff, mypy, symvision, terminology, docs contract, feature flags), committed plans pass, SASE validation passes; core-floor-probe blocked_unpublished exit 4 on project_question_round expected and owned by sibling core-cut phase sase-1nn.8.4.3.5.2; test lane 57498 passed 17 skipped with single KNOWN import-budget failure (3538 vs 3537 cap, witness 0807aefecc59861aee177979c8a6e2be) verified pre-existing on clean base tree via stash; 99 .sase-evidence files archived to file:explicit:ddc1ff91f98de4e168df0d63 (byte-identical, MANIFEST verified) and removed from git; binding pin confirmed; UI flakes non-reproducing; epic-symbols empty

## References

- file:explicit:ddc1ff91f98de4e168df0d63

## Dependencies

- **Blocks:** [sase-1nn.8.4.3.5.3](sase-1nn.8.4.3.5.3.md) ✓ · ⧖ 2026-10-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nn.8.4.3.5.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.8.4.3.5.1.md) | [sase-1nn.8.4.3.5.1](sase-1nn.8.4.3.5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3d13864`](https://github.com/sase-org/sase/commit/3d13864e7632da0911e98ef2ba7e00e669527556) | chore(integrate): archive recovery evidence and remove tracked .sase-evidence | [sase-1nn.8.4.3.5.1](sase-1nn.8.4.3.5.1.md) | 2026-10-24 23:02:56 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nn.8.4.3.5.1--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.8.4.3.5.1.md

<!-- sase:referenced-by:end -->
