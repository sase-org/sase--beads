# Bead: sase-1lj.1 — Projection header, neutral contract wording, parity repo check, and a CI drift gate

[Bead Pages](../README.md) / [sase-1lj](README.md) / sase-1lj.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.10r](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.10r.md) · **Assignee:** `sase-1lj.1` · **Size:** medium
**Created:** 2026-10-16 15:15:55 EDT · **Closed:** 2026-10-16 16:06:14 EDT
**Plan:** [202610/e4\_readable\_agents\_md.md](https://github.com/sase-org/sase--plans/blob/main/202610/e4_readable_agents_md.md)

## Description

readable-projection: add a short project-only header to the generated AGENTS.md, make the packaged contract wording true for files and bundles, make the parity repository check run on numbered headings, and stop CI regenerating committed instruction files before it checks them.

## Notes

[2026-10-16T19:34:10Z · sase-1lj.1] CI local proof (readable-projection drift gate): (1) with HOME=mktemp temp dir, ran the workflow step commands from /tmp/fake-runner-temp using absolute .venv paths: `sase init memory --no-commit` planned only the home root (no project memory target line, exit 0) and `sase skill init --force` wrote 133 skills under the temp HOME (exit 0); `git status --porcelain` in the workspace stayed at 23 dirty files (my own edits) throughout. (2) appended a line to AGENTS.md: `sase init memory --check` exited 1 naming `overwrite AGENTS.md managed AGENTS.md`, and tests/main/test_init_memory_committed_drift.py::test_repo_project_memory_notes_match_generator_output FAILED. (3) restored AGENTS.md byte-identical (cmp clean) and --check exits 0 again.

[2026-10-16T20:06:14Z · sase-1lj.1] readable-projection done and verified: (1) project-only 4-line header via optional projection_note template var (PROJECT_PROJECTION_NOTE), threaded through plan_amd_memory_sync/memory_root_context by include_project_memory; home/chezmoi excluded; test proves no bundle contains it. (2) neutral contract wording in memory-sase.template.md; sase memory init regen applied, --check exits 0, CLAUDE.md byte-identical. (3) parity repo regex accepts numbered/deeper headings with any-heading section end; numbered-fixture tests added; render -p exits 0. (4) CI home-init steps in ci.yml + master-gate.yml run outside checkout (working-directory runner.temp, absolute paths); workflow regression test added; local proof recorded in bead note (outside init leaves tree untouched; appended-line drift fails --check and the drift test; restored). (5) memory-initialization.md docs updated in place. Verify: sase tool run check 78ad3eba — all lint gates green (ruff, mypy, symvision, docs, validation, committed plans); scoped lane 56138 passed; 2 agent-docs failures were stale shape assertions updated to the header contract; 3 other failures pass in isolation (host-load flakes). epic-symbols clean. just fmt clean.

## Dependencies

- **Blocks:** [sase-1lj.2](sase-1lj.2.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lj.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lj.1/README.md) | [sase-1lj.1](sase-1lj.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`97825ee`](https://github.com/sase-org/sase/commit/97825eee1d2c9d2db63ab9427d0fe153145a8bd0) | feat(instructions): readable AGENTS.md projection with header, parity check, and CI drift gate | [sase-1lj.1](sase-1lj.1.md) | 2026-10-16 16:07:53 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1lj.1][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lj.1/README.md

<!-- sase:referenced-by:end -->
