# Bead: sase-um.9 — Finish the release gate — repair the chop's per-repo scoping, green both lanes, and ship v0.17.0

[Bead Pages](../README.md) / [sase-um](README.md) / sase-um.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-um.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-um.land.md) · **Assignee:** `sase-um.9.land`
**Created:** 2026-08-28 15:48:57 EDT · **Closed:** 2026-08-29 14:32:20 EDT
**Plan:** [202608/release\_gate\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/release_gate_completion.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202608/release_gate_completion.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202608/release_gate_completion.md

<!-- sase:links:end -->

## Description

The three release repositories sase-org/sase, sase-org/sase-github, and sase-org/sase-telegram each merge their release PRs again under the merge strategy and gating workflows that repository actually has; Full CI and the Master Gate are both green on the tip; and sase v0.17.0 is tagged and published to PyPI.

## Notes

[2026-08-29T18:32:20Z · sase-um.9.5.land] LANDED by sase-um.9.5.land on 2026-08-29, resuming the interrupted sase-um.9 landing
after its child epic sase-um.9.5 closed. Rechecked descendants, the linked plan, and
post-child drift rather than inheriting the child's verdict.

\## Descendants

All four phases (9.1 chopscope, 9.2 heavy, 9.3 gate budget, 9.4 ship) closed, plus child
epic sase-um.9.5 closed. Every phase note's follow-up was dispositioned, and I confirmed
each disposition still holds:

- 9.1 #1 (source-env chop doctor Telegram gap) -> task sase-ve, open and unmerged into
  this epic, as intended.
- 9.1 #2 (bugyi-chops dev env needed unreleased SASE) -> epic-caused, resolved: b0f6698
  declares sase>=0.17.0,<0.18.0 and 9.5.5 proved a clean public-index `just check`.
- 9.2 #1 (stale generated memory / provider shims) -> the child plan recorded this as
  already fixed by later memory-init commits. That was premature: this host's chezmoi
  home memory README was still two lines stale today (commit 179187499 removed
  `sase memory write` / `sase memory review` without republishing it), which failed
  `sase validate`'s init-memory step and therefore failed `just check` for every agent
  on this host. Republished during this landing; chezmoi commit b7411fe1 contains
  exactly that two-line removal.
- 9.3 #1 (Pillow-free fast suite so the gate can drop install-visual) -> folded into
  9.5.2 as the plan intended and delivered: tools/run_pytest FAST_MARKER_EXPRESSION is
  "not slow and not visual" and ignores tests/ace/tui/visual and tests/pager/visual
  before collection, and master-gate.yml no longer installs the visual stack.
- 9.3 #2 (test_updates_pane_sase_update_confirm_executes_and_refreshes) -> recorded as
  sase-qr's ninth +1; verified present on that bead.
- 9.4 #2 (publish bugyi-chops 0.9.0; neutralize gh JSON color in ci_watch) -> epic-caused
  blockers, both delivered: ci_watch.py:71-73 forces GH_FORCE_TTY/NO_COLOR/CLICOLOR and
  PyPI carries bugyi-chops 0.9.0.

\## Linked plan readiness -- all seven acceptance criteria, remeasured now

Measured 2026-08-29T18:0xZ, independently of 9.5.4's 17:36Z snapshot:

1. Cancelled in the trailing 50 Master Gate runs on master: 0.
2. Trailing-50 completed median wall: 7.27 min (mean 9.21, min 6.13, max 23.35;
   success-only median 7.44 over n=22). Meets <=8 min.
3. Master commits in the last 24h with a Master Gate run: 46/46 (100%), all completed.
   Meets >=90%.
4. ci_watch reached `eligible`: the 2026-08-29T13:29:16-04:00 live tick merged
   sase-org/sase #284 (classification_reason=green, release_reason=merged), and reasons
   are gating/heavy rather than default_branch_not_green.
5. Guarded release merge: merge commit ec24701af has two parents, 31b7cba99 (master) and
   bb40e49979 (PR head) -- a real `gh pr merge --merge --match-head-commit`, not a
   hand-squash.
6. PR ci.yml pull_request queue wait: p50 0.00s over 30 runs. Meets <=1 min.
7. v0.17.0 tagged at ec24701af, GitHub release published 2026-08-29T17:32:03Z, PyPI
   latest 0.17.0.

Plugin repositories rechecked: sase-github resolves to `no_release_pr` and sase-telegram
to `release_pr_not_clean` -- neither reports `gating_workflow_missing` nor
`heavy_lane_not_green`, so the §1.1 regression this epic existed to remove is gone.
sase-telegram #21 is still unmerged, but on its own dirty merge state, which is not one
of this plan's acceptance criteria and not a gate defect.

\## Post-child drift

Nine of the trailing twenty Master Gate runs are red; every one is attributed, and none
leaves this epic incomplete:

- Three (33265764923 / ec24701af, 33265829932 / b726d0a18, 33266986117 / da1da7aea)
  failed on exactly one node,
  test_init_memory_committed_drift.py::test_repo_project_memory_notes_match_generator_output.
  That is this epic's own regression -- publishing 0.17.0 bumped the version embedded in
  the committed generated task-type strands. Fixed inside sase-um.9.5's landing by
  removing the installed-version field from the generated strand rather than
  regenerating it, since regeneration would go stale again on 0.17.1; `just check` is
  green on the fix.
- Four (33256370905, 33257363153, 33258351532, 33259538015) failed on the wait-directive
  completion-range family (test_ace_and_lsp_wait_prose_replacement_ranges_match,
  test_directive_arg_completion_ranges_stop_at_unterminated_body_prose,
  test_wait_arg_completion_preserves_prose_to_cursor_right). All predate this epic's
  commit 25565fca1, which ratcheted sase-core-rs to 0.32.16; 33261735456 on 25565fca1 is
  green. Bead sase-vl tracks the flake-baseline side of that node.
- One (33263360139 / 1be5429ea) failed on a local `git clone` exiting 128 with stderr
  swallowed in tests/test_bead/sync_conflict_regression_helpers.py:34. Recorded as a
  third site on task sase-vp, which already covers this exact defect shape.
- One (33250728696 / 02cbef7af) is in the same wait-directive family.

So after the sase-um.9.5 fix lands, no red Master Gate on master is attributable to this
epic.

`sase bead epic-symbols sase-um.9` reports no --epic-symbol entries; `just symvision`
is clean (the one remaining --epic-symbol line is keyed to sase-n4, a different
in-progress epic).
