# Bead: sase-l3.6 — Skill deployment and instruction files

[Bead Pages](../README.md) / [sase-l3](README.md) / sase-l3.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zu](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zu.md) · **Assignee:** `sase-l3.6` · **Size:** small
**Created:** 2026-08-13 14:42:49 EDT · **Closed:** 2026-08-13 18:04:07 EDT
**Plan:** [202608/grok\_provider.md](https://github.com/sase-org/sase--plans/blob/main/202608/grok_provider.md)

## Description

skills: verify SASE skills deploy to and load from `~/.grok/skills/`, confirm the native-over-compat precedence and the no-shim AGENTS.md path, and record the CLAUDE.md double-load as a follow-up.

## Notes

[2026-08-13T22:03:02Z · sase-l3.6] PROPOSED FOLLOW-UP: Grok double-loads CLAUDE.md and AGENTS.md project instructions — Grok Build 1.0.3 inspect reports both files as project instructions, and [compat.claude] agents=false does not suppress generic CLAUDE.md; investigate a narrower mitigation that preserves Claude users in the same tree.

[2026-08-13T22:04:07Z · sase-l3.6] Added Grok skill/instruction coverage; verified focused pytest suite, Grok skill init dry-run targets dot_grok/skills, live Grok Build 1.0.3 inspect with temp HOME confirms native .grok skill shadows Claude compat and AGENTS.md is read without GROK.md; reran just check successfully.

[2026-08-13T22:05:41Z · sase-l3.6] Verified Grok skill deployment tests, temporary Grok inspect behavior, and just check before committing phase changes.

## Dependencies

- **Depends on:** [sase-l3.3](sase-l3.3.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-l3.7](sase-l3.7.md) ✓ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-l3.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-l3.6/README.md) | [sase-l3.6](sase-l3.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c1b2724`](https://github.com/sase-org/sase/commit/c1b2724a1fc46e264f1900395b2023644eb40552) | test: cover Grok skill deployment | [sase-l3.6](sase-l3.6.md) | 2026-08-13 18:06:36 EDT |
