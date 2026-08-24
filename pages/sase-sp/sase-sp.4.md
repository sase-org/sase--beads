# Bead: sase-sp.4 — A deliberate deferral escape hatch that does not fail the run

[Bead Pages](../README.md) / [sase-sp](README.md) / sase-sp.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ca](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ca.md) · **Assignee:** `sase-sp.4` · **Size:** medium
**Created:** 2026-08-24 09:19:09 EDT · **Closed:** 2026-08-24 13:20:49 EDT
**Plan:** [202608/finalizer\_commit\_authoring.md](https://github.com/sase-org/sase--plans/blob/main/202608/finalizer_commit_authoring.md)

## Description

escape: add `sase final defer`, honor `refusal: defer` in the controller, and report a deferred turn as a completed run with a dirty tree that the user is told about, instead of a FAILED run with a stranded workspace.

## Notes

[2026-08-24T17:20:22Z · sase-sp.4--3] PROPOSED FOLLOW-UP: chezmoi memory mirror is stale — `sase validate` fails on `init memory --check` because ~/.local/share/chezmoi/home/sase/memory/{sase.md,README.md} and the generated provider shims (AGENTS.md/CLAUDE.md/GEMINI.md/QWEN.md/OPENCODE.md) are out of sync with this repos canonical sase/memory/sase.md, and chezmoi has an unreferenced sase/memory/obsidian.md. The canonical file was last changed by already-merged commit f0982f28b (an ancestor of HEAD, predates sase-sp.4s diff), so this is pre-existing drift unrelated to this phase. Needs a memory-type task bead plus a user-approved `sase memory init` run; out of scope here since it touches the chezmoi repo and requires explicit memory-edit permission this phase worker does not have.

[2026-08-24T17:20:49Z · sase-sp.4--3] Verified: added sase final defer and refusal: defer handling in the controller so a deferred turn reports as a completed run with a disclosed dirty tree instead of a FAILED/stranded run (finalizers/commit*.py, controller*.py, main/final_handler.py, main/parser_final.py, axe/run_agent_runner_*.py, axe/runner_reporting.py, plus new/updated tests). Rebuilt sase_core_rs after the upstream 0.31.13 floor bump, reformatted 2 files for fmt-py-check, removed 4 stale --epic-symbol Justfile entries for closed beads sase-sp.3/sase-su.2, and privatized DeferredRepoOutcome to _DeferredRepoOutcome (commit_dispatch.py + its test) since symvision found no real external consumer. just check: fmt/lint/mypy/symvision/toobig and all SASE-validation sub-checks pass; the one remaining failure (SASE validation > init memory --check) is pre-existing chezmoi memory-mirror drift unrelated to this bead (canonical sase/memory/sase.md last touched by already-merged commit f0982f28b, an ancestor of HEAD) — recorded as a PROPOSED FOLLOW-UP note rather than fixed here, since it requires editing the chezmoi repo plus user-approved sase memory init. sase bead epic-symbols sase-sp.4 shows no leftover entries.

## Dependencies

- **Depends on:** [sase-sp.3](sase-sp.3.md) ✓ · ⧖ 2026-08-24
- **Blocks:** [sase-sp.6](sase-sp.6.md) ✓ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sp.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-sp.4.md) | [sase-sp.4](sase-sp.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2b046b1`](https://github.com/sase-org/sase/commit/2b046b17460b2e86e24a157c1ba54a97549fd06a) | feat(finalizers): defer commit on refusal instead of failing the turn | [sase-sp.4](sase-sp.4.md) | 2026-08-24 13:22:05 EDT |
