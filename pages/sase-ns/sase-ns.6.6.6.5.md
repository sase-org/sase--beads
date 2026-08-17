# Bead: sase-ns.6.6.6.5 — Stop a stale global sase build from silently answering workspace memory-drift checks

[Bead Pages](../README.md) / [sase-ns.6.6.6](sase-ns.6.6.6.md) / sase-ns.6.6.6.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ns.6.6.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.6.6.land.md) · **Assignee:** `sase-ns.6.6.6.5` · **Size:** medium
**Created:** 2026-08-17 05:54:40 EDT · **Closed:** 2026-08-17 06:15:08 EDT
**Plan:** [202608/backlog\_top\_five\_gates\_and\_flakes.md](https://github.com/sase-org/sase--plans/blob/main/202608/backlog_top_five_gates_and_flakes.md)

## Description

saseinstall: make it impossible for a bare `sase` resolved from a separate uv tool checkout to silently answer a memory-drift check about this workspace, which is the mechanism behind five phantom-drift reproductions across six agent shells.

## Notes

[2026-08-17T10:14:27Z · sase-ns.6.6.6.5] TASK NEEDS APPROVAL: two optional complements to the landed in-repo staleness warning are outside this phase's authority and were deliberately not done. (1) Keeping /home/bryan/.local/bin/sase's uv tool install synced with master (e.g. a chezmoi apply hook or a periodic `uv tool install --reinstall -e ~/projects/github/sase-org/sase sase`) is a change to the user's machine / the chezmoi repo. (2) Wording agent instructions (CLAUDE.md/AGENTS.md/sase/memory/*.md) to always name the venv-pinned invocation ('.venv/bin/sase memory init --check' instead of a bare 'sase ...') requires explicit user permission to edit those files. Neither is required for this phase's fix to work: the landed warning is dynamic (compares sys.executable against the invoked project's own .venv/bin/python), so once any future refresh of the global build picks up this commit, it will self-report when a workspace has its own pinned build it isn't using -- no wording change or reinstall is needed for the warning itself to start firing, only for the global build to carry the code that emits it sooner.

[2026-08-17T10:14:49Z · sase-ns.6.6.6.5] Landed option (a)'s in-repo half: sase memory init / sase init memory (both --check and apply) now detect when the running python differs from the invoked project's own <project_root>/.venv/bin/python while that project also carries its own .venv/bin/sase (src/sase/main/init_memory/staleness.py:workspace_pinned_sase_mismatch_warning). When it fires, the check surfaces a Warnings: line naming the foreign interpreter and the exact pinned command to re-run (e.g. '<project>/.venv/bin/sase memory init --check', or 'just check'), without failing the check (InitPlan.warnings, already rendered/propagated by the existing init-onboarding and sase-validate warning plumbing). No warning on the golden path: verified 'just check' runs sase validate's init-memory --check through this workspace's own venv-pinned python with zero warnings. Option (b) (rewording agent instructions) and the durable global-tool-sync route were deferred with a TASK NEEDS APPROVAL note, per this bead's approval boundaries. Verified: new unit tests in tests/main/test_init_memory_staleness.py pin the warning message and both trigger/no-trigger conditions (5 tests); just install && just check are green (just check: 12/12 lint gates + SASE validation + committed plans + scoped tests, selected 142/2821 files, all passed).

[2026-08-17T10:15:08Z · sase-ns.6.6.6.5] Closed: landed the in-repo staleness warning (src/sase/main/init_memory/staleness.py + init_memory_handler.py wiring) so sase memory init/sase init memory (check and apply) detect a foreign sase build answering a workspace's own memory check and name the workspace-pinned fix. Covered by tests/main/test_init_memory_staleness.py (5 tests, message + both trigger/no-trigger conditions pinned). just install && just check verified green (all 12 lint gates, SASE validation, committed-plans check, and the diff-scoped test lane all passed). Deferred the chezmoi/global-reinstall and agent-instruction-wording complements via a TASK NEEDS APPROVAL note, per this bead's approval boundaries.

[2026-08-17T10:15:45Z · sase-ns.6.6.6.5] Verified: just install && just check are green (ruff, mypy, sase validate, committed-plans check, and diff-scoped tests all pass) for src/sase/main/init_memory/staleness.py, src/sase/main/init_memory_handler.py, and tests/main/test_init_memory_staleness.py.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ns.6.6.6.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ns.6.6.6.5/README.md) | [sase-ns.6.6.6.5](sase-ns.6.6.6.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7f3710e`](https://github.com/sase-org/sase/commit/7f3710e3f61a743caa1b6915959b2c80f2b99a22) | fix(memory): warn when a foreign sase build answers a workspace memory-drift check | [sase-ns.6.6.6.5](sase-ns.6.6.6.5.md) | 2026-08-17 06:16:24 EDT |
