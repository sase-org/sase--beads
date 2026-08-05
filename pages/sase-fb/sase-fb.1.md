# Bead: sase-fb.1 — Make every bead-store mutation publication-verified before the CLI reports success

[Bead Pages](../README.md) / [sase-fb](README.md) / sase-fb.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.t9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.t9/README.md) · **Assignee:** `sase-fb.1` · **Size:** medium
**Created:** 2026-08-05 15:45:51 EDT · **Closed:** 2026-08-05 17:16:07 EDT
**Plan:** [202608/bead\_close\_publication\_loss.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_close_publication_loss.md)

## Description

publish: after a bead mutation commits, verify the commit actually reached the canonical remote; force a synchronous publish when it did not, and fail the command loudly when it still cannot publish, instead of returning 0 on a workspace-local-only write.

## Notes

[2026-08-05T21:14:40Z · sase-fb.1] PROPOSED FOLLOW-UP: tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout is load-flaky — it passes alone (3.6s) and on an idle full-suite run, but fails when several agents run `just check` concurrently; its 12s lock timeout and 30s process-join budget are wall-clock bound rather than load-relative.

[2026-08-05T21:15:29Z · sase-fb.1] PROPOSED FOLLOW-UP: tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough is also load-flaky — it failed only in a `just check` run that overlapped other agents' full-suite runs and passes on rerun; likely the same wall-clock-bound timing assumption.

[2026-08-05T21:16:07Z · sase-fb.1] Implemented publication-verified bead mutations (epic sase-fb, phase publish).

WHAT CHANGED
- src/sase/bead/_sync_diagnostics.py: new BeadPublicationStatus + verify_bead_store_published() built on unpushed_bead_commit_count(), plus bead_publication_failure_lines() for the operator diagnostic and is_in_tree_beads_dir() (moved here so sync.py delegates). No git root, no tracking upstream, or an in-tree layout => applicable=False, i.e. published (never a failure).
- src/sase/bead/sync.py: exports verify_bead_store_published / bead_publication_failure_lines / BeadPublicationStatus and adds MUTATION_PUBLICATION_WORKER_LOCK_WAIT_SECONDS=30 (CLI mutations wait out a busy sync worker, but not the 120s launch-checkpoint budget).
- src/sase/bead/cli_common.py: new BeadPublicationError; ensure_bead_mutation_published() verifies after the configured push policy has run, forces one synchronous push_bead_work_launch() against the store that actually holds the commit, re-verifies, and on remaining unpublished bead commits prints the diagnostic to stderr and raises. bead_store_mutation() calls it after _push_committed_bead_store() (skipped for --no-push, in-tree, and read-only stores). Verification failures of the check itself degrade to a log warning, never a false failure.
- src/sase/main/bead_fast_path.py: _apply_mutation_side_effects() now returns whether the mutation is published and runs the SAME helper, so both lanes are verified identically; execute_bead_cli() suppresses the Rust success stdout and returns exit 1 when publication failed.
- src/sase/main/entry.py: bead dispatch catches BeadPublicationError and exits 1 (diagnostic already printed), so handlers never reach their success print. That is how '✓ Closed' is prevented for an unpublished close — _print_close_results runs after the mutation context manager, which now raises first.

VERIFIED
- New tests/test_bead/test_bead_publication_verification.py (7 tests) reproduces the exact scenario: a sidecar-style bead clone at <workspace>/sase/repos/beads with an upstream, a FRESH integration marker (TTL gate suppresses the background refresh), _push_committed_bead_store stubbed out to model the enqueue-to-the-wrong-checkout branch, then a real 'sase bead close'. Asserts the close commit reaches the bare remote. Companion test with an unreachable remote asserts BeadPublicationError, no '✓ Closed' on stdout, and stderr naming 'unpublished bead commit(s): 1', the store path, and 'git -C <repo> push'; the close remains recorded locally so it can be republished. Two fast-path tests cover both outcomes, plus not-applicable cases (no upstream, in-tree) and a no-remote close that stays silent and prints ✓ Closed.
- Confirmed these 4 behavioral tests FAIL against the pre-change behavior (enforcement stubbed out) and pass with it.
- Updated tests/main/test_bead_fast_path_mutations.py for the new bool return of _apply_mutation_side_effects.
- just check: lint/format/mypy/symvision clean; a full 'just test' run on an idle machine passed 25804 tests. A later run overlapping other agents' concurrent full-suite runs flaked on two wall-clock-bound timing tests (test_concurrent_bead_mutations_wait_past_the_old_lock_timeout, test_inline_metadata_search_commit_repeat_q_and_passthrough); both pass standalone and neither touches this change's code paths. Recorded as PROPOSED FOLLOW-UP notes on this bead.

NOT DONE HERE (by design)
- Root cause 1 (enqueue drains the primary checkout) is left to epic sase-fa as the plan directs; this verification sits above push_sdd_store_after_commit and works whichever way that resolves.
- Phases evict and finalize are untouched.

## Dependencies

- **Blocks:** [sase-fb.3](sase-fb.3.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fb.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fb.1/README.md) | [sase-fb.1](sase-fb.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`99eedf7`](https://github.com/sase-org/sase/commit/99eedf74912088e92a3e8b3cbf0786bf83b85633) | fix(bead): verify bead-store mutations are published before reporting success | [sase-fb.1](sase-fb.1.md) | 2026-08-05 17:17:36 EDT |
