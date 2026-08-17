# Bead: sase-nb.11.1 — Make the feature-flag memory project-local

[Bead Pages](../README.md) / [sase-nb.11](sase-nb.11.md) / sase-nb.11.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-nb.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-nb.land.md) · **Assignee:** `sase-nb.11.1` · **Size:** medium
**Created:** 2026-08-16 21:04:25 EDT
**Plan:** [202608/feature\_flags\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/feature_flags_landing.md)

## Description

memory: delete the generated sase_flags.md template and its _GeneratedLongMemorySpec, move the Tier 1 Feature Flags pointer out of the shipped sase.md template into a project-local note, and keep both notes as hand-written files in this repo only.

## Notes

[2026-08-17T01:16:59Z · sase-nb.11.1] PROGRESS: src/tests/docs work is done and 79 init-memory tests pass. Deleted memory-sase-flags.template.md and the _GeneratedLongMemorySpec; removed the Feature Flags block from memory-sase.template.md; dropped sase_flags.md from project_deploy staged paths and the generated README/docs copy. Remaining: create a project-local Tier 1 short note (recommended: sase/memory/feature_flags.md) or add the pointer to gotchas.md, then run sase memory init + just fmt-md + just check. Stopped here because gotchas.md requires explicit user permission in this conversation before editing sase/memory/*.md, AGENTS.md, or provider shims.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-nb.11.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-nb.11.1.md) | [sase-nb.11.1](sase-nb.11.1.md) | 0 |
