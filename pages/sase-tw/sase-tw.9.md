# Bead: sase-tw.9 — Run the RELATED: note backfill

[Bead Pages](../README.md) / [sase-tw](README.md) / sase-tw.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-tj.land.w3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-tj.land.w3.md) · **Assignee:** `sase-tw.9` · **Size:** small
**Created:** 2026-08-25 15:34:41 EDT · **Closed:** 2026-08-25 18:29:25 EDT
**Plan:** [202608/artifact\_link\_durability\_and\_derivation.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_link_durability_and_derivation.md)

## Description

notes-migration: verify `sase artifact link migrate-notes --apply` on a scratch bead tree, correct its stale help text, and run it for real to convert the 269 auto-convertible `RELATED:` notes into typed related links.

## Notes

[2026-08-25T22:06:05Z · sase-tw.9] RELATED migration applied on 2026-08-25: scanned 4322 beads and 303 RELATED notes; converted 269 parseable note records into 285 related edges/MIGRATED notes; post-apply dry-run has 0 remaining conversions and 34 manual-review items. Worklist:
- sase-h8: does not match RELATED: <id>[, <id>] — <why> -- RELATED: sase-ct. Final gates for the close-out: just check-full passed end to end after local linked sase-core binding rebuild to 0.24.5; just test-visual passed 654/1 in 111.29s; residue just test-contention passed 3 repeats with 0 failed nodes in 185.5s; tools/check_test_wait_helpers exited 0; selection-health reported no new reproducible flakes with only sase-jb and sase-j6 remaining in tests/reproducible_flake_baseline.txt. This note records the umbrella retirement only; this bead remains open for owner handling of its own lifecycle.
- sase-h8.10: does not match RELATED: <id>[, <id>] — <why> -- RELATED: sase-ct. Final gates for the close-out: just check-full passed end to end after local linked sase-core binding rebuild to 0.24.5; just test-visual passed 654/1 in 111.29s; residue just test-contention passed 3 repeats with 0 failed nodes in 185.5s; tools/check_test_wait_helpers exited 0; selection-health reported no new reproducible flakes with only sase-jb and sase-j6 remaining in tests/reproducible_flake_baseline.txt. This note records the umbrella retirement only; this bead remains open for owner handling of its own lifecycle.
- sase-id: does not match RELATED: <id>[, <id>] — <why> -- RELATED: sase-id' line was written before this bead had an ID and should read 'RELATED: sase-ie (Remove the deprecated top-level glossary and amd_h1_title config aliases)'. Ordering guidance is unchanged: do this bead (sase-id) first, so a single later cleanup in sase-ie can retire all six deprecated aliases at once.
- sase-j7: does not match RELATED: <id>[, <id>] — <why> -- RELATED: sase-ct (retired umbrella, do not +1), sase-hj (closed, first recorded this node).
- sase-j7: does not match RELATED: <id>[, <id>] — <why> -- RELATED: sase-ct is the retired umbrella and explicitly forbids +1; routed here via /sase_new_task instead of creating a duplicate task.
- sase-j7: unparseable target 'sase-ct (retired umbrella' -- RELATED: sase-ct (retired umbrella — do not +1).
- sase-kw: unparseable target 'sase-kt and sase-kq' -- RELATED: sase-kt and sase-kq — both closed beads carry close notes from unrelated work re-observing this same failure in their 'just check' runs and classifying it as pre-existing. Neither filed it; they are prior sightings, not duplicates.
- sase-lk: unparseable target 'sase-lc and sase-jq' -- RELATED: sase-lc and sase-jq — both concern the reproducible-flake gate's evidence handling (dirty-workspace audit failures, and long-lived flake records blocking the baseline). A fix here should reduce this bead's records at the source rather than by adjusting the baseline.
- sase-ly: unparseable target 'sase-g5 (closed)' -- RELATED: sase-g5 (closed) — traced an agents-sidecar manifest truncation to vcs_clean_workspace (git reset --hard HEAD + git clean -fd) followed by a branch checkout, running against a clone shared by all sase_<N> workspaces. Same destructive clean primitive, different call site and different repo; that bead's reflog-signature analysis is a useful starting point.
- sase-m6: unparseable target 'sase-ct (retired umbrella' -- RELATED: sase-ct (retired umbrella, not +1'd — this is deterministic, not a flake); sase-ml and sase-mv cover the other, unrelated failures in the same lane and were corroborated separately.
- sase-mf: does not match RELATED: <id>[, <id>] — <why> -- RELATED: sase-mk (separate pre-existing symvision gate failure on the same master tree, already in progress).
- sase-mf: does not match RELATED: <id>[, <id>] — <why> -- RELATED: sase-dl is the retired broad-drift umbrella for renderer/font variance and is a different root cause.
- sase-mi: unparseable target 'sase-li (concurrent bead sync can silently delete an event from a shared stream' -- RELATED: sase-li (concurrent bead sync can silently delete an event from a shared stream — plausible upstream cause of these rewrites); sase-mk (in-progress symvision task whose +1 evidence I could not record because of this).
- sase-mp: unparseable target "sase-mc (in-progress epic 'Temporarily Disable LLM Providers')" -- RELATED: sase-mc (in-progress epic 'Temporarily Disable LLM Providers') — phase sase-mc.3 built the top-bar disabled-provider pill asserted by the very same test, so a fix editing tests/ace/tui/test_top_bar_order.py could collide with that epic's remaining work. It did not cause this failure: bisect pins the break to standalone commit 233d62463.
- sase-mp: unparseable target "sase-mf (in-progress epic 'Simplify built-in model routing and redesign the Models panel')" -- RELATED: sase-mf (in-progress epic 'Simplify built-in model routing and redesign the Models panel') — it owns the launch-settings/size-alias contract behind the '@medium@max' alias pill in this same test and already carries alias-migration DISCOVERED ISSUE notes, so its phase sase-mf.4 verification may touch these assertions. Not the cause of this failure.
- sase-mp: unparseable target 'sase-mk (in-progress task' -- RELATED: sase-mk (in-progress task, symvision private-import failures) and sase-mn (ready task, unused public FilesQueryIndexResult) — the other two independent reasons 'just check' is currently red on master. Fixing this node alone will not make the gate green; symvision runs before the test lane and still stops the recipe first.
- sase-o1: unparseable target 'd9b2984a7 / sase-ns.6.2' -- RELATED: d9b2984a7 / sase-ns.6.2 — 'fix(tui): isolate config center state replacement' solved the same shape (a test patching a process-wide primitive, os.replace) by adding a module-local hook the test patches instead. That is the model fix for this node.
- sase-oi: unparseable target 'sase-of and sase-og' -- RELATED: sase-of and sase-og — the two live beads involved. sase-of is the sase-o9 land agent's bead that my commands wrongly mutated (its notes carry my correction note); sase-og is my bead, the one that was actually created. Both are useful as a real, already-recorded reproduction.
- sase-ok: unparseable target "sase-m4 (in-progress epic 'Stabilize GitHub Actions')" -- RELATED: sase-m4 (in-progress epic 'Stabilize GitHub Actions') — topically similar (a CI job also broke due to missing/misresolved 'just' tooling), but scoped to the sase repo's own default-branch CI (release-core-floor-smoke job missing the just binary entirely: FileNotFoundError), not sase-telegram's separate CI workflow or the extractions/setup-just@v2 action. Different repo, different action, different root cause -- not a duplicate or causally linked, just adjacent context.
- sase-op: does not match RELATED: <id>[, <id>] — <why> -- RELATED: sase-o7 (systemic fix, closed done), sase-o4 / sase-nm (prior per-instance cleanups for closed beads sase-nb / sase-n9).
- sase-os: unparseable target 'sase-qy land' -- RELATED: sase-qy land — skipped regenerating the four artifacts_split PNG goldens because this bead owns the empty-details fixture. The persistent Bead/File query bar from sase-qy.2 now also shifts those frames (plus r6 limit:N / Ctrl+J/K footer). When this bead teaches the split tests to select a row, rebaseline those four nodes (and only those) so they pick up the always-on bar.
- sase-oz: unparseable target 'sase-og and sase-oe' -- RELATED: sase-og and sase-oe — two other open beads filed today with the same outward shape ('fails under the full parallel lane, passes in isolation'). Listed as shape siblings, not duplicates: those are ACE TUI modal/confirmation nodes, while this one asserts Textual worker completion in the AcePage harness teardown. A single mechanism fix could plausibly cover more than one of them, so whoever works this should skim them before designing a fix.
- sase-oz: unparseable target "commit 2959d3992 'fix(ace-tui): stop leaked proc-observer threads between tests'" -- RELATED: commit 2959d3992 'fix(ace-tui): stop leaked proc-observer threads between tests' — the most recent change to tests/test_ace_testing.py and the nearest prior art for this failure family (background work outliving a test). Worth reading first as a possible template for the fix, or as a candidate regression source if the unfinished worker turns out to be a proc observer.
- sase-oz: unparseable target "commit 2959d3992 'fix(ace-tui): stop leaked proc-observer threads between tests'" -- RELATED: commit 2959d3992 'fix(ace-tui): stop leaked proc-observer threads between tests' — the most recent change to tests/test_ace_testing.py and the nearest prior art for this failure family (background work outliving a test). Worth reading first as a possible template for the fix, or as a candidate regression source if the unfinished worker turns out to be a proc observer.
- sase-oz: does not match RELATED: <id>[, <id>] — <why> -- RELATED: sase-qy.4 (194dbebfb) added AcePage pump-free drain of cancelled sase-artifacts-project-choices on exit. sase-r6.land flagged that drain as a candidate fix for this leftover-task flake. Not verified as closed here; still this bead until an isolated full-lane rerun stays green.
- sase-p2: does not match RELATED: <id>[, <id>] — <why> -- RELATED: task sase-o7 tracks the systemic version of this gap.
- sase-p3: does not match RELATED: <id>[, <id>] — <why> -- RELATED: sase-o6 (global 'sase' on PATH is a separate uv tool install, which still logs 'Skipping invalid file hook sase-research-artifacts@research-highlights' for the same missing-provider reason).
- sase-ph: unparseable target 'sase-dc / sase-ny' -- RELATED: sase-dc / sase-ny — prior owners of the four test_ace_png_snapshots_agents_retry_e2e.py nodes (contention flakiness and stale-golden rebaselining respectively, both closed). test_real_fakey_completed_retry_chain_png_snapshot is one of

… and 3593 more characters

## Dependencies

- **Blocks:** [sase-tw.14](sase-tw.14.md) ◐ · ⧖ 2026-08-25
- **Depends on:** [sase-tw.3](sase-tw.3.md) ✓ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tw.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.9/README.md) | [sase-tw.9](sase-tw.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`012a66a`](https://github.com/sase-org/sase/commit/012a66a659853bae9bd27e0c47b0f75178794a80) | fix(artifact-links): make related note migration safe | [sase-tw.9](sase-tw.9.md) | 2026-08-25 18:30:46 EDT |
