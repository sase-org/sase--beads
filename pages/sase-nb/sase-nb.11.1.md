# Bead: sase-nb.11.1 — Make the feature-flag memory project-local

[Bead Pages](../README.md) / [sase-nb.11](sase-nb.11.md) / sase-nb.11.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-nb.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-nb.land.md) · **Assignee:** `sase-nb.11.1` · **Size:** medium
**Created:** 2026-08-16 21:04:25 EDT · **Closed:** 2026-08-16 21:35:11 EDT
**Plan:** [202608/feature\_flags\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/feature_flags_landing.md)

## Description

memory: delete the generated sase_flags.md template and its _GeneratedLongMemorySpec, move the Tier 1 Feature Flags pointer out of the shipped sase.md template into a project-local note, and keep both notes as hand-written files in this repo only.

## Notes

[2026-08-17T01:16:59Z · sase-nb.11.1] PROGRESS: src/tests/docs work is done and 79 init-memory tests pass. Deleted memory-sase-flags.template.md and the _GeneratedLongMemorySpec; removed the Feature Flags block from memory-sase.template.md; dropped sase_flags.md from project_deploy staged paths and the generated README/docs copy. Remaining: create a project-local Tier 1 short note (recommended: sase/memory/feature_flags.md) or add the pointer to gotchas.md, then run sase memory init + just fmt-md + just check. Stopped here because gotchas.md requires explicit user permission in this conversation before editing sase/memory/*.md, AGENTS.md, or provider shims.

[2026-08-17T01:34:38Z · sase-nb.11.1] PROPOSED FOLLOW-UP: retire leftover generated sase_flags.md copies — other projects that already ran sase init still have the old generated note, and init no longer deletes it because the packaged render is gone

[2026-08-17T01:35:11Z · sase-nb.11.1] Created project-local sase/memory/feature_flags.md (type:short); left sase_flags.md unchanged. Deleted the generated flags template and _GeneratedLongMemorySpec; removed the shipped Feature Flags block. sase memory list loads feature_flags.md in Tier 1 and references sase_flags.md in Tier 2; AGENTS.md hook is the sase_flags description. sase memory init --check is clean. Isolated managed-project init produces neither sase_flags.md nor a Feature Flags section. just check passed (138 scoped files).

[2026-08-17T01:36:21Z · sase-nb.11.1] Created project-local sase/memory/feature_flags.md (type:short); left sase_flags.md unchanged. Deleted the generated flags template and _GeneratedLongMemorySpec; removed the shipped Feature Flags block. sase memory list loads feature_flags.md in Tier 1 and references sase_flags.md in Tier 2; AGENTS.md hook is the sase_flags description. sase memory init --check is clean. Isolated managed-project init produces neither sase_flags.md nor a Feature Flags section. just check passed (138 scoped files).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-nb.11.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-nb.11.1.md) | [sase-nb.11.1](sase-nb.11.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f4cbb13`](https://github.com/sase-org/sase/commit/f4cbb138e20b7f57fdf6ea85031b3a13cb0b6a95) | feat(memory): keep feature-flag notes project-local | [sase-nb.11.1](sase-nb.11.1.md) | 2026-08-16 21:37:03 EDT |
