# Bead: sase-1ra.5 — False-red batch: cold keymap test, MRU provider pruning, AF\_UNIX path length (sase-1qu, sase-172, sase-1i6)

[Bead Pages](../README.md) / [sase-1ra](README.md) / sase-1ra.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.18d](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.18d.md) · **Assignee:** `sase-1ra.5` · **Size:** medium
**Created:** 2026-11-04 17:59:13 EST · **Closed:** 2026-11-04 18:56:29 EST
**Plan:** [202611/next\_ten\_task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202611/next_ten_task_beads.md)

## Description

false_red: fix three tests that fail deterministically when run cold or alone, repairing product behavior where the root cause is a product bug (sase-1qu, sase-172, sase-1i6).

## Notes

[2026-11-04T23:55:48Z · sase-1ra.5] false_red results (athena, base 0cc9fad474): all three cold nodes reproduced before the fix and pass after, alone in a fresh process and inside their modules. sase-1qu: test_update_shortcut_dispatch_performs_no_disk_or_subprocess_work failed cold because _ActionApp init builds the keymap registry after Path.read_text was patched; the app always warms defaults at startup (_state_init_late registry build), so the fix warms load_keymap_registry({}) before installing the patches and adds test_keymap_registry_load_warms_defaults_before_first_keypress pinning the warm-before-input guarantee. Module: 24 passed. sase-172: test_load_launchable_prunes_provider_mismatched_prefix dropped genuine #git:otherproj because the mock detect_workflow_type matched "gh_sase-org__sase" as a full-path substring and TMPDIR itself contains that key; product patterns (#git/#gh) are disjoint so no product bug — fixed the mock to match on the project dir name and added a github-first plugin-order variant. File: 11 passed. sase-1i6: both IPC nodes died with AF_UNIX path too long under the long agent TMPDIR; both tests now bind under tempfile.mkdtemp(dir="/tmp") via _short_socket_dir with teardown. Production resolved_socket_path is ~/.sase/run/<host>/sase-federation-worker.sock (~40 chars), well under the limit — no follow-up needed. File: 7 passed. Scoped lane (92 files): 1166 passed, 1 failed — the single failure is pre-existing on the clean base (see PROPOSED FOLLOW-UP). Task files: tests/ace/tui/test_log_panel_keymap.py, tests/test_vcs_macro_mru_pruning.py, tests/test_dispatch_federation_ipc.py.

[2026-11-04T23:55:57Z · sase-1ra.5] TASK RESOLVED: sase-1qu — cold keymap dispatch test warmed before patching; warm-before-input guarantee pinned; node passes alone and module (24) passes.

[2026-11-04T23:56:08Z · sase-1ra.5] TASK RESOLVED: sase-172 — provider-mismatch pruning was a TMPDIR-substring mock artifact, not a product bug (#git/#gh patterns disjoint); mock anchored on project dir name, github-first variant added; node passes alone and file (11) passes.

[2026-11-04T23:56:14Z · sase-1ra.5] TASK RESOLVED: sase-1i6 — IPC sockets now bind under a short /tmp dir with teardown; both nodes pass alone and module (7) passes; production socket path (~40 chars) is well under the 108-byte limit.

[2026-11-04T23:56:19Z · sase-1ra.5] PROPOSED FOLLOW-UP: tests/test_macro_terminology.py::test_macro_string_literals_avoid_xprompt_terms fails on the clean base tree too (verified via git stash at 0cc9fad474) — findings are raw_xprompt.md strings in tests/agents_sync/test_deferred_prompt_archive/, unrelated to the false_red batch.

[2026-11-04T23:56:29Z · sase-1ra.5] false_red done on athena at base 0cc9fad474: sase-1qu (warm-before-patch + guarantee pin; 24-module pass), sase-172 (dir-anchored mock + github-first variant; 11-file pass), sase-1i6 (short /tmp socket dir; 7-module pass). Each node passes alone in a fresh process and inside its module. Scoped lane: 1166 passed, 1 pre-existing clean-base failure recorded as PROPOSED FOLLOW-UP. No epic symbols.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ra.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ra.5/README.md) | [sase-1ra.5](sase-1ra.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`45bcf6f`](https://github.com/sase-org/sase/commit/45bcf6fe398e1a29e4d6985d820f1ccc9d9903d0) | test(false-red): fix keymap warmup, vcs mru mock, ipc socket path | [sase-1ra.5](sase-1ra.5.md) | 2026-11-04 18:58:37 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ra.5][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ra.5/README.md

<!-- sase:referenced-by:end -->
