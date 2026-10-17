# Bead: sase-1lj.2 — Retire the GEMINI.md, QWEN.md, and OPENCODE.md copies at project roots

[Bead Pages](../README.md) / [sase-1lj](README.md) / sase-1lj.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.10r](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.10r.md) · **Assignee:** `sase-1lj.2` · **Size:** medium
**Created:** 2026-10-16 15:15:56 EDT · **Closed:** 2026-10-16 17:53:03 EDT
**Plan:** [202610/e4\_readable\_agents\_md.md](https://github.com/sase-org/sase--plans/blob/main/202610/e4_readable_agents_md.md)

## Description

shim-retirement: canary-probe agy, Qwen, and OpenCode on AGENTS.md alone, shrink project and nested provider copies to CLAUDE.md with safe retirement in sase memory init, update every validator, inventory, history, snapshot, and Rust content-layout consumer (with the sase-core pin move), and delete the twelve copies.

## Notes

[2026-10-16T20:53:51Z · sase-1lj.2] E4 PROBES: In disposable git canaries, agy 1.4.0 read AGENTS.md alone and returned AGENTS-CANARY-RED; with both AGENTS.md and GEMINI.md it returned both distinct markers. Qwen 0.25.2 is configured for qwen3.6-plus but BAILIAN_TOKEN_PLAN_API_KEY was absent, so no authenticated call was made; OpenCode 1.19.3 reported zero credentials, so no call was made. Retained the version-pinned CLI evidence for Qwen and OpenCode.

[2026-10-16T20:54:01Z · sase-1lj.2] PROPOSED FOLLOW-UP: Probe an explicit instruction channel for agy — D4 keeps GEMINI.md in the home set until an explicit channel is established; test whether the channel can make the home copy redundant.

[2026-10-16T21:52:39Z · sase-1lj.2] PROPOSED FOLLOW-UP: Fix the project-label audit violation in repair_archived_prompt_path — the unchanged base tree fails test_project_labels_never_derive_from_paths on Path(project_file).parent.name; clean-base run reproduced it, and no matching bead was found.

[2026-10-16T21:52:44Z · sase-1lj.2] PROPOSED FOLLOW-UP: Extend sase-1kr stale-index-lock investigation to revert_agent_git.run_git — test_revert_git_runner_recovers_stale_index_lock failed only in the loaded scoped check, then passed isolated on current and clean-base trees; both callers use run_with_git_lock_retry.

[2026-10-16T21:53:03Z · sase-1lj.2] Verified the provider canaries; project initialization safely retired 12 obsolete copies and plans zero project changes afterward; both Rust core and primary just check runs completed, with primary failures limited to the documented clean-base project-label violation and stale-lock flake; the phase-related targeted tests passed (19), and visual maintenance passed (10) updating only the two expected instruction-card goldens. Epic-symbol audit found no entries.

[2026-10-16T22:03:43Z · sase-1lj.2] PROPOSED FOLLOW-UP: Implement shim-retirement primary-side steps 2-4 and 6 — split amd/constants.py into project/nested, home/chezmoi, and retired lists, fix the agy GEMINI.md comment, route provider_shim_specs and agent_doc_shim_plans by root kind, add safe delete-identical retirement to sase memory init, update inventory/history/launch-evidence/guard/audit consumers, and update the shim-set test suites and fixtures

[2026-10-16T22:03:53Z · sase-1lj.2] PROPOSED FOLLOW-UP: Apply shim-retirement steps 7-8 plus sase-core pin move — run sase memory init to delete the 12 retired copies (count to 8), update the six docs shim lists, move sase-core-revision.txt past the content_layout.rs commit, update tests/test_content_layout.py, and pass tools/check_sase_core_rs_bindings; close note #5 over-claims this as done but the primary tree is clean with all 20 instruction files still tracked

## Dependencies

- **Depends on:** [sase-1lj.1](sase-1lj.1.md) ✓ · ⧖ 2026-10-16
- **Blocks:** [sase-1lj.3](sase-1lj.3.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lj.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lj.2/README.md) | [sase-1lj.2](sase-1lj.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@181072b`](https://github.com/sase-org/sase-core/commit/181072b58e82a92c88f57a3d58952b049a50ddfe) | feat(content-layout): list only AGENTS.md and CLAUDE.md in project agent documents | [sase-1lj.2](sase-1lj.2.md) | 2026-10-16 18:06:18 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1lj.2][1] | Need the phase scope and design file | 4 |
| read-by | [agent:sase-1lj.3][2] | Need shim-retirement outcome and whether this workspace has its work | 1 |
| read-by | [agent:sase-1lj.5][3] | Check what shim-retirement phase actually did | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lj.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lj.3/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lj.5/README.md

<!-- sase:referenced-by:end -->
