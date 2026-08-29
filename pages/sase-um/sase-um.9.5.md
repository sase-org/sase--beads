# Bead: sase-um.9.5 — Complete the interrupted sase-um.9 release-gate landing

[Bead Pages](../README.md) / [sase-um.9](sase-um.9.md) / sase-um.9.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-um.9.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-um.9.land.md) · **Assignee:** `sase-um.9.5.land`
**Created:** 2026-08-28 20:17:48 EDT · **Closed:** 2026-08-29 14:27:35 EDT
**Plan:** [202608/finish\_release\_gate\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/finish_release_gate_landing.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202608/finish_release_gate_landing.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202608/finish_release_gate_landing.md

<!-- sase:links:end -->

## Description

Meet the remaining live gate criteria, ship SASE v0.17.0 through ci_watch, and publish a SASE-0.17-compatible bugyi-chops 0.9.0.

## Notes

[2026-08-29T18:27:35Z · sase-um.9.5.land] LANDED by sase-um.9.5.land on 2026-08-29. All five phases verified against source and
live evidence, one epic-caused regression found and fixed, nine phase proposals
dispositioned.

\## 1. Phase verification (read the code and the runs, not just the notes)

- 9.5.1 chopcolor: bugyi-chops 36c925f sets GH_FORCE_TTY=0 / NO_COLOR=1 / CLICOLOR=0 in
  src/bugyi_chops/ci_watch.py:71-73 on every gh call. Confirmed in the checkout.
- 9.5.2 gatebudget: .github/workflows/master-gate.yml runs eight shards
  (shard: [1..8], fail-fast: false, timeout 20m) and the fast lanes no longer install
  the visual renderer stack; tools/run_pytest FAST_MARKER_EXPRESSION is
  "not slow and not visual" and ignores tests/ace/tui/visual + tests/pager/visual before
  collection.
- 9.5.3 fullgreen / 9.5.4 ship: every fix named in the notes is present on master --
  ca7692ee3 (test_running_agents_snapshot.py:93 patches process_identity.pid_is_thread),
  e856c6804 (test_panel_tab_strip_compact.py:101 wait_for on strip._tier),
  60043deb9 (test_plugins_browser_pane_sase_update.py:103-121 captures only the restart
  helper's poll timer), c1a5b36f5, 4a8b8358f, 49d6c4188.
  sase-core-revision.txt is 51df9061 and pyproject pins sase-core-rs>=0.32.16,<0.33.0,
  matching 25565fca1's ratchet.
- Release evidence, all reconfirmed live: tag v0.17.0 -> ec24701af; GitHub release
  published 2026-08-29T17:32:03Z; PyPI sase latest 0.17.0. Merge commit ec24701af has
  two parents (31b7cba99 master + bb40e49979 PR head), i.e. a real --merge, not a
  hand-squash. bugyi-chops: b0f6698 declares sase>=0.17.0,<0.18.0, version 0.9.0, tag
  v0.9.0 exists, PyPI bugyi-chops 0.9.0 carries Requires-Dist sase<0.18.0,>=0.17.0.
  Full CI 33261893215 is success on 25565fca1.
- Acceptance remeasured 2026-08-29T18:0xZ over the trailing 50 completed Master Gate
  runs on master: 0 cancelled; median wall 7.27 min (mean 9.21, min 6.13, max 23.35);
  success-only median 7.44 min over n=22. Both bounds still met.

\## 2. Integration with post-epic commits, and the one regression this epic caused

35 commits landed between fa74163b5 and da1da7aea. Nineteen are not this epic's
(sase-vd workspace-identity work, the sase-vk memory-web work, memory plan work, TUI
fixes, test splits); none of them duplicate or conflict with what this epic added.

The epic did leave one regression, and it was live on master when this landing started:
publishing v0.17.0 bumped the package version, and the committed generated task-type
strands embed the *installed* distribution version in their Provenance section
(root_rendering_task_types.py rendered "- Version: `{provenance.version}`"). The five
strands still said 0.16.0, so
tests/main/test_init_memory_committed_drift.py::test_repo_project_memory_notes_match_generator_output
failed on every master commit after the release. Three consecutive Master Gate runs were
red on that single node and nothing else: 33265764923 (ec24701af), 33265829932
(b726d0a18), 33266986117 (da1da7aea). PR #298 (release 0.17.1) was blocked behind it.

Fixed in this landing by removing the version from the generated strand rather than
regenerating the strands, because regeneration is a treadmill: the value is per-install
environment state, so it would go stale again on 0.17.1 and it already differs between a
fresh install and an editable checkout whose metadata lags pyproject.toml (this
workspace reported 0.16.0 at HEAD da1da7aea until just install). The committed
sase/task_types.json snapshot already omits version for the same reason
(task_type_snapshot_entry carries source/package/digest only), and
`sase bead task-type show` still reports the live version, so no contract was lost. The
strand test now pins the exclusion instead of asserting the field's presence.
Verified: sase memory init --check clean for project scope, 17 init-memory and 43
task_types tests pass, `sase bead task-type show bug` still prints version 0.17.0,
`just check` fully green (all lint gates + scoped lane).

Also repaired while unblocking that gate: commit 179187499 (removed
`sase memory write` / `sase memory review`) left this host's chezmoi home memory README
two lines stale, which failed `sase validate`'s init-memory step and so failed
`just check` for every agent on this host. Republished with `sase memory init`; chezmoi
commit b7411fe1 contains exactly that two-line removal and swept in none of the
unrelated modified shims in that tree.

Deferred, deliberately: `sase validate` warns that 7 provider skill files are out of
sync with their rendered sources (the /sase_memory_write skill added by 80f389d74 is not
deployed to this host yet). That warning is non-blocking and says redeploy is deferred
until land; `sase init skills` should be rerun once this landing's commit is on master.

\## 3. Follow-up dispositions (all nine phase proposals)

Corroborated existing tasks (no new bead):
- 9.5.4 #10a rust-lsp-install stale binary -> +1 on sase-v6, which already reports the
  same hard-coded checkout-local cargo target dir and the same silent copy failure.
- 9.5.4 #8 PromptInputBar/FrontmatterPanel on_mount NoMatches -> +1 on sase-nf (same
  node, same '#frontmatter-raw' selector), carrying the new root-cause evidence and the
  negative result that a call_after_refresh deferral fails 468 prompt-bar tests.
- 9.5.3 #7 perf-floors persistent_query_keystroke 0.46us over ceiling -> +1 on sase-u8,
  same root cause and same remediation (hosted-runner variance against a tight
  per-anchor absolute ceiling); a fix that only moves the scan_facade ceiling would
  leave this anchor red.

New tasks, each named for its node or site, each linked to the beads it is adjacent to:
- sase-vm (flake, large): test_warm_cache_update_display_does_not_walk_artifacts_on_event_loop
  sees one discover walk on a warm cache; related sase-ct, sase-j7.
- sase-vn (flake, large): test_ace_page_group_rejects_overlapping_checkouts raises
  NoMatches on #stitches-timeline; related sase-ct, sase-nf.
- sase-vo (flake, large): test_commits_persistent_filter_small_terminal_png_snapshot
  captures a frame wait_for_visual_idle accepted; related sase-uy, and sase-up
  explicitly ruled out (same layout, 1 of 841 rather than a 360-golden chrome shift).
- sase-vp (bug, medium): 49d6c4188's clone hardening reached one file only;
  tests/agents_sync/git_sync_fixtures.py:17 still swallows git stderr under check=True
  and production _noninteractive_git_env still omits GIT_OPTIONAL_LOCKS; related
  sase-vf.
- sase-vq (bug, medium): six test files plant hardcoded PIDs (11111/22222) in workspace
  claims with no pid_is_thread stub, the same latent defect ca7692ee3 fixed for 33333;
  related sase-uw.
- sase-vr (bug, medium): nothing installs ruff/mypy from uv.lock, so a lock-faithful
  venv and CI disagree about the lint gate.

Nothing was declined. 9.5.3 #3 was recorded as its own bead rather than dropped even
though the parent plan had already called it a serial-pass flake, because no task bead
named the node and sase-ct's retirement forbids folding it into the umbrella.

`sase bead epic-symbols sase-um.9.5` reports no --epic-symbol entries.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-um.9.5.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-um.9.5.land/README.md) | [sase-um.9.5](sase-um.9.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e9d1a97`](https://github.com/sase-org/sase/commit/e9d1a973a0779c71425b24944d4065feaed230a5) | fix(memory): drop the installed version from generated task-type strands | [sase-um.9.5](sase-um.9.5.md) | 2026-08-29 14:36:35 EDT |
