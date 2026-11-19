# Bead: sase-1tz.2.1.6 — Keep deferred prompt sources alive and add an audited terminal state

[Bead Pages](../README.md) / [sase-1tz.2.1](sase-1tz.2.1.md) / sase-1tz.2.1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.md) · **Assignee:** `sase-1tz.2.1.6` · **Size:** medium
**Created:** 2026-11-19 11:13:27 EST · **Closed:** 2026-11-19 17:47:58 EST
**Plan:** [202611/noise\_publication\_digests\_tui\_stalls.md](https://github.com/sase-org/sase--plans/blob/main/202611/noise_publication_digests_tui_stalls.md)

## Description

prompt_terminal: find why deferred prompt sources vanish and close each gap so durable obligations keep their bytes. Add a sase-core terminal outcome for genuinely unreconstructable archives. It stops retries, releases pool protection and any tied workspace hold, and leaves an audit record. It never counts as success.

## Notes

[2026-11-19T22:46:58Z · sase-1tz.2.1.6] MEASUREMENT (prompt_terminal, read-only, 2026-11-19): athena has 369 quarantined prompt-archive rows (all attempts=3, unresolved missing-local-source), 13 terminal rows (none unrecoverable; all hood/completion terminals), 732 digest files, 32 missing-local-source digest lines in 7d. apollo has 263 quarantined prompt-archive rows and 312 terminal rows. No terminal_obligations.jsonl yet (feature uninstalled; install is human-only). After-install: wc -l ~/.sase/agent_publication/terminal_obligations.jsonl plus the pub_doctor doctor commands.

[2026-11-19T22:47:09Z · sase-1tz.2.1.6] PROPOSED FOLLOW-UP: land the sase-core half of prompt_terminal (PROMPT_STATUS_UNRECOVERABLE + past_grace_period/attempts_exhausted wire fields in agent_publication_recovery, with golden tests) as its own stitch, then ratchet sase-core-revision.txt past it (just ratchet-core-revision). The sase Python side is backward-compatible with the old core (new wire fields are optional; old cores never report unrecoverable), but terminal transitions stay dormant until the pin moves and sase-core-rs is reinstalled. sase-core working tree currently holds the uncommitted change; agents never commit.

[2026-11-19T22:47:15Z · sase-1tz.2.1.6] PROPOSED FOLLOW-UP: pre-existing check failures reproduce identically on the clean base tree (verified via git stash): test_scanner_timeout_unwinds_drain_and_leaves_request_queued and 10 siblings in test_commit_publication_drain_accounting.py fail when git_lock_facade first-imports under the blanket require_rust_binding patch (lazy-import isolation bug), test_cleanup_after_success_does_not_resurrect fails the same way, and symvision flags LaunchPromptContext (src/sase/axe/run_agent_runner_setup_prompt.py, landed in 1910892d92, untouched by this phase). No task bead found tracking these.

[2026-11-19T22:47:26Z · sase-1tz.2.1.6] FINDINGS (prompt_terminal audit): (1) toobig-* rows confirm the run-never-had-a-prompt-file cause; stale-row-names-wrong-dir fixed by probing both artifacts_dir and the run source_label in prepare and classification (regression tests). Pool GC already excluded non-terminal revisions; verified terminal revisions become collectible again by test. (2) No workspace hold is tied to an unrestorable obligation: missing sources create no dirty paths, and settle keeps only Q&A snapshot paths, so holds name scratch (pub_cleanup cause); terminal release is via pool protection + outbox retirement, no settle change needed. (3) toobig-style rows with no prompt file in the published snapshot keep the NOT_APPLICABLE path and are never terminal.

[2026-11-19T22:47:58Z · sase-1tz.2.1.6] Terminal prompt_archive_unrecoverable implemented and verified. sase-core: new unrecoverable classifier outcome (past grace + attempts exhausted + no local source + no sidecar copy) with 3 golden tests, 70/70 recovery tests green, clippy/fmt clean. sase: restore probes both artifacts_dir and run source_label (gap fix), terminal failures retire over two passes with deterministic terminal_reason, audit record to terminal_obligations.jsonl, excluded from retry-quarantined revival, pool protection released; 8 new terminal tests + sync-level retire/audit test + 2 facade tests green; hood-sync/cli docs updated; Justfile carries 2 epic-symbol rows re-keyed to open sase-1tz.2.1.7. Remaining for land: sase-core stitch commit + pin ratchet (recorded as follow-up). Pre-existing failures recorded as follow-ups: drain_accounting isolation bug, test_cleanup_after_success, LaunchPromptContext symvision (all reproduce on clean tree).

## Dependencies

- **Depends on:** [sase-1tz.2.1.4](sase-1tz.2.1.4.md) ✓ · ⧖ 2026-11-19
- **Blocks:** [sase-1tz.2.1.7](sase-1tz.2.1.7.md) ◐ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.6/README.md) | [sase-1tz.2.1.6](sase-1tz.2.1.6.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@6eedf0a`](https://github.com/sase-org/sase-core/commit/6eedf0a6544cfd9da279a29cd42c245d70404a04) | feat(agent-publication-recovery): add terminal unrecoverable deferred-prompt outcome | [sase-1tz.2.1.6](sase-1tz.2.1.6.md) | 2026-11-19 17:49:43 EST |
| sase | [`3d3d0f5`](https://github.com/sase-org/sase/commit/3d3d0f583d0790aa9ebab3af08d4fe2f32cb9904) | feat(agents-sync): retire terminal deferred prompts as unrecoverable | [sase-1tz.2.1.6](sase-1tz.2.1.6.md) | 2026-11-19 17:51:28 EST |
