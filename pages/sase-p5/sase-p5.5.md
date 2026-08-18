# Bead: sase-p5.5 — Actionable diagnostics and regression coverage

[Bead Pages](../README.md) / [sase-p5](README.md) / sase-p5.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05d](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05d.md) · **Assignee:** `sase-p5.5` · **Size:** small
**Created:** 2026-08-17 18:55:32 EDT · **Closed:** 2026-08-18 07:15:27 EDT
**Plan:** [202608/commit\_finalizer\_attribution.md](https://github.com/sase-org/sase--plans/blob/main/202608/commit_finalizer_attribution.md)

## Description

hardening: replace the guard's dead-end failure text with an operator-actionable diagnostic, add end-to-end regressions reproducing both failure clusters, and refresh the affected docs.

## Notes

[2026-08-18T11:14:45Z · sase-p5.5] PROPOSED FOLLOW-UP: just fmt-py-check fails on src/sase/amd/_memory.py:398-400 with the installed ruff 0.16.2 (collapses two adjacent string literals onto one line); confirmed pre-existing on clean master via git stash, unrelated to sase-p5.5. Needs someone to run just fmt (or apply the one-line reformat) and commit it so just check is green for every agent again.

[2026-08-18T11:15:00Z · sase-p5.5] PROPOSED FOLLOW-UP: just lint symvision reports 2 unused public symbols (long_memory_entry_path, normalize_long_memory_description_lines in src/sase/amd/_agents_doc.py) unrelated to sase-p5.5 — either make them private, delete them, or add --epic-symbol entries for whichever bead owns that in-flight work.

[2026-08-18T11:15:27Z · sase-p5.5] Improved discarded-work guard diagnostics: discarded_dirty_work_message now names the repo, HEAD before/after, the newly reachable commits found (sha/subject/attributed agent), whether the run-owned ledger was consulted, and a concrete next step, distinguishing head_not_advanced from missing_agent_provenance (src/sase/llm_provider/commit_finalizer_git_progress.py). Added tests/llm_provider/test_commit_finalizer_resume_provenance_e2e.py with 3 end-to-end regressions against real git + the real guard: Cluster A (a resumed commit's footer dropped during conflict resolution is restamped by the real _restamp_missing_footer_tags and then recognized as attributable), Cluster B (a shared external/sdd clone that goes clean under a concurrent agent's commit is a race, not a discard), and a genuine discard (reset dirty work with no commit anywhere still fails with reason=head_not_advanced). Extended test_foreign_agent_commit_does_not_satisfy_clean_after_pass with assertions on the new diagnostic fields. Refreshed docs/commit_workflows.md: resume-flow step 4 now documents the footer restamp, and a new 'Discarded-Work Guard' section documents the three attribution signals, the two failure reasons, the shared-clone exemption and its commit_finalizer_shared_clone_exempt flag, and the improved message contents. Verified: just fmt (both python and markdown gates pass for all touched files), just lint ruff/mypy/keep-sorted all pass, just test-scoped (669 passed). just fmt-py-check and just lint symvision both fail, but confirmed via git stash both failures are pre-existing on clean master (unrelated ruff-format drift in src/sase/amd/_memory.py and unrelated unused symbols in src/sase/amd/_agents_doc.py) and recorded as PROPOSED FOLLOW-UP notes on this bead. sase bead epic-symbols sase-p5.5 confirmed empty before close.

[2026-08-18T11:16:10Z · sase-p5.5] already closed in prior session; re-verifying publish state

## Dependencies

- **Depends on:** [sase-p5.4](sase-p5.4.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p5.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p5.5/README.md) | [sase-p5.5](sase-p5.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`af951d1`](https://github.com/sase-org/sase/commit/af951d1f943a999c565f36fdc0301c2c576dd02e) | fix(llm\_provider): make the discarded-work guard's failure diagnostic actionable | [sase-p5.5](sase-p5.5.md) | 2026-08-18 07:17:02 EDT |
