# Bead: sase-1tj.1 — Resolve research paths at agent run time

[Bead Pages](../README.md) / [sase-1tj](README.md) / sase-1tj.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1dz](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1dz.md) · **Assignee:** `sase-1tj.1` · **Size:** small
**Created:** 2026-11-18 11:26:28 EST
**Plan:** [202611/research\_commit\_gap.md](https://github.com/sase-org/sase--plans/blob/main/202611/research_commit_gap.md)

## Description

research-macro-paths: make the five research macros resolve the research checkout through an agent-run sase repo open research instead of a launch-time sase repo path substitution; update docs, add a regression test, and note the general launch-time cwd hazard.

## Notes

[2026-11-18T16:58:39Z · sase-1tj.1] PROPOSED FOLLOW-UP: Resolve the general launch-time cwd hazard with the sase-1tc land agent — since efc66a420b, cwd-dependent commands in macro bodies (for example sase repo path, git rev-parse, pwd) run against the runner cwd before workspace claim. Consider entering the known workspace before expansion for non-deferred launches, or delaying authored commands until after claim.

## Dependencies

- **Blocks:** [sase-1tj.3](sase-1tj.3.md) ◐ · ⧖ 2026-11-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tj.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tj.1/README.md) | [sase-1tj.1](sase-1tj.1.md) | 0 |
