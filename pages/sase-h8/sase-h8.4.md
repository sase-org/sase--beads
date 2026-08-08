# Bead: sase-h8.4 — Fix the off-pump settle-gap family

[Bead Pages](../README.md) / [sase-h8](README.md) / sase-h8.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.v5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.v5/README.md) · **Assignee:** `sase-h8.4` · **Size:** medium
**Created:** 2026-08-07 18:05:27 EDT · **Closed:** 2026-08-07 22:27:55 EDT
**Plan:** [202608/parallel\_suite\_flake\_class.md](https://github.com/sase-org/sase--plans/blob/main/202608/parallel_suite_flake_class.md)

## Description

pump: fix every triaged node whose failure is a single `pause()` standing in for work that runs off the Textual message pump, by waiting on the observable end state with the shared bounded-wait primitive.

## Notes

[2026-08-08T01:47:46Z · sase-h8.3] TRIAGE (from sase-h8.3): the phase-triage table is research:202608/parallel_suite_flake_triage.md, committed to the research sidecar. It measures family membership at master 47b9f0017 and corrects the epic plan in several places, including the family your phase owns. Read it before starting; see also the sase-h8.3 bead notes.

[2026-08-08T02:26:34Z · sase-h8.4] PROPOSED FOLLOW-UP: tests/doctor/test_checks_providers.py::test_setup_hint_points_script_installs_at_the_install_subcommand fails deterministically on clean master 050c9477c (git stash verified) — the Muse-provider setup-hint dict mismatch introduced by the muse-provider work; unrelated to sase-h8 and not in the sase-h8.3 triage table. It joins the six ff0b765a4 gate nodes in blocking a clean `just check` for every agent.

[2026-08-08T02:27:12Z · sase-h8.4] PROPOSED FOLLOW-UP: F1 is falsified for the two `test_prompt_bar_xprompt_selector_requests.py::test_vcs_tag_*` nodes the triage table assigned to `pump` — `on_prompt_input_bar_snippet_requested` is fully synchronous (no pilot, no message pump, no worker/thread/to_thread anywhere in the project-local lookup), so there is no off-pump boundary to inject a delay at. The real mechanism is a swallowed exception: the lookup block ended in `except Exception: pass`, so any raise (stale `sase_core_rs` binding through `resolve_project_config_read_path` -> `resolve_project_layout` is the leading candidate, and is the same root cause the table records for the F4 node `test_malformed_header_block_leaves_authored_metadata_visible`) is indistinguishable from "this project has no xprompts". That matches the store exactly: all 3 recorded occurrences failed as a pair, and 20260807T010908Z-e3bfbbcbfe21 has these two as its ONLY two failures. Reassign to F6/F4, not F1. Instrumentation has landed here (see the bead notes); the residual work is confirming the raiser once it recurs.

[2026-08-08T02:27:55Z · sase-h8.4] Fixed the F1 off-pump settle-gap nodes the sase-h8.3 triage table assigns to `pump`, each shown failing before and passing after under an injected delay at the identified boundary (the plan's acceptance clause), not merely on a clean run.

BOUNDARY 1 — clipboard delivery (tests/ace/tui/modals/test_artifact_files_modal_copy.py). ArtifactFileCopyingMixin routes every copy through schedule_copy_delivery -> spawn_pump_free_task -> deliver_copy, which awaits asyncio.to_thread twice, so pause() returns while the copy is still on a worker thread. Replaced the file's bare pause()/blind-drain idiom with one _wait_for_copy_delivery(pilot, predicate) helper built on the sase-h8.2 primitive (sase.ace.testing.wait.wait_for), which waits on a transition the delivery causes (a copied value or a notification absent at keypress) and then drains _pump_free_clipboard_tasks so notification assertions see the end state; the docstring names the boundary. Also serialized the two multi-copy tests (test_artifact_file_modal_copy_anchors_pdf_markdown_source_path and the two %-palette loops) so the asserted copy ORDER is not a race between concurrently scheduled delivery tasks — a second latent flake in the same file. Falsified with a 0.4s asyncio.sleep injected at the head of deliver_copy: master 9 failed / 4 passed (including BOTH triaged nodes, test_artifact_file_modal_Y_anchors_path_recovered_from_agent_meta_json and test_artifact_file_modal_copy_anchors_pdf_markdown_source_path, plus 7 siblings sharing the boundary); fixed file 13 passed under the identical delay.

BOUNDARY 2 — path-inventory thread worker (tests/ace/tui/widgets/test_prompt_at_prefix_completion.py). _schedule_prompt_path_inventory_load runs the listing via run_worker(..., thread=True). Retired the two ad-hoc `for _ in range(100): pause(0.01)` loops onto wait_for and added the missing waits to test_at_prefix_directory_drilldown. Per the plan's "watch out for", the first predicates I chose were unsound and I caught them under the delay: bool(candidates) is true immediately because a pending load shows an empty-name placeholder, and text == "@~/alpha/" lands before the menu closes. Final predicates wait on real listing entries ("alpha" / "foo.py" by name) and on text AND not active. Falsified with time.sleep(0.4) in the worker task: master 1 failed (test_at_prefix_directory_drilldown) / 2 passed; fixed file 3 passed under the identical delay.

REFERENCE SHAPE — test_agent_bulk_kill_edit.py::test_bulk_waiting_agents_mount_forced_artifact_prompts confirmed, not re-fixed: 11 passed with a 0.4s sleep injected into prepare_prompt at its named boundary (schedule_relaunch_prompt_resolution, _entry_relaunch.py). bde727ecc holds.

F1 FALSIFIED for the two test_vcs_tag_* selector nodes — see the PROPOSED FOLLOW-UP note. That call path is fully synchronous, so there is no boundary to inject at; the mechanism is a swallowed exception, and the store corroborates it (all 3 occurrences are pairs; one run has these two as its only failures). Landed instrumentation instead of a bogus wait: the bare `except Exception: pass` in _prompt_bar_requests.py now log.exception()s, and both tests assert via caplog that nothing was swallowed, failing with the formatted traceback. Verified the guard by injecting `raise OSError` into the lookup — both tests then fail together naming the cause, reproducing the store's exact pairing signature.

VERIFIED: contention harness (sase-h8.1), 6 repeats, 26 workers pinned to 2 CPUs, over all four files (44 items): 6/6 green, 0 nodes failed in any repeat, 324.2s. Measured on CPUs 2,3 because a sibling phase agent (sase_19) was soaking CPUs 0,1 at the same time; an earlier run on 0,1 was discarded as self-contaminated (I was mid-edit with an injected raise during its repeat 2). just lint fully green (ruff, mypy 2843 files, symvision, toobig, changelog, pyscripts). just check's scoped lane escalated to the full suite: 27439 passed, 7 failed — all 7 reproduce on clean master via git stash (the six known ff0b765a4 gate nodes already filed on sase-h8.3, plus one previously unfiled doctor node filed as a PROPOSED FOLLOW-UP here).

[2026-08-08T02:28:56Z · sase-h8.4] F1 flake fixes verified: injected-delay falsification for clipboard delivery + at-prefix drilldown boundaries; F1 falsified for the two vcs_tag selector nodes (swallowed exception, now logged and asserted via caplog). Contention harness 6/6 green (44 nodes, CPUs 2,3). just lint green; scoped lane's 7 failures reproduce on clean master.

## Dependencies

- **Depends on:** [sase-h8.2](sase-h8.2.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-h8.3](sase-h8.3.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-h8.8](sase-h8.8.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h8.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.4/README.md) | [sase-h8.4](sase-h8.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4dc3231`](https://github.com/sase-org/sase/commit/4dc323117f73481c24798e3aa0f2487dbfa4dfc8) | test(flakes): close the off-pump settle gaps in three ACE test files | [sase-h8.4](sase-h8.4.md) | 2026-08-07 22:29:37 EDT |
